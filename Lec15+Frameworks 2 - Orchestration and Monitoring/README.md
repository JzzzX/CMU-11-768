# Lec15 · Frameworks 2: Orchestration and Monitoring

- 日期：Tue, Oct 20（官网 Fall 2026 课表）
- 课表编号：9a
- 模块：Agent Frameworks
- 整理日期：2026-10-27
- 来源：[CMU 11-768 课程日程](https://www.cmu-agents.com/#/schedule)

## Slides

- [Lecture 15 slides](slides/Lec15-Slides.pdf) — PDF，39 页；[原始来源](https://www.cmu-agents.com/slides/lecture-15-orchestration-and-monitoring.pdf)

## Readings · 官网阅读材料

- [Building effective agents](readings/01-Building%20effective%20agents.md) — 项目或网页说明与链接；[原始来源](https://www.anthropic.com/engineering/building-effective-agents)
- [Thinking in LangGraph](readings/02-Thinking%20in%20LangGraph.md) — 网页正文及链接；[原始来源](https://docs.langchain.com/oss/python/langgraph/thinking-in-langgraph)
- [Diagnosing a performance regression on Terminal-Bench with Docent](readings/03-Diagnosing%20a%20performance%20regression%20on%20Terminal-Bench%20with%20Docent.md) — 网页正文及链接；[原始来源](https://transluce.org/docent/blog/terminal-bench)
- [Hodoscope: Unsupervised Monitoring for AI Misbehaviors](readings/04-Hodoscope%20-%20Unsupervised%20Monitoring%20for%20AI%20Misbehaviors.pdf) — PDF，21 页；[原始来源](https://arxiv.org/abs/2604.11072)

## References · 官网补充参考

- [LangGraph: Workflows and agents](references/01-LangGraph%20-%20Workflows%20and%20agents.md) — 项目或网页说明与链接；[原始来源](https://docs.langchain.com/oss/python/langgraph/workflows-agents)
- [LangGraph: Persistence](references/02-LangGraph%20-%20Persistence.md) — 项目或网页说明与链接；[原始来源](https://docs.langchain.com/oss/python/langgraph/persistence)
- [LangGraph: Interrupts](references/03-LangGraph%20-%20Interrupts.md) — 项目或网页说明与链接；[原始来源](https://docs.langchain.com/oss/python/langgraph/interrupts)
- [LangGraph: Testing](references/04-LangGraph%20-%20Testing.md) — 项目或网页说明与链接；[原始来源](https://docs.langchain.com/oss/python/langgraph/test)
- [LangChain: Testing](references/05-LangChain%20-%20Testing.md) — 项目或网页说明与链接；[原始来源](https://docs.langchain.com/oss/python/langchain/test)
- [LangSmith: Evaluation](references/06-LangSmith%20-%20Evaluation.md) — 项目或网页说明与链接；[原始来源](https://docs.langchain.com/langsmith/evaluation)
- [Course support demo: password-reset trace](references/07-Course%20support%20demo%20-%20password-reset%20trace.md) — 项目或网页说明与链接；[原始来源](https://smith.langchain.com/public/5e17b93a-17af-4386-ada0-9bd033f98a74/r)
- [Course support demo: billing trace before approval](references/08-Course%20support%20demo%20-%20billing%20trace%20before%20approval.md) — 项目或网页说明与链接；[原始来源](https://smith.langchain.com/public/aeddf201-687b-4389-acdb-137dd9683000/r)
- [Course support demo: billing trace after approval](references/09-Course%20support%20demo%20-%20billing%20trace%20after%20approval.md) — 项目或网页说明与链接；[原始来源](https://smith.langchain.com/public/416d3c74-4b43-4883-b189-92a57431a819/r)
- [Docent: Pairwise comparisons and failure-mode synthesis](references/10-Docent%20-%20Pairwise%20comparisons%20and%20failure-mode%20synthesis.md) — 项目或网页说明与链接；[原始来源](https://docent.transluce.org/dashboard/9bafeb94-3f6e-4d03-bd01-1ae8476e3f6e/analysis-plan/81230a32-88e0-42af-82c9-101660ab1d89)
- [Docent: No-timeout task comparison](references/11-Docent%20-%20No-timeout%20task%20comparison.md) — 项目或网页说明与链接；[原始来源](https://docent.transluce.org/dashboard/9bafeb94-3f6e-4d03-bd01-1ae8476e3f6e/analysis-plan/772c0920-0b0f-4355-a009-825d1dd553b4)
- [Hodoscope announcement](references/12-Hodoscope%20announcement.md) — 项目或网页说明与链接；[原始来源](https://hodoscope.dev/blog/announcement.html)
- [Embedding Atlas](references/13-Embedding%20Atlas.md) — 项目或网页说明与链接；[原始来源](https://apple.github.io/embedding-atlas/)
- [OpenHands SDK](references/14-OpenHands%20SDK.md) — 项目或网页说明与链接；[原始来源](https://docs.openhands.dev/sdk)
- [LangGraph overview](references/15-LangGraph%20overview.md) — 项目或网页说明与链接；[原始来源](https://docs.langchain.com/oss/python/langgraph/overview)
- [OpenAI Agents SDK](references/16-OpenAI%20Agents%20SDK.md) — 项目或网页说明与链接；[原始来源](https://openai.github.io/openai-agents-python/)
- [AG2 overview](references/17-AG2%20overview.md) — 项目或网页说明与链接；[原始来源](https://docs.ag2.ai/latest/docs/user-guide/basic-concepts/overview/)
- [DSPy](references/18-DSPy.md) — 项目或网页说明与链接；[原始来源](https://dspy.ai/)
- [Don’t Sleep on Single-Agent Systems](references/19-Don%E2%80%99t%20Sleep%20on%20Single-Agent%20Systems.md) — 项目或网页说明与链接；[原始来源](https://hub.openhands.dev/blog/dont-sleep-on-single-agent-systems)
- [Agent Skills specification](references/20-Agent%20Skills%20specification.md) — 项目或网页说明与链接；[原始来源](https://agentskills.io/specification)
- [Multi-Agent Computer Use (MACU)](references/21-Multi-Agent%20Computer%20Use%20%28MACU%29.pdf) — PDF，42 页；[原始来源](https://arxiv.org/abs/2606.01533)
- [OpenHands automations: Fujitsu talk slides](references/22-OpenHands%20automations%20-%20Fujitsu%20talk%20slides.md) — 项目或网页说明与链接；[原始来源](https://github.com/neubig/slides/tree/main/slides/2026-09-25-fujitsu-openhands-en)
- [Black Hat USA 2026: The OpenAI–Hugging Face incident](references/23-Black%20Hat%20USA%202026%20-%20The%20OpenAI%E2%80%93Hugging%20Face%20incident.md) — 项目或网页说明与链接；[原始来源](https://www.youtube.com/watch?v=87DyyMV0kCY)
- [OpenAI: Hugging Face incident and the road ahead](references/24-OpenAI%20-%20Hugging%20Face%20incident%20and%20the%20road%20ahead.md) — 项目或网页说明与链接；[原始来源](https://openai.com/index/hugging-face-incident-and-the-road-ahead/)
