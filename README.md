# Ember.js Sandbox

这是一个练习与挑战性质的开源项目，主题是围绕着 [Ember.js](http://emberjs.com/) 框架及其技术栈来学习和实践前端开发。

## 如何参与本项目？

我们对参与者没有任何限制，任何人都可以自由的复制或使用本项目的代码。如果你想要参与进来和我们一起练习，你可以：

1. 加入我们的 QQ 群：242650456（不强制，如果你不用 QQ 也可以仅使用 Github 全程参与）

1. 加入我们的 Github 组织，目前我们只接受 QQ 群成员成为本组织的成员，因此你需要在 QQ 群呼叫管理员来申请加入

1. Fork 这个项目的代码（这需要你有一个 Github 账号）

1. 在你的计算机上克隆你在上一步中 fork 的项目，然后安装运行这个项目所需要的依赖。具体如下：

    1. 首先确认 node 的版本不小于 4，最好是 4.5 以上（也就是目前官方的长期稳定版本）
    1. 其次确认 npm 的版本最好是 3 以上（会给你更好的性能）
    1. 全局安装以下依赖：
        - `npm install --global bower`
        - `npm install --global ember-cli`
        - `npm install --global phantomjs-prebuilt`（可选，只影响测试相关的代码）
    1. 在项目的目录下安装以下依赖：
        - `npm install`
        - `bower install`
    1. 运行项目：`ember server`，然后用浏览器打开地址 `http://localhost:1337`

以上步骤应足以帮助你在本地运行这个项目了，在此过程当中如果出现问题，可以在本项目中创建 issue 来描述你的情况并获取来自项目成员的帮助。

如果你要参与特定的某一个练习，以下是你应该知道的：

1. 每一个独立的练习都有一个独立的分支，相互之间不会干扰

1. 在本文档后面列出了目前可以参与的练习介绍，你可以找到练习所处的分支的名称

1. 在本地切换到对应的分支然后运行项目，接着你就可以写下你自己的代码了

1. 基本上每一个练习都会有一个前期介绍视频和一个后期解答视频，遇到不明白的地方可以先参考这些视频

1. 代码编写完之后提交、推送、最后创建 PR

1. PR 创建之后我们就会为你的答案进行代码审核，帮助你进一步理解练习的目的和意义，同时提高代码的质量

以上就是本项目的基本流程，有变化的地方我们都会在对应的视频中告知。如果你对 Github 协作的过程不够清楚，你可以观看系列视频的第二期，里面有完整的操作流程。

## 练习及视频列表

<details>
    <summary>第 1 期：如何开始</summary>

- 练习：无
- 视频：[Youtube](https://www.youtube.com/watch?v=GRVVYxJ0eqg) | [哔哩哔哩](http://www.bilibili.com/video/av6451274)
</details>

<details>
    <summary>第 2 期：在 Github 上协作</summary>

- 练习：无
- 视频：[Youtube](https://www.youtube.com/watch?v=Z6N1HyhEPKo) | [哔哩哔哩](http://www.bilibili.com/video/av6452647)
</details>

<details>
    <summary>第 3 期：在父子组件之间传递状态</summary>

- 练习：
    - 题目：[分支 003-begin](https://github.com/very-geek/ember-sandbox/tree/003/begin)
    - 答案：[分支 003-final](https://github.com/very-geek/ember-sandbox/tree/003/final)
- 视频：
    - 介绍：[Youtube](https://www.youtube.com/watch?v=AISmLOsWcfY) | [哔哩哔哩](http://www.bilibili.com/video/av6454526)
    - 总结：
        1. 数据绑定专题：[Youtube](https://www.youtube.com/watch?v=KMLsOpzg2hg) | [哔哩哔哩](http://www.bilibili.com/video/av6584546)
        2. [Youtube](https://www.youtube.com/watch?v=29tlYVE3mqo) | [哔哩哔哩](http://www.bilibili.com/video/av6629356)
</details>

<details>
    <summary>【番外篇】：如何实现 Github API OAuth2 鉴权</summary>

- 练习：无
- 视频：[Youtube](https://www.youtube.com/watch?v=doglVsRI2-w) | [哔哩哔哩](http://www.bilibili.com/video/av6478153)
</details>

<details>
    <summary>第 4 期：使用 Service 进行状态管理和交互</summary>

- 练习：本期练习的主要目标是创建一个全局的滑动式菜单，最终效果可以参考：[ember-sandbox-004.surge.sh](http://ember-sandbox-004.surge.sh)
    1. 菜单本身可以有两种解法（都可以尝试一下）：
        - 可以是一个组件，放置在 `application/template.hbs` 的模版内
        - 可以是一个独立的模板，通过 `application/route.js` 的 `renderTemplate` 钩子方法配合 `this.render` 方法进行渲染
    1. 菜单的弹出状态可以用 CSS 来控制（动画效果可选），但最好不要用 jQuery 来操作 CSS 类，而是应该绑定一个状态变量来切换
    1. 控制菜单弹出状态的方法应该可以随处使用（通过 Service 依赖注入实现），需要实现三个方法：显示，隐藏，切换
    1. 绑定控制方法的交互组件（比如按钮）可以根据当前菜单的状态切换 disabled 状态（可选）
        - 这些方法应该能够接收执行上下文（context），以便在任何地方调用的时候都可以正确的执行（可选）
    1. 在初始化的时候直接注入该 Service 到常用的组件里去（比如 Routes / Controllers / Components 等，可选）
    - 答案：[分支 004-final](https://github.com/very-geek/ember-sandbox/tree/004/final)
- 视频：
    - 总结：[Youtube](https://www.youtube.com/watch?v=QrNypFwF8Po) | [哔哩哔哩](http://www.bilibili.com/video/av6693855)
</details>

<details>
    <summary>第 5 期：loading 和 error 子状态</summary>

- 练习：本期练习的主要目的是理解 loading / error 子状态的定义和使用，最终效果可以参考：[ember-sandbox-005.surge.sh](http://ember-sandbox-005.surge.sh)
    - 答案：[分支 005-final](https://github.com/very-geek/ember-sandbox/tree/005/final)
- 视频：
    - 总结：[Youtube](https://www.youtube.com/watch?v=acmOpirWccc) | [哔哩哔哩](http://www.bilibili.com/video/av7587044)
</details>
