# Lec3 · Agent Capabilities 2: Context Management for Long-Context Agents

- 日期：Tue, Sep 1（官网 Fall 2026 课表）
- 课表编号：2a
- 模块：Introduction and Agent Capabilities
- 整理日期：2026-10-27
- 来源：[CMU 11-768 课程日程](https://www.cmu-agents.com/#/schedule)
- 录像：[Lecture 3 recording](https://www.youtube.com/watch?v=AiwCCvFW1uE&list=PLSN0qpDfUvTM&index=3)

## Slides

- [Lecture 3 slides](slides/Lec3-Slides.pdf) — PDF，54 页；[原始来源](https://www.cmu-agents.com/slides/lecture-03-long-context.pdf)

## References · 官网补充参考

- [DistServe](references/01-DistServe.pdf) — PDF，18 页；[原始来源](https://arxiv.org/abs/2401.09670)
- [Needle in a Haystack](references/02-Needle%20in%20a%20Haystack.md) — 项目或网页说明与链接；[原始来源](https://github.com/gkamradt/LLMTest_NeedleInAHaystack)
- [Attention Is All You Need](references/03-Attention%20Is%20All%20You%20Need.pdf) — PDF，15 页；[原始来源](https://arxiv.org/abs/1706.03762)
- [Longformer](references/04-Longformer.pdf) — PDF，17 页；[原始来源](https://arxiv.org/abs/2004.05150)
- [Transformers are RNNs](references/05-Transformers%20are%20RNNs.pdf) — PDF，17 页；[原始来源](https://arxiv.org/abs/2006.16236)
- [Linear Transformers Are Secretly Fast Weight Programmers](references/06-Linear%20Transformers%20Are%20Secretly%20Fast%20Weight%20Programmers.pdf) — PDF，16 页；[原始来源](https://arxiv.org/abs/2102.11174)
- [Gated Delta Networks](references/07-Gated%20Delta%20Networks.pdf) — PDF，22 页；[原始来源](https://arxiv.org/abs/2412.06464)
- [Kimi Linear](references/08-Kimi%20Linear.pdf) — PDF，28 页；[原始来源](https://arxiv.org/abs/2510.26692)
- [DeepSeek Sparse Attention](references/09-DeepSeek%20Sparse%20Attention.pdf) — PDF，23 页；[原始来源](https://arxiv.org/abs/2512.02556)
- [Grouped-Query Attention](references/10-Grouped-Query%20Attention.pdf) — PDF，7 页；[原始来源](https://arxiv.org/abs/2305.13245)
- [DeepSeek-V2](references/11-DeepSeek-V2.pdf) — PDF，52 页；[原始来源](https://arxiv.org/abs/2405.04434)
- [RoFormer](references/12-RoFormer.pdf) — PDF，14 页；[原始来源](https://arxiv.org/abs/2104.09864)
- [NoPE Length Generalization](references/13-NoPE%20Length%20Generalization.pdf) — PDF，37 页；[原始来源](https://arxiv.org/abs/2305.19466)
- [Position Interpolation](references/14-Position%20Interpolation.pdf) — PDF，18 页；[原始来源](https://arxiv.org/abs/2306.15595)
- [YaRN](references/15-YaRN.pdf) — PDF，20 页；[原始来源](https://arxiv.org/abs/2309.00071)
- [Qwen3.8-Flash-Next](references/16-Qwen3.8-Flash-Next.md) — 项目或网页说明与链接；[原始来源](https://qwen.ai/blog?id=qwen3.8-flash-next)
- [GLM-5](references/17-GLM-5.pdf) — PDF，40 页；[原始来源](https://arxiv.org/abs/2602.15763)
- [GLM-5.3-Flash](references/18-GLM-5.3-Flash.md) — 项目或网页说明与链接；[原始来源](https://huggingface.co/zai-org/GLM-5.3-Flash)
- [Kimi K3](references/19-Kimi%20K3.pdf) — PDF，47 页；[原始来源](https://arxiv.org/abs/2607.24653)
- [Nemotron 3 Ultra](references/20-Nemotron%203%20Ultra.pdf) — PDF，65 页；[原始来源](https://research.nvidia.com/labs/nemotron/files/NVIDIA-Nemotron-3-Ultra-Technical-Report.pdf)
- [Inkling](references/21-Inkling.md) — 项目或网页说明与链接；[原始来源](https://thinkingmachines.ai/news/introducing-inkling/)
- [DeepSeek V4](references/22-DeepSeek%20V4.pdf) — PDF，58 页；[原始来源](https://arxiv.org/abs/2606.19348)
- [Ring Attention](references/23-Ring%20Attention.pdf) — PDF，16 页；[原始来源](https://arxiv.org/abs/2310.01889)
- [Megatron Context Parallelism](references/24-Megatron%20Context%20Parallelism.md) — 项目或网页说明与链接；[原始来源](https://docs.nvidia.com/megatron-core/developer-guide/latest/user-guide/features/context_parallel.html)
- [Prompt Cache](references/25-Prompt%20Cache.pdf) — PDF，14 页；[原始来源](https://arxiv.org/abs/2311.04934)
- [Can I Buy Your KV Cache?](references/26-Can%20I%20Buy%20Your%20KV%20Cache.pdf) — PDF，8 页；[原始来源](https://arxiv.org/abs/2606.13361)
- [DeepSeek API Pricing](references/27-DeepSeek%20API%20Pricing.md) — 项目或网页说明与链接；[原始来源](https://api-docs.deepseek.com/quick_start/pricing/)
- [Z.AI API Pricing](references/28-Z.AI%20API%20Pricing.md) — 项目或网页说明与链接；[原始来源](https://docs.z.ai/guides/overview/pricing)
- [Kimi K3 Pricing](references/29-Kimi%20K3%20Pricing.md) — 项目或网页说明与链接；[原始来源](https://www.kimi.ai/resources/kimi-k3-pricing)
- [OpenAI Model Pricing](references/30-OpenAI%20Model%20Pricing.md) — 项目或网页说明与链接；[原始来源](https://developers.openai.com/api/docs/models/compare)
- [Anthropic Prompt Caching](references/31-Anthropic%20Prompt%20Caching.md) — 项目或网页说明与链接；[原始来源](https://platform.claude.com/docs/en/build-with-claude/prompt-caching)
- [PagedAttention / vLLM](references/32-PagedAttention%20-%20vLLM.pdf) — PDF，16 页；[原始来源](https://arxiv.org/abs/2309.06180)
- [SGLang / RadixAttention](references/33-SGLang%20-%20RadixAttention.pdf) — PDF，20 页；[原始来源](https://arxiv.org/abs/2312.07104)
- [SGLang Cache-Aware Load Balancing](references/34-SGLang%20Cache-Aware%20Load%20Balancing.md) — 项目或网页说明与链接；[原始来源](https://lmsys.org/blog/2024-12-04-sglang-v0-4/)
- [MemGPT](references/35-MemGPT.pdf) — PDF，13 页；[原始来源](https://arxiv.org/abs/2310.08560)
- [LongLLMLingua](references/36-LongLLMLingua.pdf) — PDF，20 页；[原始来源](https://aclanthology.org/2024.acl-long.91/)
- [Codex](references/37-Codex.md) — 项目或网页说明与链接；[原始来源](https://github.com/openai/codex)
- [OpenCode](references/38-OpenCode.md) — 项目或网页说明与链接；[原始来源](https://github.com/anomalyco/opencode)
- [Pi](references/39-Pi.md) — 项目或网页说明与链接；[原始来源](https://github.com/badlogic/pi-mono)
- [Hermes Agent](references/40-Hermes%20Agent.md) — 项目或网页说明与链接；[原始来源](https://github.com/NousResearch/hermes-agent)
- [OpenHands](references/41-OpenHands.md) — 项目或网页说明与链接；[原始来源](https://github.com/All-Hands-AI/OpenHands)
- [ReSum](references/42-ReSum.pdf) — PDF，29 页；[原始来源](https://arxiv.org/abs/2509.13313)
