# compression
* [Adaptive Sample-space & Adaptive Probability coding: a neural-network based approach for compression](https://openreview.net/forum?id=HkzNXhC9KQ)
* [Practical lossless compression with latent variables using bits back coding ](https://openreview.net/forum?id=ryE98iR5tm)
  * lossless compression of large image datasets
* [Sparse Binary Compression: Towards Distributed Deep Learning with minimal Communication](https://openreview.net/forum?id=B1edvs05Y7)
  * To mitigate problem(bandwidth communication) we propose Sparse Binary Compression (SBC), a compression framework that allows for a drastic reduction of communication cost for distributed training
  * SBC combines existing techniques of communication delay and gradient sparsification with a novel binarization method and optimal weight update encoding
  * stack of previous tech, lack of novelty
* [DeepTwist: Learning Model Compression via Occasional Weight Distortion ](https://openreview.net/forum?id=HJzLdjR9FX)
  * In this paper, we propose a simple and efﬁcient model compression framework called DeepTwist which distorts weights in an occasional manner without modifying the underlying training algorithms
  * Occasional compression within *a S<sub>D</sub> step* finally enhance acc
    * pruning
    * quantization
    * low-rank approximation
* [Exploiting Invariant Structures for Compression in Neural Networks ](https://openreview.net/forum?id=rkl85oRqYX)
  * The submission suggests a methodology compressing the parameters of neural network (NN) architectures
    * first converting them to higher-order tensors
    * then factorizing them with various tensor decompositions
  * several issues
    * the invariant structures suggested by the authors do appear within the parameters of a neural network architecture and such invariant structures are captured by the higher-order tensor decomposition proposed
    * no need to high tensor: decomposition A=a\*b is enough, there is no need to T=A\*B and then T=x<sub>1</sub>\*x<sub>2</sub>\*x<sub>3</sub>\*x<sub>4</sub>
* [Non-vacuous Generalization Bounds at the ImageNet Scale: a PAC-Bayesian Compression Approach](https://openreview.net/forum?id=BJgqqsAct7)
  * The paper presents an application of PAC-Bayesian bounds to the problem of ImangeNet classification the authors introduce some clever choices for the prior distribution (on the hypothesis space) that allow one to incoperate a compression scheme and obtain a (non-vacuous) bound for the predictor.
  * a method for taking into account symmetries of the uncompressed parameters

* [Adaptive Estimators Show Information Compression in Deep Neural Networks ](https://openreview.net/forum?id=SkeZisA5t7)
  *  In this paper we developed a more robust mutual information estimation technique, that adapts to hidden activity of neural networks and produces more sensitive measurements of activations from all functions, especially unbounded functions.
  * we show that saturation of the activation function is not required for compression
  * the amount of compression varies between different activation functions
  * We also found that there is a large amount of variation in compression between different network initializations
  * L2 regularization leads to significantly increased compression while preventing overfitting
* [Integer Networks for Data Compression with Latent-Variable Models ](https://openreview.net/forum?id=S1zz2i0cY7)
  * introduce an *interger neural network* to solve the problem raised by using *variational latent-variable models for data compression*.**the latent Representation needs to be subjected to entropy coding**
  * autor define the relationship between inputs **u** and outputs **w** of one layer is **v**=(**H** \* **u**+**b**)/**C** and **w**=g(**v**)
  * **H** and **w**:8-bit signed
  * **b v**: 32-bit signed
  * **c**: 32-bit unsigned
  * g<sub>ReLU</sub>(v)=max(min(v,255),0) (quantized ReLU and quantized Tanh)
* [NETWORK COMPRESSION USING CORRELATION ANALYSIS OF LAYER RESPONSES](https://openreview.net/forum?id=rkl42iA5t7)
* [What Information Does a ResNet Compress? ](https://openreview.net/forum?id=HklbTjRcKX)
  * This paper was motivated by the debate over the relevance of the Information Bottleneck principle to deep learning
  * The novelty is that we apply information theoretic analyses to modern convolutional ResNets trained on realistic images(CINIC-10)
  * Our solution is to deﬁne a lower bound on the mutual information  and to estimate it by training decoder models
* [REPRESENTATION COMPRESSION AND GENERALIZATION IN DEEP NEURAL NETWORKS](https://openreview.net/forum?id=SkeL6sCqK7)
* [LIT: Block-wise Intermediate Representation Training for Model Compression](https://openreview.net/forum?id=BkeUasA5YQ)
* [N-Ary Quantization for CNN Model Compression and Inference Acceleration](https://openreview.net/forum?id=HylDpoActX)
* [Data-Dependent Coresets for Compressing Neural Networks with Applications to Generalization Bounds](https://openreview.net/forum?id=HJfwJ2A5KX)
* [MLPrune: Multi-Layer Pruning for Automated Neural Network Compression](https://openreview.net/forum?id=r1g5b2RcKm)
* [Architecture Compression](https://openreview.net/forum?id=BygGNnCqKQ)
* [Model Compression with Generative Adversarial Networks](https://openreview.net/forum?id=Byxz4n09tQ)
* [Learnable Embedding Space for Efficient Neural Architecture Compression](https://openreview.net/forum?id=S1xLN3C9YX)
* [Energy-Constrained Compression for Deep Neural Networks via Weighted Sparse Projection and Layer Input Masking](https://openreview.net/forum?id=BylBr3C9K7)
