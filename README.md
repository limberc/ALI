# ALI的Tensorflow炼成与GAN科普

**Abstract：**Deep Learning是一个很大的领域，其中GAN是Deep Learning的明星，希望大家可以通过本文来简单的了解一下GAN这个模型以及这个模型的一些运用。本文介绍关于GAN的一些知识以及GAN的思想如何转移到ALI中，以及通过Google的Deep Learning框架`TensorFlow`，通过MNIST数据来实现ALI模型。所涉及到Tensorflow的一些很简单的一些解说，包括`tf.Variable()`和`tf.placeholder()`的一些用法以及区别，同时给出一小段代码案例。虽然提到了最简单的两个Tensorflow，`tf.Variable()`和`tf.placeholder()`，但是在本文中，不深入解释更多的关于TensorFlow的运用以及神经网络是如何搭建的。最后，我们将结果组合成模型。

-----------------

本文由[ALI Paper, arxiv](https://arxiv.org/abs/1606.00704)依照Tensorflow重现。ALI的概念非本人提出，本人根据自己对ALI的理解通过Tensorflow进行实现，并且运行于Jupyter中。所有代码在Windows10,Python3.5,TensorflowGPU版(1.1.0rc2)完美运行。限于本人水平，可能有出现一定的错误，如有失误，欢迎交流。同时，由于本人学习Deep Learning的时候直接接触英文材料，故一些专有名词的翻译可能存在一些偏差。故一些专有名词直接保留为原单词，不做翻译。ALI的翻译没有参考过任何相关中文信息，由本人直接查阅在Arxiv上ALI的原文所得。

如果有想来交流的小伙伴，欢迎私信。

-----------------
## Reference

1. [ALI Paper, arxiv](https://arxiv.org/abs/1606.00704)
* [GAN - Paper, NIPS](http://papers.nips.cc/paper/5423-generative-adversarial-nets.pdf)
* [GAN - Goodfellow](https://github.com/goodfeli/adversarial)
* [生成模型与判别模型 zouxy09,csdn](http://blog.csdn.net/zouxy09/article/details/8195017)
* [Adversarial machine learning - ACM Digital Library](https://dl.acm.org/citation.cfm?id=2046692)
* [Running Graph](https://www.tensorflow.org/api_guides/python/client)