# Lec8 · Training 1: Supervised Fine-Tuning (SFT)

- 日期：Thu, Sep 17（官网 Fall 2026 课表）
- 课表编号：4b
- 模块：Training Methods
- 整理日期：2026-10-27
- 来源：[CMU 11-768 课程日程](https://www.cmu-agents.com/#/schedule)
- 讲师：[Yueqi Song](https://yueqis.github.io/)
- 录像：[Lecture 8 recording](https://www.youtube.com/watch?v=O3HSU0AoILc&list=PLSN0qpDfUvTM&index=8)

## Slides

- [Lecture 8 slides](slides/Lec8-Slides.pdf) — PDF，49 页；[原始来源](https://www.cmu-agents.com/slides/lecture-08-sft.pdf)

## References · 官网补充参考

- [Kimi K3](references/01-Kimi%20K3.pdf) — PDF，47 页；[原始来源](https://arxiv.org/abs/2607.24653)
- [DeepSeek-R1](references/02-DeepSeek-R1.pdf) — PDF，86 页；[原始来源](https://arxiv.org/abs/2501.12948)
- [Nemotron 3 Ultra](references/03-Nemotron%203%20Ultra.pdf) — PDF，65 页；[原始来源](https://research.nvidia.com/labs/nemotron/files/NVIDIA-Nemotron-3-Ultra-Technical-Report.pdf)
- [MAI-Thinking-1](references/04-MAI-Thinking-1.pdf) — PDF，109 页；[原始来源](https://microsoft.ai/pdf/mai-thinking-1.pdf)
- [K2 Horizon model card](references/05-K2%20Horizon%20model%20card.md) — 项目或网页说明与链接；[原始来源](https://huggingface.co/IFM/K2-Horizon-375B-A23B)
- [Kimi K2](references/06-Kimi%20K2.pdf) — PDF，32 页；[原始来源](https://arxiv.org/abs/2507.20534)
- [OpenThoughts-Agent](references/07-OpenThoughts-Agent.pdf) — PDF，36 页；[原始来源](https://arxiv.org/abs/2606.24855)
- [SWE-Gym](references/08-SWE-Gym.pdf) — PDF，21 页；[原始来源](https://arxiv.org/abs/2412.21139)
- [Agent Data Protocol](references/09-Agent%20Data%20Protocol.pdf) — PDF，21 页；[原始来源](https://arxiv.org/abs/2510.24702)
- [BalanceSFT](references/10-BalanceSFT.pdf) — PDF，18 页；[原始来源](https://arxiv.org/abs/2505.20192)
- [Instruction Modelling](references/11-Instruction%20Modelling.pdf) — PDF，24 页；[原始来源](https://arxiv.org/abs/2405.14394)
- [Weighted Instruction Tuning](references/12-Weighted%20Instruction%20Tuning.pdf) — PDF，20 页；[原始来源](https://arxiv.org/abs/2507.07817)
- [DAgger](references/13-DAgger.pdf) — PDF，9 页；[原始来源](https://proceedings.mlr.press/v15/ross11a.html)
- [Transformers: chat templates](references/14-Transformers%20-%20chat%20templates.md) — 项目或网页说明与链接；[原始来源](https://huggingface.co/docs/transformers/en/chat_templating)
- [Transformers: apply_chat_template](references/15-Transformers%20-%20apply_chat_template.md) — 项目或网页说明与链接；[原始来源](https://huggingface.co/docs/transformers/en/main_classes/tokenizer)
- [TRL: SFTTrainer](references/16-TRL%20-%20SFTTrainer.md) — 项目或网页说明与链接；[原始来源](https://huggingface.co/docs/trl/en/sft_trainer)
- [TRL: training chat templates](references/17-TRL%20-%20training%20chat%20templates.md) — 项目或网页说明与链接；[原始来源](https://huggingface.co/docs/trl/en/chat_templates)
- [Axolotl: conversation datasets](references/18-Axolotl%20-%20conversation%20datasets.md) — 项目或网页说明与链接；[原始来源](https://docs.axolotl.ai/docs/dataset-formats/conversation.html)
- [LLaMA-Factory](references/19-LLaMA-Factory.md) — 项目或网页说明与链接；[原始来源](https://github.com/hiyouga/LLaMA-Factory)
