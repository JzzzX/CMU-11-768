# Lec5 · Agent Capabilities 4: Planning, Task Decomposition, and Multi-Agent Coordination

- 日期：Tue, Sep 8（官网 Fall 2026 课表）
- 课表编号：3a
- 模块：Introduction and Agent Capabilities
- 整理日期：2026-10-27
- 来源：[CMU 11-768 课程日程](https://www.cmu-agents.com/#/schedule)
- 录像：[Lecture 5 recording](https://www.youtube.com/watch?v=S8v-dR4s29M&list=PLSN0qpDfUvTM&index=5)

## Slides

- [Lecture 5 slides](slides/Lec5-Slides.pdf) — PDF，48 页；[原始来源](https://www.cmu-agents.com/slides/lecture-05-planning.pdf)

## Readings · 官网阅读材料

- [Cursor: Introducing Plan Mode](readings/01-Cursor%20-%20Introducing%20Plan%20Mode.md) — 网页正文及链接；[原始来源](https://cursor.com/blog/plan-mode)
- [Least-to-Most Prompting](readings/02-Least-to-Most%20Prompting.pdf) — PDF，61 页；[原始来源](https://arxiv.org/abs/2205.10625)
- [Decomposed Prompting](readings/03-Decomposed%20Prompting.pdf) — PDF，69 页；[原始来源](https://arxiv.org/abs/2210.02406)
- [Code as Policies](readings/04-Code%20as%20Policies.pdf) — PDF，16 页；[原始来源](https://arxiv.org/abs/2209.07753)
- [SayCan](readings/05-SayCan.pdf) — PDF，34 页；[原始来源](https://arxiv.org/abs/2204.01691)
- [Plan-and-Act](readings/06-Plan-and-Act.pdf) — PDF，44 页；[原始来源](https://arxiv.org/abs/2503.09572)
- [Thinking vs. Doing](readings/07-Thinking%20vs.%20Doing.pdf) — PDF，41 页；[原始来源](https://arxiv.org/abs/2506.07976)
- [Calibrate-Then-Act](readings/08-Calibrate-Then-Act.pdf) — PDF，35 页；[原始来源](https://arxiv.org/abs/2602.16699)
- [Recursive Agent Optimization (RAO)](readings/09-Recursive%20Agent%20Optimization%20%28RAO%29.pdf) — PDF，30 页；[原始来源](https://arxiv.org/abs/2605.06639)
- [Multi-Agent Computer Use (MACU)](readings/10-Multi-Agent%20Computer%20Use%20%28MACU%29.pdf) — PDF，42 页；[原始来源](https://arxiv.org/abs/2606.01533)

## References · 官网补充参考

- [Claude Code Permission Modes](references/01-Claude%20Code%20Permission%20Modes.md) — 项目或网页说明与链接；[原始来源](https://code.claude.com/docs/en/cli-usage)
- [OpenAI Model Guidance](references/02-OpenAI%20Model%20Guidance.md) — 项目或网页说明与链接；[原始来源](https://developers.openai.com/api/docs/guides/latest-model)
- [Large Language Models are Zero-Shot Reasoners](references/03-Large%20Language%20Models%20are%20Zero-Shot%20Reasoners.pdf) — PDF，42 页；[原始来源](https://arxiv.org/abs/2205.11916)
- [Plan-and-Solve Prompting](references/04-Plan-and-Solve%20Prompting.pdf) — PDF，24 页；[原始来源](https://arxiv.org/abs/2305.04091)
- [STaR](references/05-STaR.pdf) — PDF，30 页；[原始来源](https://arxiv.org/abs/2203.14465)
- [DeepSeek-R1](references/06-DeepSeek-R1.pdf) — PDF，86 页；[原始来源](https://arxiv.org/abs/2501.12948)
- [Recursive Language Models](references/07-Recursive%20Language%20Models.pdf) — PDF，43 页；[原始来源](https://arxiv.org/abs/2512.24601)
- [PlanBench](references/08-PlanBench.pdf) — PDF，50 页；[原始来源](https://arxiv.org/abs/2206.10498)
- [ProgPrompt](references/09-ProgPrompt.pdf) — PDF，8 页；[原始来源](https://arxiv.org/abs/2209.11302)
- [Binder](references/10-Binder.pdf) — PDF，27 页；[原始来源](https://arxiv.org/abs/2210.02875)
- [Anthropic: Building Effective Agents](references/11-Anthropic%20-%20Building%20Effective%20Agents.md) — 项目或网页说明与链接；[原始来源](https://www.anthropic.com/engineering/building-effective-agents)
- [UGround](references/12-UGround.pdf) — PDF，34 页；[原始来源](https://arxiv.org/abs/2410.05243)
- [Agent S](references/13-Agent%20S.pdf) — PDF，23 页；[原始来源](https://arxiv.org/abs/2410.08164)
- [Language Models as Zero-Shot Planners](references/14-Language%20Models%20as%20Zero-Shot%20Planners.pdf) — PDF，33 页；[原始来源](https://arxiv.org/abs/2201.07207)
- [LLM-Planner](references/15-LLM-Planner.pdf) — PDF，14 页；[原始来源](https://arxiv.org/abs/2212.04088)
- [Inner Monologue](references/16-Inner%20Monologue.pdf) — PDF，25 页；[原始来源](https://arxiv.org/abs/2207.05608)
- [SwiftSage](references/17-SwiftSage.pdf) — PDF，18 页；[原始来源](https://arxiv.org/abs/2305.17390)
- [The Danger of Overthinking](references/18-The%20Danger%20of%20Overthinking.pdf) — PDF，16 页；[原始来源](https://arxiv.org/abs/2502.08235)
- [Training Proactive and Personalized LLM Agents (PPP-Agent)](references/19-Training%20Proactive%20and%20Personalized%20LLM%20Agents%20%28PPP-Agent%29.pdf) — PDF，23 页；[原始来源](https://arxiv.org/abs/2511.02208)
- [Vending-Bench](references/20-Vending-Bench.pdf) — PDF，28 页；[原始来源](https://arxiv.org/abs/2502.15840)
- [The Illusion of Diminishing Returns](references/21-The%20Illusion%20of%20Diminishing%20Returns.pdf) — PDF，28 页；[原始来源](https://arxiv.org/abs/2509.09677)
- [ADaPT](references/22-ADaPT.pdf) — PDF，27 页；[原始来源](https://arxiv.org/abs/2311.05772)
- [Web Agents Should Adopt the Plan-Then-Execute Paradigm](references/23-Web%20Agents%20Should%20Adopt%20the%20Plan-Then-Execute%20Paradigm.pdf) — PDF，15 页；[原始来源](https://arxiv.org/abs/2605.14290)
- [TravelPlanner](references/24-TravelPlanner.pdf) — PDF，24 页；[原始来源](https://arxiv.org/abs/2402.01622)
- [Odysseys](references/25-Odysseys.md) — 项目或网页说明与链接；[原始来源](https://odysseys-website.pages.dev/)
- [Don't Sleep on Single-Agent Systems](references/26-Don%27t%20Sleep%20on%20Single-Agent%20Systems.md) — 项目或网页说明与链接；[原始来源](https://www.openhands.dev/blog/dont-sleep-on-single-agent-systems)
