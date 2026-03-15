# Research 2 - 卷积神经网络

## 学习目的

在上一轮考核中，你成功实现了一个简单的二层神经网络，并在 CIFAR-10 数据集上进行了训练。

然而，现实世界中的神经网络远比两层神经网络复杂得多。为了应对更复杂的任务，我们需要引入更多的层次、更复杂的结构，以及更高效的训练方法。

CNN 是深度学习中最重要的网络结构之一，广泛应用于计算机视觉任务中。通过卷积操作，CNN 能够有效地捕捉图像中的空间特征，从而大幅提升图像分类、目标检测等任务的性能。

本轮的任务是学习 CNN，并且探索现代深度学习框架（如 PyTorch）的使用方法。

## 学习内容

本轮的学习将从整体架构转向模块化实现，你将深入理解并实现构成现代神经网络的各个独立组件：

* 网络优化与正则化：批量归一化（Batch Normalization）、Dropout
* 模块化网络设计：将网络层（如全连接层、ReLU 激活层）抽象为独立的、拥有 `forward` 和 `backward` 接口的模块
* 卷积神经网络核心：卷积层（Convolutional Layer）的前向与反向传播、池化层（Pooling Layer）的前向与反向传播
* 现代框架实践：在手动实现所有组件后，使用高层框架（如 PyTorch）快速搭建一个高性能的 CNN 模型

## 作业

### 作业 1 - 完成 CS231n Assignment 2

