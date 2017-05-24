---
layout: post
title: Word Embedding
category: NLP
---
1. A Neural Probabilistic Language Model

	三层的神经网络来构建语言模型，同样也是 n-gram 模型

2. Natural Language Processing (Almost) from Scratch

	论文主要目的并不是在于生成一份好的词向量，甚至不想训练语言模型，而是要用这份词向量去完成 NLP 里面的各种任务， 比如词性标注、命名实体识别、短语识别、语义角色标注等等。

	公布的词向量与其它词向量相比主要有两个区别：
    * 词表中只有小写单词。也就是说他把大写开头的单词和小写单词当作同一个词处理。其它的词向量都是把他们当作不同的词处理的。
    * 词向量并不直接是上述公式的优化结果，而是在此基础上进一步跑了词性标注、命名实体识别等等一系列任务的 Multi-Task Learning 之后，二次优化得到的。也可以理解为是半监督学习得到的，而非其他方法中纯无监督学习得到的。

3. Three new graphical models for statistical language modelling	

	一共提了 3 个模型。从最基本的 RBM 出发，一点点修改能量函数，最后得到了“Log-Bilinear”模型。
4. A scalable hierarchical distributed language model

	“hierarchical log-bilinear”模型,使用了一个层级的结构做最后的预测
5. Statistical Language Models based on Neural Networks

	用循环神经网络,真正充分地利用所有上文信息来预测下一个词，而不像前面的其它工作那样，只能开一个 n 个词的窗口，只用前 n 个词来预测下一个词。
6. Improving Word Representations via Global Context and Multiple Word Prototypes

	第一个创新是使用全文信息辅助已有的局部信息，第二个创新是使用多个词向量来表示多义词。
7. word2vec
8. glove
9. Conclusion & Renference

|名称|语料规模|词向量|特点|	资源|
|---|-------|-----|----|----|
|C&W|English Wikipedia + Reuters RCV1共 631M + 221M 词|130000 词 , 50 维|不区分大小写；经过有监督修正；训练了 7 周|[链接](http://ml.nec-labs.com/senna/)|
|C&W - Turian|Reuters RCV1 63M 词|268810 词 25、50、100、200 维|区分大小写；训练了若干周|[链接](http://metaoptimize.com/projects/wordreprs/)|
|M&H - Turian|Reuters RCV1|246122 词 50、100 维|区分大小写；用GPU训练了7天|[链接](http://metaoptimize.com/projects/wordreprs/)|
|Mikolov|Broadcast news|82390 词 80、640、1600 维	|不区分大小写；训练了若干天|[链接](http://www.fit.vutbr.cz/~imikolov/rnnlm/)|
|Huang 2012|English Wikipedia|100232 词 50 维|不区分大小写；最高频的6000词，每词有10种表示	|[链接](http://www.socher.org/index.php/Main/ImprovingWordRepresentationsViaGlobalContextAndMultipleWordPrototypes)|

这么多模型，本质是非常相似的。都是从前若干个词的词向量通过线性变换抽象出一个新的语义（隐藏层），再通过不同的方法来解析这个隐藏层。模型的差别主要就在隐藏层到输出层的语义。Bengio 2003 使用了最朴素的线性变换，直接从隐藏层映射到每个词；C&W 简化了模型（不求语言模型），通过线性变换将隐藏层转换成一个打分；M&H 复用了词向量，进一步强化了语义，并用层级结构加速；Mikolov 则用了分组来加速。

Holger Schwenk 在词向量和语言模型方面也做了一些工作。