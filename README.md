# animal_detect_paddle
 基于paddlepaddle框架的十二种动物识别

项目aistudio地址：https://aistudio.baidu.com/aistudio/projectdetail/4214486?contributionType=1

### 项目介绍：

#### 项目思路

（1）创建数据集标注文件

对训练集、验证集、测试集三个数据集进行标注。

（2）数据预处理

将原图随机裁切为224*224大小，训练集中的数据将有50%的概率水平翻转。

（3）数据加载

使用paddle.io.DataLoader将数据加载进paddlepaddle框架中，设置参数batch_size，shuffle，dropout。

（4）搭建神经网络

搭建了两种经典CNN，VGG16与RepVGG

（5）评估训练模型

对使用不同神经网络和不同优化器训练的模型进行评估，计算出accuracy、error rate、precision、recall四个值

#### 最终结果

最终结果准确率为83.33%，由于使用VGG16网络和训练集较大、输出结果较多导致训练较慢，若需要进一步提升还需要大量时间来进行提升。从混淆矩阵中可以看出一些有意思的东西，老鼠和龙的识别成功率较低，可能训练集中的图像风格不一，同一类别中都有较大的差别。牛也有可能识别为羊，马有可能识别成牛，因为这三类动物相似度较高。识别成功率较高的是猪和鸡，可能因为形态和颜色与其他种类的动物具有较大的差别。
