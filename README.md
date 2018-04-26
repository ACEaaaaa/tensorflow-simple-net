# tensorflow-simple-net
tensorflow实现简单的卷积神经网络
使用的数据集是mnist,预期可以达到99.2%左右的准确率。
使用两个卷积层加一个全连接层构建一个简单但是非常有代表性的卷积神经网络。
输入图片为28X28的单通道数字图片
第一个卷积层[5,5,1,32]卷积核尺寸为5X5，一个颜色通道，32个不同的卷积核。使用conv2d函数进行卷积操作，并加上偏置，接着再使用RelU激活函数进行非线性处理。
然后使用最大池化函数max_pool_2x2对卷积的输出结果进行池化操作。
第二个卷积层[5,5,32,64]卷积核尺寸为5X5，32通道，64个不同的卷积核。使用conv2d函数进行卷积操作，并加上偏置，接着再使用RelU激活函数进行非线性处理。
然后使用最大池化函数max_pool_2x2对卷积的输出结果进行池化操作。
为了减轻过拟合，使用一个Dropout层，通过一个placeholder传入keep_prob比率来控制。在训练时，随机丢弃一部分结点的数据来减轻过拟合，预测时则保留全部数据来追求最好的预测性能。

这个CNN模型可以得到的准确率为99.2%，基本可以满足对手写数字识别准确率的要求。性能提升来自于更优秀的网络设计，即卷积网络对图像特征的提取和抽象能力。依靠卷积核的权值共享，CNN的参数量并没有爆炸，降低计算量的同时也减轻了过拟合，因此整个模型的性能也有较大的提升。
