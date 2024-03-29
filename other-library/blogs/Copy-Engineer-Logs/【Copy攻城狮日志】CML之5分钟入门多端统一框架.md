*Created by **[huqi](https://github.com/hu-qi)** at 2019-4-6 21:57:17*    
*Updated by **[huqi](https://github.com/hu-qi)** at 2019-4-7 22:54:55*


![clipboard.png](https://segmentfault.com/img/bVbqW9P)
↑开局一张图，故事全靠编↑
# CML是啥？变色龙又是啥？
自从有小程序以来，小程序的第三方框架便孕育而生，从原始时代的只基于微信小程序多如今多端统一开发框架，可以说前端技术从2018年到2019年又发生了天翻地覆的变化。感觉现在和圈内人吹水，不蹦出几个诸如megalo、Taro、uni-app之类的新词都感觉没法混，哈哈。今天逛掘金的时候，偶然间打开了@Chameleon社区 发布的[我们用5分钟写了一个跨多端项目](https://juejin.im/post/5ca2de0f51882543d65287a7),Chameleon刚刚开源的时候就有关注过，不过一直没有入手，看到开头这个视频教程就有了尝试的冲动(相比某个开源的商业化项目出的教程还需支付一定费用已经很良心了)，三天节假日也已经过去两天了，是该在Copy&Paste一下，不然连这个CP的技能冷却时间会变得更长。
一句话介绍CML：**cml([Chameleon](https://github.com/didi/chameleon) 变色龙） 作为真正让一套代码运行多端的框架，提供标准的MVVM模式，统一开发各类终端。**
为什么要入手Chameleon？我觉得Chameleon的思想觉得我们学习，毕竟多端统一对前端来说是个大趋势。

![https://segmentfault.com/img/bVbqXfK)

# 五分钟真的能入门吗？
答案不肯定的，当然也不是否定的，要根据用户的实际场景实际情况，假如我连前端开发环境都木有，别说入门，就算是装个Cli环境甚至Node环境可能都要花费好几分钟；假如我掌握了一定技巧且有良好的环境，Copy&Paste也轻而易举的事。废话不多说，前提是您至少要用node环境。
- 安装node环境
   详见@i5ting 的文章：[狼叔：如何正确的学习Node.js](https://segmentfault.com/a/1190000013933520)

- 全局安装Chameleon构建工具
    ```
    npm i -g chameleon-tool
    ```
 我已安装node@10.14.1、chameleon-tool@0.0.16(展示没看到更新命令，最新[0.1.1](https://github.com/didi/chameleon/blob/master/CHANGELOG.md)，并且暂不支持yarn、cnpm等安装方式)
    ![clipboard.png](https://segmentfault.com/img/bVbqXgL)
- 创建项目(可选参数:project、page、component)，输入项目名会自动创建项目文件并安装依赖

    ```
    cml init
    ```
    说实话，如果npm不给力，别说5分钟，可能15分钟过去了估计还卡在npm installing... 
    ![clipboard.png](https://segmentfault.com/img/bVbqXhN)
    那就先看看目录结构
        ├── chameleon.config.js                 // 项目的配置文件
        ├── dist                                // 打包产出目录(build之后显示)
          ├── alipay                            // 支付宝小程序代码(build之后显示)
          ├── baidu                             // 百度小程序代码(build之后显示)
          ├── wx                                // 微信小程序代码(build之后显示)
        ├── mock                                // 模拟数据目录(目前内置api和template文件夹)
        ├── node_modules                        // npm包依赖
        ├── package.json                        // 包文件
        ├── npm-shrinkwrap.json                 // 锁定依赖版本
        └── src                                 // 项目源代码
            ├── app                             // app启动入口(包含app.cml)
            ├── assets                          // 静态文件夹(包含默认images)
            ├── components                      // 组件文件夹(包含默认组件)
            ├── pages                           // 页面文件夹(包含默认页面)
            ├── router.config.json              // 路由配置
            └── store                           // 全局状态管理(类似Vuex)
    .cml文件vscode默认是不支持的，不过已经有拓展可以下载
    
    ![clipboard.png](https://segmentfault.com/img/bVbqXiy)
    
    如果npm依赖安装不成功，可以手动安装；或者切换成taobao源
    
  ![clipboard.png](https://segmentfault.com/img/bVbqXiz)
- 通过运行help命令查看chameleon的帮助提示

    ```
    cml -h
    
      Usage: chameleon [command] [options]

  Options:

    -V, --version     输出版本号
    -h, --help        输出使用信息

  Commands:

    init [options]    初始化变色龙(chameleon)项目的模板
    dev [options]     启动开发模式
    build [options]   启动构建模式
    server [options]  开发环境服务器的工具
    web [options]     Web项目的工具
    weex [options]    Weex项目的工具
    wx [options]      微信小程序项目的工具
    baidu [options]   百度小程序项目的工具
    alipay [options]  支付宝小程序项目的工具
    ```
- 运行dev命令启动dev环境，同时浏览器会打开彩蛋

    ```
    cml dev web
    ```
   
 ![clipboard.png](https://segmentfault.com/img/bVbqYBt)

- 当然，也许不一定一帆风顺，遇到问题先本地排查，实在解决不了再去chameleon官方仓库翻翻issue，或者直接提出issue。
- 既然是Copy&paste，那就直接把@jalonjs 大佬创建的[cml-first-demo](https://github.com/jalonjs/cml-first-demo)直接复制过来，一边看文档一边敲代码，尽走上从入门到放弃的康庄大道！


