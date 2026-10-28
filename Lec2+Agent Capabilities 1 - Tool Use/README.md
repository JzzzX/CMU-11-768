# Lec2 · Agent Capabilities 1: Tool Use

- 日期：Thu, Aug 27（官网 Fall 2026 课表）
- 课表编号：1b
- 模块：Introduction and Agent Capabilities
- 整理日期：2026-10-27
- 来源：[CMU 11-768 课程日程](https://www.cmu-agents.com/#/schedule)
- 录像：[Lecture 2 recording](https://www.youtube.com/watch?v=jXChFB4JSyw&list=PLSN0qpDfUvTM&index=2)

## Slides

- [Lecture 2 slides](slides/Lec2-Slides.pdf) — PDF，60 页；[原始来源](https://www.cmu-agents.com/slides/lecture-02-tool-use.pdf)

## Readings · 官网阅读材料

- [What Are Tools Anyway?](readings/01-What%20Are%20Tools%20Anyway.pdf) — PDF，20 页；[原始来源](https://arxiv.org/abs/2403.15452)
- [CodeAct](readings/02-CodeAct.pdf) — PDF，25 页；[原始来源](https://arxiv.org/abs/2402.01030)
- [Toolformer](readings/03-Toolformer.pdf) — PDF，17 页；[原始来源](https://arxiv.org/abs/2302.04761)
- [XGrammar](readings/04-XGrammar.pdf) — PDF，17 页；[原始来源](https://arxiv.org/abs/2411.15100)

## References · 官网补充参考

- [OpenAI Chat Completions API](references/01-OpenAI%20Chat%20Completions%20API.md) — 项目或网页说明与链接；[原始来源](https://platform.openai.com/docs/api-reference/chat/create)
- [Hugging Face Chat Templates](references/02-Hugging%20Face%20Chat%20Templates.md) — 项目或网页说明与链接；[原始来源](https://huggingface.co/docs/transformers/chat_templating)
- [Qwen2.5 Chat Template](references/03-Qwen2.5%20Chat%20Template.md) — 项目或网页说明与链接；[原始来源](https://huggingface.co/Qwen/Qwen2.5-7B-Instruct/blob/main/tokenizer_config.json)
- [Berkeley Function-Calling Leaderboard V4](references/04-Berkeley%20Function-Calling%20Leaderboard%20V4.md) — 项目或网页说明与链接；[原始来源](https://gorilla.cs.berkeley.edu/leaderboard.html)
- [BFCL V4 Methodology](references/05-BFCL%20V4%20Methodology.md) — 项目或网页说明与链接；[原始来源](https://gorilla.cs.berkeley.edu/blogs/15_bfcl_v4_web_search.html)
- [OpenRouter Provider Analytics](references/06-OpenRouter%20Provider%20Analytics.md) — 项目或网页说明与链接；[原始来源](https://openrouter.ai/)
- [OpenAI Function Calling Guide](references/07-OpenAI%20Function%20Calling%20Guide.md) — 项目或网页说明与链接；[原始来源](https://developers.openai.com/api/docs/guides/function-calling)
- [Qwen3.8 Tool-Call Template](references/08-Qwen3.8%20Tool-Call%20Template.md) — 项目或网页说明与链接；[原始来源](https://huggingface.co/Qwen/Qwen3.8-27B/blob/main/tokenizer_config.json)
- [Mistral Small 4 Model Card](references/09-Mistral%20Small%204%20Model%20Card.md) — 项目或网页说明与链接；[原始来源](https://huggingface.co/mistralai/Mistral-Small-4-119B-2603)
- [Mistral Tool-Call Tokenization Guide](references/10-Mistral%20Tool-Call%20Tokenization%20Guide.md) — 项目或网页说明与链接；[原始来源](https://github.com/mistralai/cookbook/blob/main/concept-deep-dive/tokenization/tool_calling.md)
- [DeepSeek V3.2 Tool-Call Encoding](references/11-DeepSeek%20V3.2%20Tool-Call%20Encoding.md) — 项目或网页说明与链接；[原始来源](https://huggingface.co/deepseek-ai/DeepSeek-V3.2/blob/main/encoding/encoding_dsv32.py)
- [OpenHands Tool System Architecture](references/12-OpenHands%20Tool%20System%20Architecture.md) — 项目或网页说明与链接；[原始来源](https://docs.openhands.dev/sdk/arch/tool-system)
- [OpenHands Agent Dispatch Source](references/13-OpenHands%20Agent%20Dispatch%20Source.md) — 项目或网页说明与链接；[原始来源](https://github.com/OpenHands/software-agent-sdk/blob/main/openhands-sdk/openhands/sdk/agent/agent.py)
- [OpenHands ToolDefinition Source](references/14-OpenHands%20ToolDefinition%20Source.md) — 项目或网页说明与链接；[原始来源](https://github.com/OpenHands/software-agent-sdk/blob/main/openhands-sdk/openhands/sdk/tool/tool.py)
- [JSON Schema 2020-12](references/15-JSON%20Schema%202020-12.md) — 项目或网页说明与链接；[原始来源](https://json-schema.org/draft/2020-12/json-schema-core.html)
- [JSON Schema 2020-12 Validation](references/16-JSON%20Schema%202020-12%20Validation.md) — 项目或网页说明与链接；[原始来源](https://json-schema.org/draft/2020-12/json-schema-validation.html)
- [OpenAPI Specification](references/17-OpenAPI%20Specification.md) — 项目或网页说明与链接；[原始来源](https://spec.openapis.org/oas/latest.html)
- [FastAPI Generated OpenAPI](references/18-FastAPI%20Generated%20OpenAPI.md) — 项目或网页说明与链接；[原始来源](https://fastapi.tiangolo.com/tutorial/first-steps/#openapi)
- [FastAPI Security and OpenAPI](references/19-FastAPI%20Security%20and%20OpenAPI.md) — 项目或网页说明与链接；[原始来源](https://fastapi.tiangolo.com/tutorial/security/)
- [MCP 2026-07-28 Specification Release](references/20-MCP%202026-07-28%20Specification%20Release.md) — 项目或网页说明与链接；[原始来源](https://blog.modelcontextprotocol.io/posts/2026-07-28/)
- [MCP TypeScript SDK v2 Overview](references/21-MCP%20TypeScript%20SDK%20v2%20Overview.md) — 项目或网页说明与链接；[原始来源](https://ts.sdk.modelcontextprotocol.io/v2/)
- [MCP Transports Specification](references/22-MCP%20Transports%20Specification.md) — 项目或网页说明与链接；[原始来源](https://modelcontextprotocol.io/specification/draft/basic/transports)
- [MCP Tools Specification](references/23-MCP%20Tools%20Specification.md) — 项目或网页说明与链接；[原始来源](https://modelcontextprotocol.io/specification/draft/server/tools)
- [FastMCP OpenAPI Integration](references/24-FastMCP%20OpenAPI%20Integration.md) — 项目或网页说明与链接；[原始来源](https://gofastmcp.com/integrations/openapi)
- [FastMCP Token Verification](references/25-FastMCP%20Token%20Verification.md) — 项目或网页说明与链接；[原始来源](https://gofastmcp.com/servers/auth/token-verification)
- [FastMCP Bearer Client Authentication](references/26-FastMCP%20Bearer%20Client%20Authentication.md) — 项目或网页说明与链接；[原始来源](https://gofastmcp.com/clients/auth/bearer)
