# LLM-LEARNING
## 注意力机制-网课学习
多头注意力机制
注意力机制原理
## 前馈神经网络
1.Transformer的前馈神经网络由两个线性层中间夹一个RELU激活层实现的，以及还加入了一个Dropout层来防止过拟合
## 归一化
1.归一化介绍：让不同层的输入的取值范围和分布大致相同
  例子：神经网络就像一条流水线，每道工序（每一层）的输出会变成下道工序的输入。如果不做归一化，前面工序的微小变化经过多层传递后，会让后面工序的 “原料”（输入数据）变得五花八门，和最初训练时的样子差太远，导致最后做出的 “产品”（预测结果）出错。
## 残差链接
由于 Transformer 模型结构较复杂、层数较深，​为了避免模型退化，Transformer 采用了残差连接的思想来连接每一个子层。残差连接，即下一层的输入不仅是上一层的输出，还包括上一层的输入。残差连接允许最底层信息直接传到最高层，让高层专注于残差的学习。
## encoder模块的组成
Encoder 由 N 个 Encoder Layer 组成，每一个 Encoder Layer 包括一个注意力层和一个前馈神经网络
## decoder模块的组成
类似的，我们也可以先搭建 Decoder Layer，再将 N 个 Decoder Layer 组装为 Decoder。但是和 Encoder 不同的是，Decoder 由两个注意力层和一个前馈神经网络组成。第一个注意力层是一个掩码自注意力层，即使用 Mask 的注意力计算，保证每一个 token 只能使用该 token 之前的注意力分数；第二个注意力层是一个多头注意力层，该层将使用第一个注意力层的输出作为 query，使用 Encoder 的输出作为 key 和 value，来计算注意力分数。最后，再经过前馈神经网络
## 代表性大语言模型
### 1.BERT
- BERT，全名为 Bidirectional Encoder Representations from Transformers，是由 Google 团队在 2018年发布的预训练语言模型。该模型发布于论文《BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding》，实现了包括 GLUE、MultiNLI 等七个自然语言处理评测任务的最优性能（State Of The Art，SOTA），堪称里程碑式的成果。
- 自 BERT 推出以来，预训练+微调的模式开始成为自然语言处理任务的主流，不仅 BERT 自身在不断更新迭代提升模型性能，也出现了如 MacBERT、BART 等基于 BERT 进行优化提升的模型。可以说，BERT 是自然语言处理的一个阶段性成果，标志着各种自然语言处理任务的重大进展以及预训练模型的统治地位建立，一直到 LLM 的诞生，NLP 领域的主导地位才从 BERT 系模型进行迁移。即使在 LLM 时代，要深入理解 LLM 与 NLP，BERT 也是无法绕过的一环。








