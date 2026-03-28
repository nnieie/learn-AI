# Research 2 - 训练自己的模型

> 预计耗时：30 天

## 学习目的

## 作业

### 作业 3 - 根据 MNIST 数据集实现一个简单的识别数字的 Demo（选做）

人工智能的高级框架不只有 PyTorch，还有 TensorFlow，Keras 等等。

目前，Keras 已经被集成到 TensorFlow 中，成为其高级 API。

TensorFlow.js 是 TensorFlow 的 JavaScript 版本，可以直接在浏览器中运行深度学习模型。

本次作业要求你实现并部署一个基于 TensorFlow.js 的 MNIST 手写数字识别 Web 应用。

该项目的最终成果可以在 [这里](https://shaddocknh3.github.io/tfjs-mnist-digit-recognizer/) 体验。

本次作业的目标是让你亲历一个人工智能应用从训练到部署的全过程。你可以以 [该项目](https://github.com/ShaddockNH3/tfjs-mnist-digit-recognizer) 为基础框架，但识别模型需要你亲手训练。

> 此后简称为该项目，不列出链接。

#### 训练识别模型

原项目（旧版本）中的模型存在版本兼容性问题，且无法兼容手机端。

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

你可以 fork 该项目，然后替换原仓库 model 文件夹下的两个模型文件。

在你完成文件替换后，你还需要将 index.html 的第 6 行修改为你自己的 GitHub 用户名。

当然你也可以从零开始实现一个前端页面，要求功能与该项目类似即可。

在你完成整个项目后，你需要通过 GitHub Pages 将项目部署为一个公开可访问的网页。

在 PC 和移动端打开你的网页，在画板上写下数字，验证识别功能是否正常工作。

## 推荐教程与参考资料

### 识别数字 Demo 参考资料

* [参考实现：使用 Keras.js 的旧版思路](https://github.com/starkwang/keras-js-demo)
* [参考教程：从训练到部署的详细步骤](https://www.cnblogs.com/chinasoft/p/17084356.html)
* [TensorFlow.js 官方文档](https://www.tensorflow.org/js/guide?hl=zh-cn)
