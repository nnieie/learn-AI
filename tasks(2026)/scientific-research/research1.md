# Research 1 - 机器学习

## 学习目的

在前三轮学习中，你已经掌握了 Python 编程基础，爬虫以及和基本的数据分析。

人工智能领域主要分为两大方向：计算机视觉和自然语言处理。

无论是 CV、NLP 还是其他方向，它们的训练都基于共同的核心理论基础——反向传播算法。

诚然，使用 PyTorch 等现代成熟的深度学习框架可以有效简化实现过程。

然而西二在线的目标不是培养简单的工具使用者，而是培养具备扎实理论基础和实践能力的实践者、研究者。

作为计算机专业的学生，我们的竞争力在于深入理解基本原理，并具备从零实现算法、调试和优化模型的能力。

本轮考核的目的是让你掌握一些基本的机器学习算法。

对于基于树的复杂集成算法（如随机森林、XGBoost、决策树），由于其实现逻辑与神经网络差异较大，只需要了解原理并掌握 [scikit-learn](https://scikit-learn.org/stable/) 即可，无需从零实现。

但对于线性分类器（k-NN, SVM, Softmax），它们是理解神经网络损失函数和梯度下降的基石，你需要在作业 1 中实现。

这里简要解释传统机器学习与深度学习的区别。二者最核心的区别在于如何学习和利用数据的「特征」。

例如，决策树和随机森林基于预先定义的特征（如气象状态、温度范围等），通过一系列逻辑判断逐步推理出结论，整个决策过程直观且可解释。

而支持向量机则更为抽象，它试图在数据之间找到一个最优的分界超平面。这种通过数学优化寻找复杂边界的思想，与神经网络通过调整权重来划分数据的逻辑具有相似性。

深度学习最根本的优势在于其强大的「自动特征提取」能力。我们不再需要手动设计特征，深度神经网络能够从原始数据中逐层抽象和学习出解决问题所需的高效特征表示，这正是它与传统机器学习算法最关键的区别。

此外，本阶段虽然名为机器学习，但我们将以神经网络的诞生作为终点，为你平滑过渡到下一阶段的深度学习。

## 学习内容

本轮的学习内容将围绕一系列经典的机器学习模型与概念展开，最终导向对神经网络机制的理解：

- 分类器基础：K-Nearest Neighbor（k-NN, K-近邻）、Support Vector Machine（SVM, 支持向量机）、Softmax Classifier（Softmax 分类器）、XGBoost、Random Forest（随机森林）
- 神经网络核心：Two-Layer Neural Network（两层神经网络）、Fully-Connected Networks（全连接网络）
- 特征工程：Image Features（图像特征，包括 Histogram of Oriented Gradients、Color Histograms）

## 学习要求

本轮学习内容对新手而言具有相当的挑战性，尤其对于首次接触全英文课程的同学。但这正是我们希望你克服的首要难题。在人工智能领域，英文阅读能力不是加分项，而是必备技能，因为绝大多数前沿论文、官方文档和高质量社区讨论都以英文为载体。我们鼓励你勇敢面对这个挑战，并善用工具辅助学习。

此外，本轮需要一些前置知识：线性代数、微积分、NumPy 以及 Python 编程。

后两者已经在前几轮涉及，前两者如果学校课程尚未开设（对于大一学生，偏导数部分在高等数学大一下学期讲授），可以参考下一节的推荐教程。

对于非类似深度学习思想的机器学习算法，只需要写一篇文档来描述算法的原理和使用场景即可，无需从零实现。

## 作业

对于本次作业，你需要完成 2 篇文档以及 1 个 CS231n 的作业。

### 文档 1

介绍 K-Nearest Neighbor（k-NN, K-近邻）、Support Vector Machine（SVM, 支持向量机）、Softmax Classifier（Softmax 分类器）、XGBoost、Random Forest（随机森林）这五种机器学习算法的原理和使用场景，并指出这些算法与神经网络的区别。

### 文档 2

阅读[李宏毅生成式人工智能教程课本](https://github.com/datawhalechina/leegenai-tutorial/releases)，寻找文章片段，并且以文档形式讲述大语言模型的整个训练流程。

> 本文档**不要求精确的数学公式和理论表达**，只需用你自己的话，简要描述生成式 AI 的三个训练阶段：
>
> 1. 自监督学习（Pre-training）
> 2. 监督式学习（Supervised Fine-tuning）
> 3. 人类反馈强化学习（RLHF）

### 作业 1 - CS231n Assignment 1

完成 [CS231n Assignment 1](https://cs231n.github.io/assignments2025/assignment1/)，并且写一份文档来描述你在完成作业过程中遇到的挑战和解决方案。

## 推荐教程与参考资料

### 生成式 AI 认识

[李宏毅 2024 B 站](https://www.bilibili.com/video/BV1BJ4m1e7g8/?spm_id_from=333.337.search-card.all.click&vd_source=e3594664d709db7578f4b2e76329df18)

[李宏毅 2024 YouTube](https://www.youtube.com/watch?v=AVIKFXLCPY8&t=1s)

[李宏毅 2025 YouTube](https://www.youtube.com/watch?v=VuQUF1VVX40&list=PLJV_el3uVTsMMGi5kbnKP5DrDHZpTX0jT&index=1&t=10s)

[李宏毅生成式人工智能教程课本](https://github.com/datawhalechina/leegenai-tutorial/releases)

> 注意：生成式 AI 导论不要求完成课程作业。YouTube 上的 2025 版课程仍在持续更新，教程课本是根据 2024 年春季学期课程整理而成。
>
> 2025 年秋季版课程在前几讲就引入了较为复杂的概念，与 2024 年春季版相比难度提升较多，内容变化也较大。建议初学者优先学习 2024 年春季版课程或直接阅读教程课本，无需观看 2025 年秋季版。
>
> 学习生成式 AI 导论时，无需看完所有课程或课本，只需根据作业文档 2 的要求，针对性地学习相关内容即可。

### Sklearn

[scikit-learn](https://scikit-learn.org/stable/)

### CS231n

学习机器学习需要有一定的数学知识作为基础。

#### 前置知识

1. 前三轮知识：尤其是 NumPy、Pandas 和 Matplotlib 库。Python 基础不必多说，爬虫的作用主要是为未来进行人工智能研究时，具备补全数据或爬取所需数据的能力。
2. 多元函数复合求导（求偏导）：具体内容在高等数学 B 下学期讲授，可参考[宋浩高等数学](https://www.bilibili.com/video/BV1Eb411u7Fw?spm_id_from=333.788.videopod.episodes&vd_source=0272bb7dd0d8d9302c55fc082442b9e3&p=96)，直至能够完成一些简单的求偏导计算。
3. 线性代数：计算机专业的同学大一上已经开设线性代数课程。无论对于已学或未学的同学，都可以参考[线性代数的本质](https://www.bilibili.com/video/BV1Ys411k7yQ/?spm_id_from=333.337.search-card.all.click&vd_source=0272bb7dd0d8d9302c55fc082442b9e3)系列视频加深对线性代数的理解。
4. NumPy：作业将大量使用 NumPy 进行向量化（Vectorization）计算。请务必完成 [CS231n 官方 NumPy 教程](https://cs231n.github.io/python-numpy-tutorial/)。对于不熟悉的 API，学会使用搜索引擎和大语言模型工具进行查询。
5. 矩阵求导：这是理解反向传播数学原理的关键。不必畏惧，你只需掌握基础的求偏导知识即可入门。推荐通过以下资源学习：
   - [B 站视频教程](https://www.bilibili.com/video/BV1av4y1b7MM/)
   - [知乎文章讲解](https://zhuanlan.zhihu.com/p/273729929)

#### CS231n 课程相关链接

Stanford CS231n: Convolutional Neural Networks for Visual Recognition

- [CS231n 2024 Notes](https://cs231n.github.io/)
- [CS231n 2024 Spring](https://cs231n.github.io/)
- [CS231n 2025 Spring](https://cs231n.stanford.edu/assignments.html)
- [课程中文翻译](https://zhuanlan.zhihu.com/p/21930884)（采用 Python 2.7 版本，已过时，可作为辅助理解材料）

> 需要注意，CS231n 课程官方笔记页面提供的是 24 版本的作业。当前版本的则是 25 版，不过官方的笔记没有跟进。你可以选择完成 24 年的版本或者 25 年的版本，无论选择哪个版本，核心任务和学习目标是一致的。

#### CS231n 课程视频

1. CS231n 的[课程视频](https://www.bilibili.com/video/BV1b1agz5ERC/?spm_id_from=333.337.search-card.all.click&vd_source=0272bb7dd0d8d9302c55fc082442b9e3)
2. 如果觉得 CS231n 的数学推导过多，建议观看[李宏毅老师的机器学习课程](https://www.bilibili.com/video/BV1Wv411h7kN/)，该课程更侧重于从直观角度理解模型原理
3. [吴恩达老师的机器学习视频](https://www.bilibili.com/video/BV1owrpYKEtP/?spm_id_from=333.337.search-card.all.click&vd_source=0272bb7dd0d8d9302c55fc082442b9e3)

#### 配环境

学习 CS231n 需要配置环境，这里主要推荐两条路线。

- 使用 Colab

如果你的电脑配置较低（没有 GPU），建议使用 Google Colab。

CS231n 官方和 Google 有合作，只要你有 Google 账号，就可以直接使用 Colab 环境完成作业。

打开 CS231n [24 Spring Assignment 1](https://cs231n.github.io/assignments2024/assignment1/) 页面或者 [25 Spring Assignment 1](https://cs231n.github.io/assignments2025/assignment1/) 页面，然后观看 Setup 这个视频，按照视频中的步骤操作即可。

这里直接给出这个视频的链接：[CS231N Google Colab Assignment Workflow Tutorial](https://www.youtube.com/watch?v=DsGd2e9JNH4&source_ve_path=MjM4NTE&embeds_referring_euri=https%3A%2F%2Fcs231n.github.io%2F)

- 本地配置环境

本地配置环境的推荐前提是有一台性能较好的电脑，最好有 NVIDIA 显卡（支持 CUDA）。

如果你是 Linux 或 Mac 用户，推荐直接使用系统自带的终端进行配置。

如果你是 Windows 用户，可以考虑使用 Windows Subsystem for Linux（WSL2）不推荐直接在 Windows 系统下使用。

不推荐使用 Linux 虚拟机，因为虚拟机的性能通常较差，可能无法满足深度学习的需求。

如果你执意要直接使用 Windows，可以参考[weijianxian CS231n 2025 spring 的环境配置](https://github.com/weijianxian/cs231n-25)，该方法使用 uv，也可以使用传统的 venv。

如果你想采用 Windows + conda 的方式进行配置，可以参考[rechenz CS231n 2025 spring 的环境配置](https://github.com/rechenz/SetupLocal-for-cs231n-25)。

个人推荐使用 WSL2，微软官方有详细的[安装教程](https://learn.microsoft.com/zh-cn/windows/wsl/install)。

这里贴出来几个下载 WSL2 碰到的常见的问题以及解决方案，如果你是 Linux 或者 Mac 用户，可以跳过这部分。

1. 我配完 WSL2 后，手机模拟器（例如 mumu 模拟器）非常卡顿，怎么办？

因为市面上大多数的手机模拟器的实现技术和 WSL2 是冲突的。

具体而言，WSL2 是基于 Hyper-V 的虚拟化技术，而大多数手机模拟器是基于 VirtualBox 或者其他虚拟化技术实现的，这两种虚拟化技术是冲突的，所以会导致手机模拟器非常卡顿。

解决方法有两种，一种是使用蓝叠模拟器或者谷歌模拟器（Beta 开发中），另一种是 `Win + Shift + R`，输入 `cmd` 后，`Win + Shift +Enter` 进入管理员模式：

```bash
# 只能使用 wsl 时
bcdedit /set hypervisorlaunchtype auto

# 使用 mumu 模拟器时
bcdedit /set hypervisorlaunchtype off
```

然后重启。

注意是重启，大部分没经过特别设置的 Windows，关机等同于深度睡眠，并不会修改你的系统设置。

> 更新中。

#### 学习路径建议

1. 适应英文环境：积极适应全英文的学习材料。建议不要使用浏览器的全文自动翻译，可以安装划词翻译插件，强制自己阅读原文，只在遇到生词时进行查询。
2. 研读课程笔记（Notes）：CS231n 的课程 Notes 是完成作业的重要学习资源，内容详实且深入。请务必花费时间仔细阅读，这是理解所有模型原理的基础。
3. 攻克数学难点：遇到矩阵求导等数学难题时，不要直接跳过。利用推荐的视频和文章，认真推导一两个简单的例子，你会发现它并没有想象中那么困难。
4. 建立交流社区：我们希望将考核群打造成一个高效的学习社区。请积极在群里讨论问题，尤其是数学和理论方面的内容。交流能极大地提高学习效率。但严禁直接分享或抄袭代码。

## 作业要求

1. 不要抄袭
2. 遇到不会可以多使用搜索引擎，实在没有找到解决方法可以来群里提问，作为一个CSer学习提问的方式也非常重要，强烈建议阅读 [Stop-Ask-Questions-The-Stupid-Ways](https://github.com/tangx/Stop-Ask-Questions-The-Stupid-Ways/blob/master/README.md) 这篇文章
3. 不限制使用 ChatGPT 等大语言模型工具，但你需要确保你了解模型生成的内容的每一个细节，最好你可以在使用大语言模型生成的代码部分注释上「reference from ChatGPT」这样的内容
4. 你还需要学习基本的 Git 的使用，所有考核都采用 Git 的方式进行上传
5. 作业内容可能会进行更新，请保持关注

## 作业提交方式

1. 你需要学习 GitHub 的使用，创建一个你自己的仓库用来存放你的代码实现
2. 接着你需要学习如何使用 Git 进行 PR 操作，在 [solutions](https://github.com/west2-online-reserve/collection-ai) 中进行操作
