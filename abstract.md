# CSDNWRITERS
* [paper summary](https://www.jianshu.com/p/e73851f32c9f)  
* [csdn writer](https://blog.csdn.net/yingpeng_zhong?t=1)  
  * （笔记）细颗粒度的三值网络Ternary Neural Networks with Fine-Grained Quantization
  * （笔记）网络压缩量化，训练三值量化TRAINED TERNARY QUANTIZATION
  * （笔记）通过知识蒸馏和量化进行模型压缩MODEL COMPRESSION VIA DISTILLATION AND QUANTIZATION
    * 有一个浮点模型 *w*，一个量化模型 *w^q* ，用 *量化模型* 计算前向loss（加上知识蒸馏的loss），*对w^q计算梯度*，用以 *更新浮点模型*。每次前向计算之前用更新的浮点模型更新量化模型。
    * *teacher* quantized and *student* unquantized
  * （笔记）神经网络压缩，Ristretto: Hardware-Oriented Approximation of Convolutional Neural Networks（一）
* [综述作者](https://blog.csdn.net/wspba)  
  * 论文笔记：ThiNet——一种filter级的模型裁剪算法
  * 论文笔记：DeepRebirth——从非权重层入手来进行模型压缩
    * 本文却另辟蹊径，从非权重层入手来进行模型压缩。
    * 如ResNet、GoogLenet等的卷积层都是由很小的卷积核组成，本身就非常紧致了，并且也去掉了非常占参数量的全连接层。而Non-tensor layer（也就是非权重层，如pooling、BN、LRN、ReLU等等）反而成为了模型在cpu以及其他嵌入式硬件上达到real-time的最大阻碍
    * *streamline*
      * 将这一连串的层合并起来(Non-Tensor层（Pooling、LRN）),对于Pooling层，将stride直接乘到Conv层中
    * *branch merging*
      * 主要针对GoogLeNet中的Inception结构
      * 作者将比较细小的卷积层（1*1）以及Pooling层所在的分支，直接合并到和它并排的大卷积分支中
    * 对于一个预训练模型，作者逐层进行合并，合并得到的 *新层* 使用 *标准的初始化方式* ，*其他层的参数保留原预训练模型的参数*，然后将新层的学习率调高为其他层的10倍，进行finetuning，对于某些层，如GoogLenet中的Inception 4b-4d可以一起进行合并在finetuning。
  * 深度学习模型压缩方法综述（1-3）
  * residual
* [压缩神经网络实验及简直策略等](https://blog.csdn.net/jason19966)  
  * 压缩神经网络（四）：Deep Compression（附加问题）
  * 压缩神经网络 实验记录（剪枝 + rebirth + mobilenet）
  * 压缩神经网格（三）：MobileNets
  * 压缩神经网络（一）：剪枝的基本思想
  * 压缩神经网格（二）：融合分支的思想
* [several paper](https://blog.csdn.net/cookie_234?t=1)  
  * Incremental Network Quantization: Towards Lossless CNNs with Low-precision Weights
  * *Soft weight-sharing for neural network compression*

  * Exploring the Regularity of Sparse Structure in Convolutional Neural Networks
  * Learning both Weights and Connections for Efficient Neural Networks
  * Do Deep Nets Really Need to be Deep?
  * caffe 解读
* [地大大](https://blog.csdn.net/liujianlin01)  
  * 挺多的
  * Fixed-Point Performance Analysis of Recurrent Neural Networks
  * 【Quantized Convolutional Neural Networks for Mobile Devices】论文笔记
# ARTICLES
* [机器之心总结](https://www.jiqizhixin.com/articles/2018-06-01-11)  
  * Quantization
    * deep compression最后参数会变成一个稀疏的矩阵，作者自己提出了一种编码方式
    * 量化其实是一种权值共享的策略
    * 因为梯度很小，所以使用无法使用低精度来正确表达梯度，同时梯度是有高斯白噪声的，累加梯度才能抵消噪声
    * 二值化相当于给权重和输出值添加了噪声，而这样的噪声具有正则化作用，可以防止模型过拟合,二值化也可以被看做是 Dropout 的一种变形
    * Xnor-Net 在 BNN 的基础上引入了比例因子
    * ternary-net 权值的分布接近于一个正态分布和一个均匀分布的组合,使用一个 scale 参数去最小化三值化前的权值和三值化之后的权值的 L2 距离。
    * 当然，这种方法有进化版本，我们完全可以将权值组合变成（-2，-1，0，1，2）的组合，以期获得更高的准确率。
    * 权值三值化并没有完全消除乘法器
    * *DoReLa-Net*<sub>detailed</sub> 对卷积层的整体输出计算一个均值常量作为比例因子
  * *目前的高精度压缩算法只适合于传统的有很多冗余的网络*
  * [hardware](http://www.rle.mit.edu/eems/wp-content/uploads/2017/11/2017_pieee_dnn.pdf)
  * 硬件加速神经网络前向运算的最主要的任务就是完成卷积优化，减少卷积运算的资源和能源消耗非常核心
  * main idea of optimize convolution
    * 内存换取时间,一次加载图片，产生多次的数据，而不需要多次访问图片，这就是用内存来换时间
    * 乘法优化,我们可以把卷积核心展开成一条行，然后多个卷积核就可以排列成多行，再把图像也用类似的方法展开，就可以把一个卷积问题转换成乘法问题。这样就是一行乘以一列，就是一个结果了。这样虽然多做了一些展开的操作，但是对于计算来讲，速度会提升很多。
    * GPU
    * strassen algorithm,分析 CNN 的线性代数特性，增加加法减少乘法，这样降低了卷积运算的计算的复杂度
* [模型压缩论文及其相关](https://www.jishux.com/p/4007c8b22f2c7083)  
  * 深度神经网络的量化技术可主要分为两类：完整训练后量化和训练时量化
    * 量化类的方法属于改变网络多样性的方法，容易造成精度损失
    * 完整训练后量化
    * 训练时量化
  * *some about quantization*
* [SigAI-卷积神经网络的压缩和加速](https://mp.weixin.qq.com/s?__biz=MzU4MjQ3MDkwNA==&mid=2247485042&idx=1&sn=cdcf8d4b07acf64c7a6f5f7c1a731a12&chksm=fdb69be5cac112f377766984afb87313c1e1c58d94c80005f0f6f6af61ee5a4bd1bf6c6157b6&token=1065243837&lang=zh_CN#rd)
  * pruning
    * 删掉一个filter，相应的输出特征图将少一个通道 *filter-level*
    * 将3*3的kernel删成某个固定的形状 *group-level pruning*
    * 不急着删去参数，而是将那些没用的参数设为0，于是矩阵的乘法可以用稀疏矩阵的乘法来代替 *Fine-grained，vector-level，kernel-level*
  * low-rank
    * 用若干小矩阵对参数矩阵进行估计,没有改变基础运算的结构，不需要额外定义新的操作,低秩估计方法存在一个待解决的问题，就是保留多少秩是不明确的
      * 保留太多的秩可以保证准确率，但加速压缩效果不好
      * 保留秩太少，加速压缩效果好
    * 直接对张量进行分解，而且卷积也符合结合律
  * Quantization
    * 移动端和嵌入式设别的CPU处理整数的计算速度要快于浮点数
    * Tensorflow给出了定点化的Op操作
  * Distillation
    * 直接设计了一个简单结构的小网络
    * 模型蒸馏方法仍有很大的研究空间
  * *related articles*
* [github巨全的一个总结](https://github.com/Ewenwan/MVision/tree/85c37ba2df091570510d5240ea2f698b75e3fbb6/CNN/Deep_Compression)
  * Pruning
    * 基于量级的裁剪方式（用weight值的大小来评判其重要性）
    * [统计filter中激活为0的值的数量作为标准](https://arxiv.org/pdf/1607.03250.pdf)
    * [基于熵值的剪裁](https://arxiv.org/pdf/1706.05791.pdf)
    * [基于能量效率的裁剪方式](https://arxiv.org/pdf/1611.05128.pdf)
    * 遗传算法思想,随机剪裁，选择效果好的
    * 基于icc组内相关来衡量filter的重要性
    * 基于神经元激活相关性的重要性判别方法
    * 将裁剪问题当做一个组合优化问题
    * 一种基于Hessian矩阵的网络修剪算法
  * Quantization
    * Weights
    * feature map
    * gradient
* [Model-Compression-Papers](https://github.com/chester256/Model-Compression-Papers)
# PRUNING
* [Soft Weight-Sharing for Neural Network Compression ](http://cn.arxiv.org/abs/1702.04008)
* [Channel Pruning for Accelerating Very Deep Neural Networks](https://arxiv.org/abs/1707.06168)
* [Deep Compression: Compressing Deep Neural Networks with Pruning, Trained Quantization and Huffman Coding](https://arxiv.org/abs/1510.00149)
* [MODEL COMPRESSION WITH GENERATIVE ADVERSARIAL NETWORKS](https://openreview.net/forum?id=Byxz4n09tQ)
* [Dynamic Network Surgery for Efficient DNNs](https://arxiv.org/abs/1608.04493)
  * 文章主要提出可以恢复的剪
    * 传统剪枝会删除重要的连接而且周期长
  * 用mask来代表状态，每轮利用mask后的参数计算出的loss更新参数
  * 再用过更新后的权重导数更新mask(a<sub>k</sub>和b<sub></sub>)
  * 为了加速训练减少删除连接的概率避免难收敛卷积层和全连接层分层剪枝
* [To prune, or not to prune: exploring the efficacy of pruning for model compression](http://cn.arxiv.org/abs/1710.01878)
* [Learning both Weights and Connections for Efficient Neural Networks](http://cn.arxiv.org/abs/1506.02626)
* [Sensitivity Based Network Pruning: A Modern Perspective](http://users.cecs.anu.edu.au/~Tom.Gedeon/conf/ABCs2018/paper/ABCs2018_paper_135.pdf)
  * 定义了一个在反向传播时计算神经元连接敏感度的公式
  * 通过累计在反向时偏导对权重的误差
* [A pruning based method to learn both weights and connections for LSTM](https://nlp.stanford.edu/courses/cs224n/2015/reports/2.pdf)
  * 剪枝完重训练
  * 按照权重绝对值
* [Second order derivatives for network pruning: Optimal Brain Surgeon](https://papers.nips.cc/paper/647-second-order-derivatives-for-network-pruning-optimal-brain-surgeon.pdf)
  * 待看，求二阶偏导作为重要是否的标准
# QUANTIZATION
  ## binarization
  * [binary neural network](https://arxiv.org/abs/1602.02830)
  * [XNOR-net](https://arxiv.org/abs/1603.05279)
  * [HORQ-net](https://arxiv.org/abs/1708.08687)
  * [ternary neural network](https://arxiv.org/abs/1705.01462)
  * [DeRefa-net](https://arxiv.org/abs/1606.06160)
  * [YodaNN](https://arxiv.org/abs/1606.05487)
  * [BinaryRelax- A Relaxation Approach For Training Deep Neural Networks With Quantized Weights](http://cn.arxiv.org/abs/1801.06313)
  ## fixed-point quantization
  * [fixed-point factorized network](https://arxiv.org/abs/1611.01972)
  * [Scalable Methods for 8-bit Training of Neural Networks](https://arxiv.org/abs/1805.11046)
    * 待复现
  * [Extremely Low Bit Neural Network: Squeeze the Last Bit Out with ADMM](https://arxiv.org/abs/1707.09870)
    * 待复现
  ## quantization method
  * [incremental network quantization](https://arxiv.org/abs/1702.03044)
  * [Hashed-Net](https://arxiv.org/abs/1702.00758)
  * [Quantized Convolutional Neural Networks for Mobile Devices](https://arxiv.org/abs/1512.06473)
  ## quantization article
  *  [summary](https://blog.csdn.net/u012101561/article/details/80868352?utm_source=blogxgwz34)
# NET
* [GoogLeNet](https://www.cs.unc.edu/~wliu/papers/GoogLeNet.pdf)
* [SqueezeNet](https://arxiv.org/abs/1602.07360)
* [MobileNets](https://arxiv.org/abs/1704.04861)
* [ShuffleNet](https://arxiv.org/abs/1707.01083)
