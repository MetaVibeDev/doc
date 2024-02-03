# 写在前面

各位开发同事好，这篇文章专门供于大家迈出第一步开发步骤。

+ VisionPro是一款全新的平台，对于纯软开发来说，是需要提前进行一些阅读和练手才能进行开发的。该文章会提供一些useful resource，供开发同事翻阅、练手，并且学习最佳实践。
+ 最早期的我们人数很少，开发控制在了4人以内。但是团队不在于大而在于精，对于编码的格式、提交的范式等的要求需要按照本文的要求来。严格的规范约束是为了培养大家日常的编码习惯以及协作风格，谨记在协同开发中，**代码是先给人看，然后才给机器运行的**。

# 仓库管理&提交规范

## 仓库

我们的远程仓库选用Github，所有的仓库(repository)都在Github的MetaVibeDev组织中。

+ 将开发机器和Github绑定的指导文档：[connecting-to-github-with-ssh](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)
+ 提交PR的指导文档：[creating-a-pull-request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)

## 提交规范

每一次提交，对于一个PR的描述，都是体现在我们的commit message中的。想想当你自己去review别人的代码的时候，是不是首先就会想知道他的这个提交是想解决什么问题或者上了什么特性？这些信息，我们都需要在commit message中以对外友好的形式来体现。这是非常非常重要的一点，同时也作为要求约束大家。

+ Git command cheat sheet: [cheat-sheet](https://training.github.com/downloads/zh_CN/github-git-cheat-sheet/)
+ 提交规范指导文档: [conventional-commits](https://www.conventionalcommits.org/zh-hans/v1.0.0/#%e7%ba%a6%e5%ae%9a%e5%bc%8f%e6%8f%90%e4%ba%a4%e8%a7%84%e8%8c%83)

## 合入流程

1. 每一笔提交的合入，都已经设置为不能直接push的。至少要有一人review过，rate过，才能够合入。
<br>这样要求有两个好处：
+ 把大家往全栈的方向上去培养，在发挥大家本身的技术水平同时，也拓宽一下技术视野
+ 把控质量，杜绝低级问题

2. 所有的独立对外接口，特别是公共能力，**必须有单元测试用例覆盖**。并且，一个单独PR大家应该首先要从单元测试用例开始审视PR所要实现的内容。
<br>这样要求有两个好处：
+ 培养大家开发者自测的能力，以及方便reviewer从接口调用、返回值等场景了解接口的使用方法。有时候我们的接口有可能是对他人交付的，从单元测试能够清晰直接的看到接口的用法。
+ 为迭代开发提供有效的防护保证，我们要力求尽量少在后续的修改中，引入问题影响了原有的接口的实现。

**作为提交人，必须主动跟进提交的合入情况。提了PR不算交差，合入合入合入！！**
# 开发相关（不同方向）

## 后台

后台开发采用微服务架构，云平台在开发阶段选择`AWS`或者`Azure`。由于是微服务，因此我们对于语言以及框架并没有强制的要求，大家可以选择自己熟悉的语言或者框架进行上手开发。但是鉴于我们现在要做`Unity`类的产品，所以我建议用`.Net Core`来开发我们的Web api或者rpc服务。我个人用的是`.Net 8`。

关于`.Net 8`的相关学习资源来链接如下：
+ [使用 ASP.NET Core 创建最小 API](https://learn.microsoft.com/zh-cn/aspnet/core/tutorials/min-web-api?view=aspnetcore-8.0&tabs=visual-studio)
+ [在 ASP.NET Core 中创建 gRPC 客户端和服务器](https://learn.microsoft.com/zh-cn/aspnet/core/tutorials/grpc/grpc-start?view=aspnetcore-8.0&tabs=visual-studio)

对于后台服务的部署形态以及交互方式，我们不能光写代码。我自己的一个习惯方式是在`draw.io`上去画图，这不作为一个要求。

## VisionOS

这个其实我也是刚开始入门，我最近做了一些资料收集的相关工作。所以这里先列出来我最近看过的一些资料。

我们在最初始的阶段，最重要的是要知道本地是否有VisionOS上运行的模拟器，能够直接在电脑上看到我们的Unity效果。

+ [VisionOS官网](https://developer.apple.com/visionos/)
+ [Unity-VisionOS开发指导](https://zhuanlan.zhihu.com/p/641226939)
+ [开发沉浸式App](https://zhuanlan.zhihu.com/p/660899626)

