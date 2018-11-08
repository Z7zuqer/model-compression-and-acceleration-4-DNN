# pruning
* [PRUNING IN TRAINING: LEARNING AND RANKING SPARSE CONNECTIONS IN DEEP CONVOLUTIONAL NETWORKS ](https://openreview.net/forum?id=r1GgDj0cKX)
* [Cumulative Saliency based Globally Balanced Filter Pruning For Efficient Convolutional Neural Networks ](https://openreview.net/forum?id=H1fevoAcKX)
* [PRUNING WITH HINTS: AN EFFICIENT FRAMEWORK FOR MODEL ACCELERATION](https://openreview.net/forum?id=Hyffti0ctQ)
* [SNIP: SINGLE-SHOT NETWORK PRUNING BASED ON CONNECTION SENSITIVITY](https://openreview.net/forum?id=B1VZqjAcYX)
  * 文章大致还是提出一个剪枝标准，单考虑更新时的梯度，公式是用误差函数对 C<sub>mask</sub>求偏导（为了减少权值对连接重要性的影响）
  * 整个网络所有参数放在一起选取topK
  * 饱和的激活函数会导致梯度信息不明，所以应该选取敏感的激活函数
  * 推荐variance scaling方法去初始化权重使得整个网络variance保持不变
  * 单batch训练剪枝效果最好
    * 选取剪枝的标准
    * 对剪枝加一个penalty
* [Progressive Weight Pruning Of Deep Neural Networks Using ADMM](https://openreview.net/forum?id=rygo9iR9F7)
* [Integral Pruning on Activations and Weights for Efficient Neural Networks](https://openreview.net/forum?id=HyevnsCqtQ)
* [Dynamic Channel Pruning: Feature Boosting and Suppression ](https://openreview.net/forum?id=BJxh2j0qYm)
* [In search of theoretically grounded pruning](https://openreview.net/forum?id=SkfQAiA9YX)
* [Learning to Search Efficient DenseNet with Layer-wise Pruning](https://openreview.net/forum?id=r1fWmnR5tm)
* [DEEP-TRIM: REVISITING L1 REGULARIZATION FOR CONNECTION PRUNING OF DEEP NETWORK](https://openreview.net/forum?id=r1exVhActQ)
* [INTERPRETABLE CONVOLUTIONAL FILTER PRUNING](https://openreview.net/forum?id=BJ4BVhRcYX)
* [Mean Replacement Pruning](https://openreview.net/forum?id=BJxRVnC5Fm)
