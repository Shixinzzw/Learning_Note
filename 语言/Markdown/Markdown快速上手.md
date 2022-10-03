# Markdown 快速上手

本文旨在介绍Markdown标记语言，及快速上手实现包含公式，代码，图片等丰富内容的文本编写

<center>Write by Shixin</center>

## 目录

[TOC]

### 1.Markdown介绍

#### 1.1 Markdown是什么

 引用Markdown官方教程的话来说：
>Markdown 是一种轻量级的标记语言，可用于在纯文本文档中添加格式化元素。Markdown 由 John Gruber 于 2004 年创建，如今已成为世界上最受欢迎的标记语言之一。
>专注于文字内容；
纯文本，易读易写，可以方便地纳入版本控制；
语法简单，没有什么学习成本，能轻松在码字的同时做出美观大方的排版。

#### 1.2 为什么要选择Markdown其与Word，WPS等软件有何区别

Markdown其标记文本的属性，使其极易用快速简单的语法来实现多内容的文章书写而不需要在意其排版或者字体颜色大小等内容。

Markdown不同于Word，WPS等工具，其为纯文本而生，文字内容不会包括其字体格式等多种内容，易于阅读便于使用。Markdown 语法的首要设计目标是尽可能易读。基于这个目标，Markdown 格式的文档能够以纯文本形式原样发布，而不会看起来像被填满了标签或格式化指令（正像你每次从网站或者Word中复制的内容总是附带了各种字体格式）。

#### 1.3 为何要选择Markdown

> 当你可以通过按下界面中的按钮来设置文本格式时，为什么还要使用 Markdown 来书写呢？使用 Markdown 而不是 word 类编辑器的原因有：
>
>- Markdown 无处不在。StackOverflow、CSDN、掘金、简书、GitBook、有道云笔记、V2EX、光谷社区等。主流的代码托管平台，如 GitHub、GitLab、BitBucket、Coding、Gitee 等等，都支持 Markdown 语法，很多开源项目的 README、开发文档、帮助文档、Wiki 等都用 Markdown 写作。
>- Markdown 是纯文本可移植的。几乎可以使用任何应用程序打开包含 Markdown 格式的文本文件。如果你不喜欢当前使用的 Markdown 应用程序了，则可以将 Markdown 文件导入另一个 Markdown 应用程序中。这与 Microsoft Word 等文字处理应用程序形成了鲜明的对比，Microsoft Word 将你的内容锁定在专有文件格式中。
>- Markdown 是独立于平台的。你可以在运行任何操作系统的任何设备上创建 Markdown 格式的文本。
>- Markdown 能适应未来的变化。即使你正在使用的应用程序将来会在某个时候不能使用了，你仍然可以使用文本编辑器读取 Markdown 格式的文本。当涉及需要无限期保存的书籍、大学论文和其他里程碑式的文件时，这是一个重要的考虑因素。

### 2.Markdown可以干什么

可以编写包含公式，代码，图片在内的多种内容的文章而无需使用复杂排版软件或者繁杂操作仅需使用简单的Markdown语法即可实现。诸多平台支持Markdown格式的文档可以快速完成文章编写上传。

### 3.Markdown编写环境配置

使用 Viusal Studio Code 与相关插件配置 Markdown 编写环境。

Visual Studio Code 是由 Microsoft 基于 json 开发的一款开源免费的跨平台代码编辑器

#### 3.1 Visual Studio Code的安装

进入 Visual Studio 官网找到 Visual Studio Code 的链接入口（你也可以直接搜索 Visual Studio Code 来进入其网站）[https://code.visualstudio.com/]

![visualstuiocode_offical](../../图床/Markdown/visualstudiocode_official.png)

一般网站会自动识别电脑的系统和架构直接点击[Download for Windows]即可。注：建议选择Stable版本，Insider版本为测试开发版，稳定性差，不建议一般用户选择。

下载后按照一般软件的安装步骤进行安装即可。

安装完成后可打开软件可见到如下界面：

![vscode_home](../../图床/Markdown/vscode.png)

不过由于我已经安装并配置好了所以内容会和你们有一些不太。启动时为英文界面，下方会弹出一个通知提示你安装汉语插件，点击Install，待安装完成后程序会重新加载一次，这下你的Visual Studio Code 已经安装好了。

#### 3.2 下载相关插件

Visual Studio Code 有着及其丰富的插件库，且查询安装过程简便易于上手。插件极大的拓展了软件的功能性，你甚至可以将其打造成专属你个人的IDE编程环境。

##### 3.2.1 Markdown 插件

![extension](../../图床/Markdown/vscode_extension_home.png)

上方标记的地方即为扩展，应用商店点击后可以看到如下内容：

![store](../../图床/Markdown/vscode_extension_empty.png)

我们在搜索框中输入markdown，查找我们需要的插件

我们选择下载量最多的Markdown插件

![down](../../图床/Markdown/vscode_extension_down.png)

下载好标记的插件，待安装完成后重新载入软件即可。
到此我们的Markdown编写环境就配置好了！！！

#### 3.3 进行渲染测试

环境配置完成后当然要尝试使用一下我们配置的环境啦。首先打开Visual Studio Code 。

![files](../../图床/Markdown/files.png)

点此打开一个文件夹作为我们的笔记本，可以将不同内容的种类的笔记按照文件夹分门别类的存放。
比如，我在Onedrive文件中建立了Note文件夹其打开后的文件结构如下图所示。

![filesOFmy](../../图床/Markdown/filesOFmy.png)

结构层次清晰，便于查找。

下面请你打开你的文件夹后开始尝试建立一个Markdown文件吧。

![filesnew](../../图床/Markdown/filesnew.png)

点击该处新建一个文件`FristMarkdownNote.md`
注意：Markdown文件的后缀为```.md```

文件建立好后正式开始你的Markdown笔记之旅吧！！！

按照图片中的内容输入进去在点击下面的那个带放大镜的文件图标就可以实时看到渲染的效果了，你可以一边写一边看实时的效果。

![preview](../../图床/Markdown/preview.png)

正如下面那样

![clik](../../图床/Markdown/test.png)

### 4.其他内容

时间仓促，待补，详细见
<https://github.com/Shixinzzw/personblog_shixin.git>
