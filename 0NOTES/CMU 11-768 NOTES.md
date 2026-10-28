# CMU 11-768 NOTES

## Lec1 What're Agents & How do they work?

### 如何定义一个Agent

<img src="assets/image-20261028200039877.png" alt="image-20261028200039877" style="zoom:50%;" />

**Environment + State + Actions + Reward**

让我们再 recap 一下LanguageModels：

<img src="assets/image-20261028200426696.png" alt="image-20261028200426696" style="zoom:40%;" />

ToolCalling:

<img src="assets/image-20261028200955979.png" alt="image-20261028200955979" style="zoom:50%;" />

从LLMs 到Agents——

<img src="assets/image-20261028201622200.png" alt="image-20261028201622200" style="zoom:50%;" />

**Model in the loop**

![image-20261028202102477](assets/image-20261028202102477.png)

<img src="assets/image-20261028202054613.png" alt="image-20261028202054613" style="zoom:50%;" />

### Agent capabilities

What Makes An Agent Good?

<img src="assets/image-20261028203032880.png" alt="image-20261028203032880" style="zoom:50%;" />

两种方法来 build 出我们想要的 Agents：模型本身的能力或者外层的Harness

**LLMTrainning or HarnessEngineering**

现在很多情况，或者说业界的一个通用点是：很多时候，模型能力的提升也足够完善相当多的Harness。当然，这两者肯定是同样重要的。

<img src="assets/image-20261028204653178.png" alt="image-20261028204653178" style="zoom:50%;" />

Agents的训练：

<img src="assets/image-20261028204901498.png" alt="image-20261028204901498" style="zoom:50%;" />

预训练跟我们无关，毕竟现在的模型参数都是 billion 起步，太多啦～
中期训练/监督微调(SFT) & 强化学习(RL) 会是我们比较关注的点。



#### 六个Agents能力进行拆解

**（1）准确的工具调用**

<img src="assets/image-20261028205241326.png" alt="image-20261028205241326" style="zoom:50%;" />

**（2）长上下文的连贯性**

<img src="assets/image-20261028205249117.png" alt="image-20261028205249117" style="zoom:50%;" />

**（3）定制性**

<img src="assets/image-20261028205346278.png" alt="image-20261028205346278" style="zoom:50%;" />

**（4）复杂任务管理**

<img src="assets/image-20261028205359701.png" alt="image-20261028205359701" style="zoom:50%;" />

**（5）环境理解**

<img src="assets/image-20261028205416304.png" alt="image-20261028205416304" style="zoom:50%;" />

**（6）安全性**

<img src="assets/image-20261028205427958.png" alt="image-20261028205427958" style="zoom:50%;" />



### AgentEngineering

Agents是系统，而不只是模型

<img src="assets/image-20261028210247041.png" alt="image-20261028210247041" style="zoom:50%;" />

<img src="assets/image-20261028210533143.png" alt="image-20261028210533143" style="zoom:50%;" />

诸如 LangChain 这样的Orchestrators现在已经不怎么提了，复杂度较低，只能查查数据，而写不出真实的程序。

<img src="assets/image-20261028210852502.png" alt="image-20261028210852502" style="zoom:50%;" />

<img src="assets/image-20261028211022126.png" alt="image-20261028211022126" style="zoom:50%;" />

<img src="assets/image-20261028211056249.png" alt="image-20261028211056249" style="zoom:50%;" />

<img src="assets/image-20261028211104443.png" alt="image-20261028211104443" style="zoom:50%;" />

