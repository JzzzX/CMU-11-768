# Thinking in LangGraph

- 资料链接：[Thinking in LangGraph](https://docs.langchain.com/oss/python/langgraph/thinking-in-langgraph)
- 所属：Lec15 · Frameworks 2: Orchestration and Monitoring
- 官网分类：readings
- 整理日期：2026-10-27

网页官方简介：Learn how to think about building agents with LangGraph

## 网页正文摘存

以下为自动提取的正文，图片、交互内容及格式可能不完整，请以原网页为准。

## ​ Start with the process you want to automate

The agent should: - Read incoming customer emails - Classify them by urgency and topic - Search relevant documentation to answer questions - Draft appropriate responses - Escalate complex issues to human agents - Schedule follow-ups when needed Example scenarios to handle: 1. Simple product question: "How do I reset my password?" 2. Bug report: "The export feature crashes when I select PDF format" 3. Urgent billing issue: "I was charged twice for my subscription!" 4. Feature request: "Can you add dark mode to the mobile app?" 5. Complex technical issue: "Our API integration fails intermittently with 504 errors"

## ​ Step 1: Map out your workflow as discrete steps

- Read Email : Extract and parse the email content

- Classify Intent : Use an LLM to categorize urgency and topic, then route to appropriate action

- Doc Search : Query your knowledge base for relevant information

- Bug Track : Create or update issue in tracking system

- Draft Reply : Generate an appropriate response

- Human Review : Escalate to human agent for approval or handling

- Send Reply : Dispatch the email response

## ​ Step 2: Identify what each step needs to do

## LLM steps

## Data steps

## Action steps

## User input steps

### ​ LLM steps

Classify intent

- Static context (prompt): Classification categories, urgency definitions, response format

- Dynamic context (from state): Email content, sender information

- Desired outcome: Structured classification that determines routing

Draft reply

- Static context (prompt): Tone guidelines, company policies, response templates

- Dynamic context (from state): Classification results, search results, customer history

- Desired outcome: Professional email response ready for review

### ​ Data steps

Document search

- Parameters: Query built from intent and topic

- Retry strategy: Yes, with exponential backoff for transient failures

- Caching: Could cache common queries to reduce API calls

Customer history lookup

- Parameters: Customer email or ID from state

- Retry strategy: Yes, but with fallback to basic info if unavailable

- Caching: Yes, with time-to-live to balance freshness and performance

### ​ Action steps

Send reply

- When to execute node: After approval (human or automated)

- Retry strategy: Yes, with exponential backoff for network issues

- Should not cache: Each send is a unique action

Bug track

- When to execute node: Always when intent is “bug”

- Retry strategy: Yes, critical to not lose bug reports

- Returns: Ticket ID to include in response

### ​ User input steps

Human review node

- Context for decision: Original email, draft response, urgency, classification

- Expected input format: Approval boolean plus optional edited response

- When triggered: High urgency, complex issues, or quality concerns

## ​ Step 3: Design your state

### ​ What belongs in state?

## Include in state

## Don't store

- The original email and sender info (can’t reconstruct these later)

- Classification results (needed by multiple later/downstream nodes)

- Search results and customer data (expensive to re-fetch)

- The draft response (needs to persist through review)

- Execution metadata (for debugging and recovery)

### ​ Keep state raw, format prompts on-demand

- Different nodes can format the same data differently for their needs

- You can change prompt templates without modifying your state schema

- Debugging is clearer—you see exactly what data each node received

- Your agent can evolve without breaking existing state

from typing import TypedDict , Literal # Define the structure for email classification class EmailClassification ( TypedDict ): intent : Literal [ " question " , " bug " , " billing " , " feature " , " complex " ] urgency : Literal [ " low " , " medium " , " high " , " critical " ] topic : str summary : str class EmailAgentState ( TypedDict ): # Raw email data email_content : str sender_email : str email_id : str # Classification result classification : EmailClassification | None # Raw search/API results search_results : list [ str ] | None # List of raw document chunks customer_history : dict | None # Raw customer data from CRM # Generated content draft_response : str | None messages : list [ str ] | None

## ​ Step 4: Build your nodes

### ​ Handle errors appropriately

- Transient errors

- LLM-recoverable

- User-fixable

- Unexpected

- Saga / compensation

from langgraph . types import RetryPolicy workflow . add_node ( "search_documentation" , search_documentation , retry_policy = RetryPolicy ( max_attempts = 3 , initial_interval = 1.0 ) )

from langgraph . types import Command def execute_tool ( state : State ) -> Command [ Literal [ " agent " , " execute_tool " ]]: try : result = run_tool ( state [ ' tool_call ' ]) return Command ( update = { "tool_result" : result }, goto = "agent" ) except ToolError as e : # Let the LLM see what went wrong and try again return Command ( update = { "tool_result" : f "Tool error: { str ( e ) } " }, goto = "agent" )

from langgraph . types import Command def lookup_customer_history ( state : State ) -> Command [ Literal [ " lookup_customer_history " , " draft_response " ]]: if not state . get ( 'customer_id' ): user_input = interrupt ({ "message" : "Customer ID needed" , "request" : "Please provide the customer's account ID to look up their subscription history" }) return Command ( update = { "customer_id" : user_input [ ' customer_id ' ]}, goto = "lookup_customer_history" ) # Now proceed with the lookup customer_data = fetch_customer_history ( state [ ' customer_id ' ]) return Command ( update = { "customer_history" : customer_data }, goto = "draft_response" )

def send_reply ( state : EmailAgentState ): try : email_service . send ( state [ " draft_response " ]) except Exception : raise # Surface unexpected errors

from langgraph . errors import NodeError from langgraph . types import Command , RetryPolicy def payment_error_handler ( state : State , error : NodeError ) -> Command : return Command ( update = { "status" : f "compensated: { error . error } " }, goto = "finalize" , ) workflow . add_node ( "charge_payment" , charge_payment , retry_policy = RetryPolicy ( max_attempts = 3 , retry_on = ConnectionError ), error_handler = payment_error_handler , )

### ​ Implementing our email agent nodes

Read and classify nodes

from typing import Literal from langgraph . graph import StateGraph , START , END from langgraph . types import interrupt , Command , RetryPolicy from langchain_openai import ChatOpenAI from langchain . messages import HumanMessage llm = ChatOpenAI ( model = "gpt-5-nano" ) def read_email ( state : EmailAgentState ) -> dict : """Extract and parse email content""" # In production, this would connect to your email service return { "messages" : [ HumanMessage ( content = f "Processing email: { state [ ' email_content ' ] } " )] } def classify_intent ( state : EmailAgentState ) -> Command [ Literal [ " search_documentation " , " human_review " , " draft_response " , " bug_tracking " ]]: """Use LLM to classify email intent and urgency, then route accordingly""" # Create structured LLM that returns EmailClassification dict structured_llm = llm . with_structured_output ( EmailClassification ) # Format the prompt on-demand, not stored in state classification_prompt = f """ Analyze this customer email and classify it: Email: { state [ ' email_content ' ] } From: { state [ ' sender_email ' ] } Provide classification including intent, urgency, topic, and summary. """ # Get structured response directly as dict classification = structured_llm . invoke ( classification_prompt ) # Determine next node based on classification if classification [ ' intent ' ] == 'billing' or classification [ ' urgency ' ] == 'critical' : goto = "human_review" elif classification [ ' intent ' ] in [ 'question' , 'feature' ]: goto = "search_documentation" elif classification [ ' intent ' ] == 'bug' : goto = "bug_tracking" else : goto = "draft_response" # Store classification as a single dict in state return Command ( update = { "classification" : classification }, goto = goto )

Search and tracking nodes

def search_documentation ( state : EmailAgentState ) -> Command [ Literal [ " draft_response " ]]: """Search knowledge base for relevant information""" # Build search query from classification classification = state . get ( 'classification' , {}) query = f " { classification . get ( 'intent' , '' ) } { classification . get ( 'topic' , '' ) } " try : # Implement your search logic here # Store raw search results, not formatted text search_results = [ "Reset password via Settings > Security > Change Password" , "Password must be at least 12 characters" , "Include uppercase, lowercase, numbers, and symbols" ] except SearchAPIError as e : # For recoverable search errors, store error and continue search_results = [ f "Search temporarily unavailable: { str ( e ) } " ] return Command ( update = { "search_results" : search_results }, # Store raw results or error goto = "draft_response" ) def bug_tracking ( state : EmailAgentState ) -> Command [ Literal [ " draft_response " ]]: """Create or update bug tracking ticket""" # Create ticket in your bug tracking system ticket_id = "BUG-12345" # Would be created via API return Command ( update = { "search_results" : [ f "Bug ticket { ticket_id } created" ], "current_step" : "bug_tracked" }, goto = "draft_response" )

Response nodes

def draft_response ( state : EmailAgentState ) -> Command [ Literal [ " human_review " , " send_reply " ]]: """Generate response using context and route based on quality""" classification = state . get ( 'classification' , {}) # Format context from raw state data on-demand context_sections = [] if state . get ( 'search_results' ): # Format search results for the prompt formatted_docs = " \n " . join ([ f "- { doc } " for doc in state [ ' search_results ' ]]) context_sections . append ( f "Relevant documentation: \n{ formatted_docs } " ) if state . get ( 'customer_history' ): # Format customer data for the prompt context_sections . append ( f "Customer tier: { state [ ' customer_history ' ]. get ( 'tier' , 'standard' ) } " ) # Build the prompt with formatted context draft_prompt = f """ Draft a response to this customer email: { state [ ' email_content ' ] } Email intent: { classification . get ( 'intent' , 'unknown' ) } Urgency level: { classification . get ( 'urgency' , 'medium' ) } { chr ( 10 ). join ( context_sections ) } Guidelines: - Be professional and helpful - Address their specific concern - Use the provided documentation when relevant """ response = llm . invoke ( draft_prompt ) # Determine if human review needed based on urgency and intent needs_review = ( classification . get ( 'urgency' ) in [ 'high' , 'critical' ] or classification . get ( 'intent' ) == 'complex' ) # Route to appropriate next node goto = "human_review" if needs_review else "send_reply" return Command ( update = { "draft_response" : response . content }, # Store only the raw response goto = goto ) def human_review ( state : EmailAgentState ) -> Command [ Literal [ " send_reply " , END ]]: """Pause for human review using interrupt and route based on decision""" classification = state . get ( 'classification' , {}) # interrupt() must come first - any code before it will re-run on resume human_decision = interrupt ({ "email_id" : state . get ( 'email_id' , '' ), "original_email" : state . get ( 'email_content' , '' ), "draft_response" : state . get ( 'draft_response' , '' ), "urgency" : classification . get ( 'urgency' ), "intent" : classification . get ( 'intent' ), "action" : "Please review and approve/edit this response" }) # Now process the human's decision if human_decision . get ( "approved" ): return Command ( update = { "draft_response" : human_decision . get ( "edited_response" , state . get ( 'draft_response' , '' ))}, goto = "send_reply" ) else : # Rejection means human will handle directly return Command ( update = {}, goto = END ) def send_reply ( state : EmailAgentState ) -> dict : """Send the email response""" # Integrate with email service print ( f "Sending reply: { state [ ' draft_response ' ][: 100 ] } ..." ) return {}

## ​ Step 5: Wire it together

Graph compilation code

from langgraph . checkpoint . memory import MemorySaver from langgraph . types import RetryPolicy # Create the graph workflow = StateGraph ( EmailAgentState ) # Add nodes with appropriate error handling workflow . add_node ( "read_email" , read_email ) workflow . add_node ( "classify_intent" , classify_intent ) # Add retry policy for nodes that might have transient failures workflow . add_node ( "search_documentation" , search_documentation , retry_policy = RetryPolicy ( max_attempts = 3 ) ) workflow . add_node ( "bug_tracking" , bug_tracking ) workflow . add_node ( "draft_response" , draft_response ) workflow . add_node ( "human_review" , human_review ) workflow . add_node ( "send_reply" , send_reply ) # Add only the essential edges workflow . add_edge ( START , "read_email" ) workflow . add_edge ( "read_email" , "classify_intent" ) workflow . add_edge ( "send_reply" , END ) # Compile with checkpointer for persistence, in case run graph with Local_Server --> Please compile without checkpointer memory = MemorySaver () app = workflow . compile ( checkpointer = memory )

### ​ Try out your agent

Testing the agent

from typing import TypedDict from langgraph . checkpoint . memory import InMemorySaver from langgraph . graph import END , START , StateGraph from langgraph . types import Command , interrupt class EmailState ( TypedDict ): email_content : str response_text : str | None def human_review_node ( state : EmailState ): interrupt ( { "approved" : False , "edited_response" : state . get ( "response_text" ) or "" , } ) return { "response_text" : "placeholder" } app = ( StateGraph ( EmailState ) . add_node ( "human_review" , human_review_node ) . add_edge ( START , "human_review" ) . add_edge ( "human_review" , END ) . compile ( checkpointer = InMemorySaver ()) ) initial_state = { "email_content" : "I was charged twice for my subscription! This is urgent!" , "response_text" : "Draft response" , } # Run with a thread_id for persistence config = { "configurable" : { "thread_id" : "customer_123" }} stream = app . stream_events ( initial_state , config , version = "v3" ) _ = stream . output # drive the stream to completion # The graph will pause at human_review print ( f "human review interrupt: { stream . interrupts } " ) human_response = Command ( resume = { "approved" : True , "edited_response" : "We sincerely apologize for the double charge. I've initiated an immediate refund..." , } ) # Resume execution resumed = app . stream_events ( human_response , config , version = "v3" ) final_state = resumed . output print ( "Email sent successfully!" )

## View example trace

## ​ Summary and next steps

### ​ Key Insights

## Break into discrete steps

## State is shared memory

## Nodes are functions

## Errors are part of the flow

## Human input is first-class

## Graph structure emerges naturally

### ​ Advanced considerations

Node granularity trade-offs

- Isolation of external services: Doc Search and Bug Track are separate nodes because they call external APIs. If the search service is slow or fails, we want to isolate that from the LLM calls. We can add retry policies to these specific nodes without affecting others.

- Intermediate visibility: Having Classify Intent as its own node lets us inspect what the LLM decided before taking action. This is valuable for debugging and monitoring—you can see exactly when and why the agent routes to human review.

- Different failure modes: LLM calls, database lookups, and email sending have different retry strategies. Separate nodes let you configure these independently.

- Reusability and testing: Smaller nodes are easier to test in isolation and reuse in other workflows.

### ​ Where to go from here

## Human-in-the-loop patterns

## Subgraphs

## Streaming

## Observability

## Tool Integration

## Retry Logic

Was this page helpful?
