# Backend Routine

## 学习目的

尽管 Python 后端已经不再推荐，但是仍然可以用于快速验证原型机、个人小项目以及应付大作业。

## 学习内容

[Golang 后端 / 运维从入门到如土](https://github.com/west2-online/learn-go)

Flask / FastAPI

## 作业

你可以完成这些作业来检验你的学习水平。这些作业并不需要提交，当然你也可以提交展示并参与答辩。

其实我更推荐你直接去写 Go / Java 的考核，写这些东西代码不重要，重要的是你的架构思想和统筹全局的观念。

### TODO LIST Demo

[TODO LIST Demo](https://github.com/west2-online/learn-go/blob/main/docs/3-%E5%A4%87%E5%BF%98%E5%BD%95.md)

### TikTok Demo

[TikTok Demo](https://github.com/west2-online/learn-go/blob/main/docs/4-%E5%A4%A7%E4%BD%9C%E5%93%81.md)

### TikTok Demo PLUS

[TikTok Demo PLUS](https://github.com/west2-online/learn-go/blob/main/docs/5(2025)-%E5%BE%AE%E6%9C%8D%E5%8A%A1.md)

### TikTok Demo Ultra

[TikTok Demo Ultra](https://github.com/west2-online/learn-go/blob/main/docs/6(2025)-%E9%83%A8%E7%BD%B2%E4%B8%8E%E7%9B%91%E6%8E%A7.md)

## 推荐教程与参考资料

### 一些问题

1. ~~Q：我想学人工智能，为什么要学后端方面的知识？~~

    ~~A：人工智能不是单打独斗，也需要合作应用，很多时候训练好的模型在别人调用时，需要一些简单的接口，因此需要学习少量的后端知识，从而知道怎么发送接口，但是无需深入了解。~~

2. Q：Python 后端有前途吗？

    A：Python 后端在几年前还是很热门的，但是现在已经日渐式微，在求职方面比不过 Java 和 Go，但由于搭建速度快还是有些中小公司在产品初期使用，因此如果有想深入后端的，可以去多看看 Java 和 Go，或者转前端测试。但是如果你只想做一个个人的小项目的话，Python 开发速度快，工具多，是不错的选择。

3. Q：为什么学习 Flask 或者 FastApi 而不是更强的 Django？

    A：现在前后端分离是主流，前端通过接口和后端通讯，而不是后端直接渲染，强调低耦合。而 Django 在前后端分离的项目上，对比 Flask 以及 FastApi 没有优势，反而显得太重了。因此选择 Flask 或者 FastApi 进行学习

### 偏基础阶段的文档

1. Git 和 GitHub 的使用：<https://blog.csdn.net/weixin_53315561/article/details/126802065> (pycharm 的 git 其实也很方便，可以了解一下)
2. flask 文档：<https://dormousehole.readthedocs.io/en/latest/>
3. flask 视频教程：<https://www.bilibili.com/video/BV1v7411M7us> （为什么推荐这个教程，因为这个教程只讲接口，不用了解模板和渲染的纯后台，更适合现在前后端分离趋势）
4. fastapi 文档：<https://fastapi.tiangolo.com/zh/> (fastapi 的文档已经写的很完善了，一步步入手，可以先看文档，不会再去搜)
5. 接口测试工具
    - apifox：<https://www.apifox.cn/>
    - apipost：<https://www.apipost.cn/>
    - postman：<https://www.postman.com/>
6. REST 风格 api：<https://juejin.cn/post/7025222833798119454>，状态码请按照文中的反例来写，状态码全传 200，通过返回体中的 code 字段进行区分请求是否成功，同时返回 msg，成功返回 data。至于为什么状态码全传 200 可以看知乎

    ```json
    HTTP/1.1 200 ok
    Content-Type: application/json
    Server: example.com
    #失败
    {
        "code": 404,
        "msg": "该活动不存在",
    }
    #成功
    {
        "code": 200,
        "msg": "success",
        "data": {
            ...
        }
    }
    ```

7. RESTful api 部分相关前置知识：<https://cloud.tencent.com/developer/article/1448167> 、<https://blog.csdn.net/D_R_L_T/article/details/82562902>
8. 多种传参方式，Query传参和Body传参，具体请看相应框架的文档
9. GitHub 是一个很好的学习平台，可以看别人的代码的架构了解自己的不足
10. pycharm 可以在创建项目时选择 Flask 项目和 FastApi 项目，让项目快速启动起来，可以尝试

### 稍微进一步的文档

1. RESTAPI
2. JWT 鉴权知识：<https://learnku.com/articles/17883>
3. JWT用法：<https://blog.csdn.net/yangbindxj/article/details/125344291> （这里用了Fastapi 的例子，其实 jwt 库两个都可以用）
4. ORM 用 Flask 推荐 flask-sqlalchemy，用 Fastapi 推荐 sqlalchemy，flask-sqlalchemy 可以通过 paginate 分页比较方便，sqlalchemy 分页需要 offset + limit
5. 蓝图（Flask）/ APIRouter（Fastapi）看各自的文档还有网上资料
6. 通过异常处理器（@app.errorhandler/@app.exception_handler）捕获异常（参数错误 /token 错误），并把异常结果格式化为应该返回的格式
7. 文件的上传，响应文件下载
8. 推荐使用 logging 日志工具打印运行时的日志
9. 在登陆后在 token 中添加用户的权限信息，对于需要 token 的接口在 JWT 解码时进行权限检验和进行拦截，Flask 使用装饰器，FastApi 可以选择依赖注入，或者使用中间件拦截
10. FastiApi 可以使用自带的参数检验，Flask 应该引入 Flask-Restful，规范 RestfulAPi，同时使用其带的参数检验功能 [Flask-RESTful](http://www.pythondoc.com/Flask-RESTful/index.html)
11. 在框架中接入 redis 等进行缓存，读写很快，可以用于缓存验证码，以及一些经常读写的信息
12. 部署项目环境弄起来非常的难受，建议大家学习一下 docker，使用 docker 将项目部署到服务器
13. 各种 id 可以使用雪花算法来生成，防止数据库自增 id 过程出错

### 偏进阶阶段的文档

1. [Flask-SocketIO](https://flask-socketio.readthedocs.io/)：经常打不开，不过网上有很多它的翻译，可以查看
2. [fastapi-socketio](https://github.com/pyropy/fastapi-socketio)：文档都没有，不过网上有一些实战经验，可以进行参考
3. [Socket.IO](https://socket.io/zh-CN/)：最完善的 SocketIO 文档，不过服务端是 Nodejs，不是 Python，可以参考借鉴，客户端api在写前端时可能会用到
4. 推荐使用 logging 日志工具打印运行时的日志
5. 在登陆后在 token 中添加用户的权限信息，对于需要 token 的接口在 JWT 解码时进行权限检验和进行拦截，Flask 使用装饰器，FastApi 可以选择依赖注入，或者使用中间件拦截
6. FastiApi 可以使用自带的参数检验，Flask 应该引入 Flask-Restful，规范 RestfulAPi，同时使用其带的参数检验功能 [Flask-RESTful](http://www.pythondoc.com/Flask-RESTful/index.html)
7. 在框架中接入 redis 等进行缓存，读写很快，可以用于缓存验证码，以及一些经常读写的信息
8. 使用 pytest 编写单元测试，使用 pytest-cov 查看单测覆盖率（发送请求并传入参数，判断结果是否一致，好的产品单元测试覆盖率应该达到 85%）
9. 作为一个程序员怎么能没有一个属于自己的服务器呢？如果有点钱的话，大家可以去腾讯云、阿里云等云服务商购买一个便宜的云服务器（新人首单有优惠，要买就买久一点，一年100左右吧），同时将自己的项目部署到服务器上。服务器上请使用 `uWSGI` 或 `gunicorn` 启动项目，以获取更大的性能。（还可以用做部署定时爬虫，在线图床，个人网站等，大家可以自己尝试）
10. 部署项目环境弄起来非常的难受，建议大家学习一下 docker，使用 docker 将项目部署到服务器
11. 建议为代码编写注释以及使用 typehint，增加代码的可读性，在每天写完代码后，或者解决什么问题后，可以写一下笔记，方便以后再进行回顾
12. 本次项目给的时间应该会很长，对于 Flask 和 FastApi 这两个框架其实还有很多可以拓展的地方，[awesome-flask](https://github.com/humiaozuzu/awesome-flask) 和 [awesome-fastapi](https://github.com/mjhea0/awesome-fastapi) 列举了很多这些框架的相关精彩项目和插件，可以自主进行学习。同时大家也不要把自己局限于 Python上，应该多了解一些别的语言的相关写法，比如 Go，Java，或者前端。但是不允许**什么都不学**。本轮考核结束后，我会问一些你在这段时间内学到的东西和收获。

### 开源相关

这里我们推荐以下站点，可以关注一下：

1. 开源软件供应链点亮计划（开源之夏）：<https://summer-ospp.ac.cn/>
2. Google Summber of Code (gsoc)：<https://summerofcode.withgoogle.com/>
3. GLCC开源夏令营：<https://opensource.alibaba.com/>
4. 腾讯犀牛鸟开源人才培养计划：<https://opensource.tencent.com/summer-of-code>

除此之外，可以关注一下一些大厂的开源网站

1. 阿里开源：<https://opensource.alibaba.com/>
2. 腾讯开源：<https://opensource.tencent.com/>
3. Meta Open Source：<https://opensource.fb.com/>
4. Google Open Source：<https://opensource.google/>
5. Uber Open Source：<https://uber.github.io/#/>
6. 开源 - 美团技术团队：[https://tech.meituan.com/tags/%E5%BC%80%E6%BA%90.html](https://tech.meituan.com/tags/开源.html)
