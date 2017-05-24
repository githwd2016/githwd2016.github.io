---
layout: post
title: Word Embedding Evaluation
category: NLP
---
词向量的评价大体上可以分成两种方式，第一种是把词向量融入现有系统中，看对系统性能的提升；第二种是直接从语言学的角度对词向量进行分析，如相似度、语义偏移等。
1. 提升现有系统(任务相关（Task-specific）),最常见的有两种

　　	* 直接用于神经网络模型的输入层
	* 作为辅助特征扩充现有模型
2. 语言学评价

	* 将词向量的相似度与人工标注的相似度做比较
	* 类比（analogy）的方式来评测(Mikolov, 2013)
3. Reference

	* 可解释性 : [Evaluation of Word Vector Representations by Subspace Alignment](http://www.cs.cmu.edu/~ytsvetko/papers/qvec.pdf)
	* 指标: [Evaluation methods for unsupervised word embeddings](http://aclweb.org/anthology//D/D15/D15-1036.pdf)
	* [Don’t count, predict! A systematic comparison of context-counting vs. context-predicting semantic vectors](http://clic.cimec.unitn.it/marco/publications/acl2014/baroni-etal-countpredict-acl2014.pdf)
	* [Word representations :A simple and general method for semi-supervised learning](http://people.cs.pitt.edu/~huynv/research/deep-nets/Word%20representations%20a%20simple%20and%20general%20method%20for%20semi-supervised%20learning.pdf)
		将Word Representation分为三类，（1）Distributional Representation；（2）Clustering-based word representation；（3）Distributed Representation。

		Distributional Representation 是基于共现矩阵， 其中为词表大小， 为Context大小， 矩阵中每行为一个词的表示向量， 每一列为某些Context内容。 构造矩阵有许多的方案和技巧，比如context的构建（左边 or 右边的Context窗口内容， Context窗口大小等）。同时，基于现有的共现矩阵，可以采用一些降维方法压缩词的表示，比如LSA中的SVD + Low Rank Approximation等。

		Clustering-based word Representation是进行Distributional Representation中的共现矩阵“变换”成一个个聚类。 常见的模型有：brown clustering，HMM-LDA based POS and word segmentation等。

		Distributed Representation在Section 3.1中已经讲到， 现有的词向量表示都可以归到此类中， 这类模型到现在已经提出了好几十种， 主要是Feed Forward Neural Network based和Recurrent Neural Network based两大类。
	* [The Expressive Power of Word Embeddings](https://arxiv.org/pdf/1301.3226.pdf)
	* [How to Generate a Good Word Embedding?](https://arxiv.org/pdf/1507.05523.pdf)