完成 [CS231n Assignment 2](https://cs231n.github.io/assignments2025/assignment2/)，并写一份文档记录你的实现细节、分析结果以及你在实现过程中遇到的挑战与解决方案。

> 完成这次作业后请思考，我们为什么需要 PyTorch 这样的框架？

### 作业 2 - 自定义数据集构建与数据增强

CS231n 和很多教程都是直接用 torchvision.datasets.CIFAR10，数据也是打包好的。

但现实世界的 AI 工程师，90% 的时间在处理乱七八糟的数据。

本轮作业要求你自己构建一个图像分类数据集，并实现数据增强管道。

#### 拟定题目

请确定一个你感兴趣的多分类主题（至少 3 个类别）。

例如：

1. 猫咪 vs 狗狗 vs 仓鼠
2. 剪刀 vs 石头 vs 布
3. 你最喜欢的三个动漫角色
4. 三种不同的食物
5. 自行拟题目

#### 收集数据

利用爬虫或者手动收集所需要的图片，每个类别至少 50 张图片，并将它们整理到合适的文件夹结构中，例如：

```tree
dataset/
    train/
        class1/
            img1.jpg
            img2.jpg
            ...
        class2/
            img1.jpg
            img2.jpg
            ...
        class3/
            img1.jpg
            img2.jpg
            ...
    val/
        class1/
            img1.jpg
            img2.jpg
            ...
        class2/
            img1.jpg
            img2.jpg
            ...
        class3/
            img1.jpg
            img2.jpg
            ...
```

要求：

1. 图片不需要裁剪整齐，尺寸可以不一致。
2. 严禁直接下载 Kaggle 或其他网站上已经打包好的 .zip 格式数据集。

#### 数据集类

你需要继承 torch.utils.data.Dataset 类，实现你自己的数据集加载器。

你的代码结构应该包含：

* `__init__`：初始化文件路径，读取图片列表。
* `__len__`：返回数据集的大小。
* `__getitem__`：根据索引读取图片，转换色彩空间（如 RGB），并应用数据预处理/增强。

你的数据集中可能包含损坏的图片（无法读取）或者非 RGB 格式（如 CMYK 或 灰度图）的图片，你的代码需要具备鲁棒性，能够处理或过滤掉这些异常情况，而不是直接报错崩溃。

#### 数据增强

请使用 torchvision.transforms 或 albumentations 库设计一套增强策略，包括但不限于：

* 几何变换：随机旋转、翻转、裁剪。
* 色彩变换：亮度、对比度、饱和度调整。
* 进阶（选做）：尝试使用 Cutout, Mixup 等高级增强技巧。

#### 验证与可视化

你需要编写脚本来验证你的数据集是否工作正常。

使用 DataLoader 加载一个 Batch 的数据。

利用 matplotlib 将这个 Batch 中的图片及其对应的标签（Label）可视化出来。

展示同一张图片在应用了不同的数据增强策略后的效果对比。

#### 文档要求

在完成作业后，你需要写一份**文档**，内容包括但不限于：

1. 你构建了什么数据集？数据来源是哪里？包含多少个类别和样本？
2. 展示你的 CustomDataset 类的代码，并解释你是如何处理图片读取和异常值的。
3. 展示你的 transforms 配置。
    1. 贴出 DataLoader 读取出的 Batch 可视化截图。
    2. 对比原始图片与增强后的图片，分析增强策略是否合理
4. 在处理脏数据的过程中，你踩了哪些坑？（例如图片后缀是 .jpg 但实际是 png 格式？图片损坏导致训练中断？）

### 作业 3 - 根据 MNIST 数据集实现一个简单的识别数字的 Demo（选做）

人工智能的高级框架不只有 PyTorch，还有 TensorFlow，Keras 等等。

目前，Keras 已经被集成到 TensorFlow 中，成为其高级 API。

TensorFlow.js 是 TensorFlow 的 JavaScript 版本，可以直接在浏览器中运行深度学习模型。

本次作业要求你实现并部署一个基于 TensorFlow.js 的 MNIST 手写数字识别 Web 应用。

该项目的最终成果可以在[这里](https://shaddocknh3.github.io/tfjs-mnist-digit-recognizer/)体验。

本次作业的目标是让你亲历一个人工智能应用从训练到部署的全过程。你可以以[该项目](https://github.com/ShaddockNH3/tfjs-mnist-digit-recognizer)为基础框架，识别模型需要你亲手训练。

> 此后简称为该项目，不列出链接。

#### 训练识别模型

原项目（旧版本）中的模型存在版本兼容性以及无法兼容手机端的问题。

由于浏览器环境主要运行 TensorFlow.js，无法直接运行 PyTorch 和 TensorFlow。

你的任务是使用 Keras / PyTorch，在经典的 MNIST 数据集上，从零开始构建并训练一个卷积神经网络（CNN）。

你需要自行设计网络结构、选择优化器和损失函数，并进行超参数调整，以达到尽可能高的识别准确率。

训练完成后，你将得到一个 Keras / PyTorch 模型文件（通常是 `.h5` 格式或 `.pt` 格式）。

#### 模型转换

你需要通过转换工具，将训练好的模型迁移到 Web 环境中。

如果你采用了 Keras 进行训练，你需要使用 `tensorflowjs_converter` 将 Keras 模型直接转换为 TensorFlow.js 格式。

如果你采用了 PyTorch 进行训练，你需要把训练好的模型导出为 ONNX 格式，然后使用 onnx-tf 等工具将 ONNX 模型转换为 TensorFlow SavedModel，再转换为 TensorFlow.js 格式。

最终，你将得到两个文件：`model.json` 和一个 `.bin` 权重文件。

#### 前端实现

你可以 fork 该项目，然后替换原仓库 model 文件夹下的两个训练文件。

在你完成了文件替换后，你还需要修改 index.html 的第 6 行为自己的 GitHub 用户名。

当然你也可以从零开始实现一个前端页面，要求功能与该项目类似即可。

在你完成了整个项目后，你需要通过 GitHub Pages，将你的项目部署为一个公开可访问的网页。

在 PC 和移动端打开你的网页，在画板上写下数字，验证识别功能是否正常工作。

## 推荐教程与参考资料

### 识别数字 Demo 参考资料

* [参考实现：使用 Keras.js 的旧版思路](https://github.com/starkwang/keras-js-demo)
* [参考教程：从训练到部署的详细步骤](https://www.cnblogs.com/chinasoft/p/17084356.html)
* [TensorFlow.js 官方文档](https://www.tensorflow.org/js/guide?hl=zh-cn)

## 作业要求

1. 不要抄袭
2. 遇到不会可以多使用搜索引擎，实在没有找到解决方法可以来群里提问，作为一个CSer学习提问的方式也非常重要，强烈建议阅读 [Stop-Ask-Questions-The-Stupid-Ways](https://github.com/tangx/Stop-Ask-Questions-The-Stupid-Ways/blob/master/README.md) 这篇文章
3. 不限制使用 ChatGPT 等大语言模型工具，但你需要确保你了解模型生成的内容的每一个细节，最好你可以在使用大语言模型生成的代码部分注释上「reference from ChatGPT」这样的内容
4. 你还需要学习基本的 Git 的使用，所有考核都采用 Git 的方式进行上传
5. 作业内容可能会进行更新，请保持关注

## 作业提交方式

1. 你需要学习 GitHub 的使用，创建一个你自己的仓库用来存放你的代码实现
2. 接着你需要学习如何使用 Git 进行 PR 操作，在 [solutions](https://github.com/west2-online-reserve/collection-ai) 中进行操作
