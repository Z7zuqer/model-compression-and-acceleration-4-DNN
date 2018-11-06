# squeeze
首先，顺着空间维度把每一张featuremap通过global average pooling归纳为一个实数。featuremap维度I<sub>c*h*w</sub>，经过池化会成为I<sub>c*1*1</sub>。  
这个实数具有全局的感受野，理解为更加能够代表这张featuremap的*整体*信息
# excitation
* 能够学习通道之间的非线性交互
* 学习非互斥的关系？
首先将特征维度降低到输入的 1/16，然后经过 ReLu 激活后再通过一个 Fully Connected 层升回到原来的维度
* 特征融合，将不同通道的特征融合
* 避免全连接，减少计算量
