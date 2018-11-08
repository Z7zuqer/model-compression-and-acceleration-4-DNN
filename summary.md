# CSDNWRITERS
* [paper summary](https://www.jianshu.com/p/e73851f32c9f)  
* [csdn writer](https://blog.csdn.net/yingpeng_zhong?t=1)  
* [综述作者](https://blog.csdn.net/wspba)  
* [压缩神经网络实验及简直策略等](https://blog.csdn.net/jason19966)  
* [several paper](https://blog.csdn.net/cookie_234?t=1)  
* [地大大](https://blog.csdn.net/liujianlin01)  
# ARTICLES
* [合集](https://www.jiqizhixin.com/articles/2018-06-01-11)  
* [模型压缩论文及其相关](https://www.jishux.com/p/4007c8b22f2c7083)  
* [神经网络模型压缩与加速的常见方法](https://blog.csdn.net/LiJiancheng0614/article/details/79478792?utm_source=blogxgwz1)  
* [prune和网络剪枝](https://blog.csdn.net/SIGAI_CSDN/article/details/80803956?utm_source=blogxgwz8)  
* [github summary](https://github.com/Ewenwan/MVision/tree/master/CNN/Deep_Compression/quantization)
# PRUNING
* [Soft Weight-Sharing for Neural Network Compression ](http://cn.arxiv.org/abs/1702.04008)
* [Channel Pruning for Accelerating Very Deep Neural Networks](https://arxiv.org/abs/1707.06168)
* [Deep Compression: Compressing Deep Neural Networks with Pruning, Trained Quantization and Huffman Coding](https://arxiv.org/abs/1510.00149)
* [MODEL COMPRESSION WITH GENERATIVE ADVERSARIAL NETWORKS](https://openreview.net/forum?id=Byxz4n09tQ)
* [Dynamic Network Surgery for Efficient DNNs](https://arxiv.org/abs/1608.04493)
  * 文章主要提出可以恢复的剪枝
    * 传统剪枝会删除重要的连接而且周期长
  * 用mask来代表状态，每轮利用mask后的参数计算出的loss更新参数
  * 再通过更新后的权值更新mask(a<sub>k</sub>和b<sub></sub>)
  * 为了加速训练作者1：减少删除连接的概率避免难收敛2：卷积层和全连接层分开剪枝
* [To prune, or not to prune: exploring the efficacy of pruning for model compression](http://cn.arxiv.org/abs/1710.01878)
* [Learning both Weights and Connections for Efficient Neural Networks](http://cn.arxiv.org/abs/1506.02626)
* [Sensitivity Based Network Pruning: A Modern Perspective](http://users.cecs.anu.edu.au/~Tom.Gedeon/conf/ABCs2018/paper/ABCs2018_paper_135.pdf)
  * 定义了一个在反向传播时计算神经元连接敏感度的公式
  * 通过累计在反向时偏导对权重的误差
* [A pruning based method to learn both weights and connections for LSTM](https://nlp.stanford.edu/courses/cs224n/2015/reports/2.pdf)
  * 剪枝完重训练
  * 按照权值绝对值大小剪枝
* [Second order derivatives for network pruning: Optimal Brain Surgeon](https://papers.nips.cc/paper/647-second-order-derivatives-for-network-pruning-optimal-brain-surgeon.pdf)
  * 待看，求二阶偏导作为重要性
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
  ## quantization method
  * [incremental network quantization](https://arxiv.org/abs/1702.03044)
  * [Hashed-Net](https://arxiv.org/abs/1702.00758)
  * [Quantized Convolutional Neural Networks for Mobile Devices](https://arxiv.org/abs/1512.06473)
  ## quantization article
  * [summary](https://blog.csdn.net/u012101561/article/details/80868352?utm_source=blogxgwz34)
# NET
* [GoogLeNet](https://www.cs.unc.edu/~wliu/papers/GoogLeNet.pdf)
* [SqueezeNet](https://arxiv.org/abs/1602.07360)
* [MobileNets](https://arxiv.org/abs/1704.04861)
* [ShuffleNet](https://arxiv.org/abs/1707.01083)
