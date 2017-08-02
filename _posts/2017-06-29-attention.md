---
layout: post
title: Attention
category: NLP
---
Attention模型最初应用于图像识别，模仿人看图像时，目光的焦点在不同的物体上移动。当神经网络对图像或语言进行识别时，每次集中于部分特征上，识别更加准确。如何衡量特征的重要性呢？最直观的方法就是权重，因此，Attention模型的结果就是在每次识别时，首先计算每个特征的权值，然后对特征进行加权求和，权值越大，该特征对当前识别的贡献就大。
## 以机器翻译为例，Encoder-Decoder结构
Attention在Encoder-Decoder中介于Encoder和Decoder中间，首先根据Encoder和Decoder的特征计算权值，然后对Encoder的特征进行加权求和，作为Decoder的输入，其作用是将Encoder的特征以更好的方式呈献给Decoder。(1)首次将Attention模型应用到机器翻译中。


 
(1)[Bahdanau, D., Cho, K., & Bengio, Y. (2014). Neural machine translation by jointly learning to align and translate. arXiv preprint arXiv:1409.0473.](https://arxiv.org/abs/1409.0473) 
