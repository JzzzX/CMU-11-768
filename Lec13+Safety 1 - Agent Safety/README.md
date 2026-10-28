# Lec13 · Safety 1: Agent Safety

- 日期：Tue, Oct 6（官网 Fall 2026 课表）
- 课表编号：7a
- 模块：Agent Safety
- 整理日期：2026-10-27
- 来源：[CMU 11-768 课程日程](https://www.cmu-agents.com/#/schedule)

## Slides

- [Lecture 13 slides](slides/Lec13-Slides.pdf) — PDF，43 页；[原始来源](https://www.cmu-agents.com/slides/lecture-13-agent-safety.pdf)

## References · 官网补充参考

- [OpenClaw incident report](references/01-OpenClaw%20incident%20report.md) — 项目或网页说明与链接；[原始来源](https://x.com/summeryue0/status/2025774069124399363)
- [PocketOS database-deletion incident](references/02-PocketOS%20database-deletion%20incident.md) — 项目或网页说明与链接；[原始来源](https://thenewstack.io/ai-agents-credential-crisis)
- [Microsoft advisory: CVE-2025-32711](references/03-Microsoft%20advisory%20-%20CVE-2025-32711.md) — 项目或网页说明与链接；[原始来源](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-32711)
- [Cline supply-chain compromise postmortem](references/04-Cline%20supply-chain%20compromise%20postmortem.md) — 项目或网页说明与链接；[原始来源](https://cline.bot/blog/post-mortem-unauthorized-cline-cli-npm)
- [Gambit Security: AI agents targeting online retailers](references/05-Gambit%20Security%20-%20AI%20agents%20targeting%20online%20retailers.md) — 项目或网页说明与链接；[原始来源](https://gambit.security/blog-posts/autonomous-ai-agents-online-retailers-25-a-company)
- [AgentDojo](references/06-AgentDojo.pdf) — PDF，26 页；[原始来源](https://arxiv.org/abs/2406.13352v3)
- [ToolEmu](references/07-ToolEmu.pdf) — PDF，70 页；[原始来源](https://arxiv.org/abs/2309.15817v2)
- [Introducing Docent](references/08-Introducing%20Docent.md) — 项目或网页说明与链接；[原始来源](https://transluce.org/docent/blog/introducing-docent)
- [Gray Swan Arena: Agent Red-Teaming Challenge](references/09-Gray%20Swan%20Arena%20-%20Agent%20Red-Teaming%20Challenge.md) — 项目或网页说明与链接；[原始来源](https://app.grayswan.ai/arena/challenge/agent-red-teaming/leaderboard)
- [Security Challenges in AI Agent Deployment: Insights from a Large Scale Public Competition](references/10-Security%20Challenges%20in%20AI%20Agent%20Deployment%20-%20Insights%20from%20a%20Large%20Scale%20Public%20Competition.pdf) — PDF，30 页；[原始来源](https://arxiv.org/abs/2507.20526)
- [Jailbreaking Black Box Large Language Models in Twenty Queries (PAIR)](references/11-Jailbreaking%20Black%20Box%20Large%20Language%20Models%20in%20Twenty%20Queries%20%28PAIR%29.pdf) — PDF，34 页；[原始来源](https://arxiv.org/abs/2310.08419)
- [Nemotron 3 Super technical report](references/12-Nemotron%203%20Super%20technical%20report.pdf) — PDF，51 页；[原始来源](https://research.nvidia.com/labs/nemotron/files/NVIDIA-Nemotron-3-Super-Technical-Report.pdf)
- [Docker Engine security](references/13-Docker%20Engine%20security.md) — 项目或网页说明与链接；[原始来源](https://docs.docker.com/engine/security/)
- [Modal sandbox networking and security](references/14-Modal%20sandbox%20networking%20and%20security.md) — 项目或网页说明与链接；[原始来源](https://modal.com/docs/guide/sandbox-networking)
- [OpenShell architecture (pinned revision)](references/15-OpenShell%20architecture%20%28pinned%20revision%29.md) — 项目或网页说明与链接；[原始来源](https://github.com/NVIDIA/OpenShell/blob/ec49209da25be39840742df29b64ec694d159c2f/docs/about/architecture.mdx)
- [Modal sandboxes](references/16-Modal%20sandboxes.md) — 项目或网页说明与链接；[原始来源](https://modal.com/docs/guide/sandboxes)
- [E2B sandbox persistence](references/17-E2B%20sandbox%20persistence.md) — 项目或网页说明与链接；[原始来源](https://docs.e2b.dev/sandbox/persistence)
- [Apptainer quick start](references/18-Apptainer%20quick%20start.md) — 项目或网页说明与链接；[原始来源](https://apptainer.org/docs/user/main/quick_start.html)
- [QEMU system emulation](references/19-QEMU%20system%20emulation.md) — 项目或网页说明与链接；[原始来源](https://www.qemu.org/docs/master/system/introduction.html)
- [E2B sandbox lifecycle](references/20-E2B%20sandbox%20lifecycle.md) — 项目或网页说明与链接；[原始来源](https://docs.e2b.dev/sandbox)
- [GitHub personal access tokens](references/21-GitHub%20personal%20access%20tokens.md) — 项目或网页说明与链接；[原始来源](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)
- [RFC 8693: OAuth 2.0 Token Exchange](references/22-RFC%208693%20-%20OAuth%202.0%20Token%20Exchange.md) — 项目或网页说明与链接；[原始来源](https://www.rfc-editor.org/rfc/rfc8693.html)
- [GitHub App installation access tokens](references/23-GitHub%20App%20installation%20access%20tokens.md) — 项目或网页说明与链接；[原始来源](https://docs.github.com/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)
- [AI Control: Improving Safety Despite Intentional Subversion](references/24-AI%20Control%20-%20Improving%20Safety%20Despite%20Intentional%20Subversion.pdf) — PDF，47 页；[原始来源](https://arxiv.org/abs/2312.06942v5)
- [OpenTelemetry generative AI attributes](references/25-OpenTelemetry%20generative%20AI%20attributes.md) — 项目或网页说明与链接；[原始来源](https://opentelemetry.io/docs/specs/semconv/registry/attributes/gen-ai/)
- [Docent](references/26-Docent.md) — 项目或网页说明与链接；[原始来源](https://transluce.org/docent)
- [Monitoring Reasoning Models for Misbehavior and the Risks of Promoting Obfuscation](references/27-Monitoring%20Reasoning%20Models%20for%20Misbehavior%20and%20the%20Risks%20of%20Promoting%20Obfuscation.pdf) — PDF，39 页；[原始来源](https://arxiv.org/abs/2503.11926)
- [AgentHarm](references/28-AgentHarm.pdf) — PDF，36 页；[原始来源](https://arxiv.org/abs/2410.09024)
- [OpenAgentSafety](references/29-OpenAgentSafety.pdf) — PDF，26 页；[原始来源](https://arxiv.org/abs/2507.06134v2)
- [Monitoring Monitorability](references/30-Monitoring%20Monitorability.pdf) — PDF，90 页；[原始来源](https://arxiv.org/abs/2512.18311)
