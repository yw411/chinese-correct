# 关于中文纠错,感觉比较好的论文

## 1、PLOME: Pre-training with Misspelled Knowledge for Chinese Spelling Correction. ACL 2021.
1.1 加入字形和拼音信息，感觉很重要。此文使用的是gru产生相关的向量。

1.2 mask时使用了混淆集。当错字和正确的字之间存在的关系更加紧密时，我们有更加高的信心预测出正确的字。若不相关，其实是否要预测成这个字，是心里没底的。

1.3 字错了几个，但是拼音没有错误的时候，使用拼音上下文进行预测。

比如: 是神灵->侍神令，谷雪无名川->浴血无名川，权和小姐->劝和小组，
此时拼音可以起作用。同理，形近亦如此。


## 1.1、引申论文：SpellGCN: Incorporating Phonological and Visual Similarities into Language Models for Chinese Spelling Check
1.1 同样是加入拼音和形近信息。使用gcn加入邻居信息。若字之间存在同音或者形近关系，则边的取值为1，否则为0。

1.2 使用：最后一层的bert输出v和gcn的输出w做点乘，计算相关性。即一个字的上下文和这个字的字形拼音计算相关性。(感觉不如1的方法更直观,上下文的字形拼音信息没有捕捉到)。

## 2 Spelling Error Correction with Soft-Masked BERT
2.1 疑问：偏向mask编码和偏向词本身的编码为什么会影响结果？字错了，用mask编码，否则用本身的编码，有什么区别呢？不是很懂。



