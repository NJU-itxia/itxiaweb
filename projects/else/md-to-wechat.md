# MD转推送小工具

 Markdown推广计划介绍

## 一、Markdown是什么、怎么用

我们的网站已经存档了一份Markdown教程，详情请参看这里：[Markdown教程（IT侠存档）](https://itxia.club/guide/markdown/manual.htm)

## 二、注意Markdown的规范

由于我们想要尽可能地统一社团内的Markdown规范，以便后续各类功能的接入，因此基本采用上述教程的规范。事实上，Markdown有很多扩展规范，所以请注意不要混用哦

## 三、我们用Markdown可以做什么

通过Markdown，我们最好的好处是 **可以快速编辑，从而统一化排版样式，达到快速复用排版样式、专注内容的目的** 。

具体的应用见下方（逐步更新）

### 1. 互助文档、教程的可移植性

我们可以搬运腾讯文档的[互助群文档](https://docs.qq.com/doc/DVHVucUpQaE9rbXVO)到语雀、知乎、简书、GitHub乃至任何支持Markdown的平台，方便移植。

### 2. 教程向推送转化

通过Markdown撰写的教程具有很好的移植性，因此我们可以通过转换工具直接将Markdown转换为推送。目前初步的应用已经搭建完毕，请查看[IT侠微信公众号格式化工具](https://itxia.club/tools/mdcvt/)

该工具可以将样式通过CSS分离开来，内容以Markdown填充。具体可以参看该工具自带的样例。

此工具部署于此，使Geek或Web供稿至OP组高效转换为推送成为可能。

### 3. 自助教程、Bot计划

我们可以在群内或者网页上设置机器人。然而机器人所需要的知识需要来自我们维护的知识库，因此Markdown化我们的文档有利于读取格式。一般的word文档等有一定复杂性，而Markdown由于结构清晰的特点，非常适合搭建我们的知识库。

举个例子，Markdown的下面这段结构非常方便读取：

```markdown
# 电脑坏了
## 有钱
### 想修
请去售后维修
### 不想修
请重买
## 没钱
### 想修
请联系IT侠先尝试维修
### 不想修
（机器人退出服务）
```
上述Markdown结构其实可以读取为一个树形结构。

## 四、推荐入门可用的软件

这里推荐的都可以Windows、Mac OS、Linux上使用。

1. 👍[Typora](https://www.typora.io/)：专用的Markdown编辑器，可以严格限制使用Github规范的Markdown，并且插入本地图片管理很方便。
2. [VSCode](https://code.visualstudio.com/) + Markdown Preview Enhanced插件：比较贴合程序员的使用习惯。

## 五、Markdown转推送

目前构想是拆成两部分：

1. Markdown转至微信推送的转换（杨子航已完成）
2. 样式设计，优化推送的展示样式

## 六、具体需求

### 20190911更新

（备选）经过调研和实践，建议将微信格式化工具改为使用以下项目：
https://github.com/lyricat/wechat-format

### 20200101更新

为主题添加标准格式“标准模式”，使得主题模式更加适用于教程推送。

mdcvt的主题修改方式：

1. `tools/mdcvt/pageThemes/*.css`为主题文件，里面采用CSS选择器的方式进行设置。
2. 文件`tools/mdcvt/js/index.js`中的`PageTheme.prototype.bindEvt`可以修改mdcvt的选择条目，从而添加主题

### 20200120更新

+ 添加了多个美化主题
+ 丰富了链接引用的文末自动处理格式
+ 与推送进行适配，解决了几个小bug

实际改造过程中发现，采用yzh在`tools/mdcvt/index.html`里直接添加修改的方式更加简单粗暴容易维护，修改`tools/mdcvt/js/index.js`很容易出错。
