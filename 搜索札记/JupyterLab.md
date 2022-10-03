# JupyterLab环境配置与使用（基于Windows Subsystem for Linux）

----

最近我们专业在组织进行金工实训，在人工智能环节，需要学习Python。学校使用的环境为：Ubuntu虚拟机+JupyterLab。Python学习的课程则为来自知乎大佬Pyhton-Jack[^1]在github上发布的Pyhton-100-Days[^2]的精简版Python-30-Days，教程内容详细，循序渐进，很适合初学者学习。由于该环节的实训只有1天，我们实训并没接触有关Python人工智能或者机器学习的相关内容，只是学习了一些Python的基本语法，但是这个Python环境引起了我的注意，再者本人对于Python学习也有一定兴趣，于是在网络上搜索了一些关于Python IDE环境的内容，发掘JupyterLab是使用较为广泛，功能强大的一个开发环境，免费使用不像PyCharm一样商业化的软件售价高昂，因此本人决定在我的计算机上也配置基于JupyterLab的开发环境。并且将我在配置环境当中遇到的问题和技巧记录下来。

## 1.Python环境配置

本人开始在在命令提示符输入`python`直接检查我是否已经安装，结果打开了Microsoft Store，跳转到了Python3.9的安装，于是转向Ubuntu虚拟机中安装Python，由于Python官网需要科学上网才能进入遂放弃，但本人搜索后发现原来Ubuntu自带了Pyhon😂，可以直接配置JupyterLab。下面说明一下在Ubuntu和Windows上的Python环境配置。

### 1.1 Ubuntu配置Python

#### 1.1.1 直接在Windows本地配置

在命令行中输入Python将跳转到Windows应用商店下载Python 3.9，由于Python官网需要科学上网才能访问，因此建议使用Windows应用商店下载，其下载目录默认为C盘。下载完成后在命令行输入`Python`检查安装完成情况。
安装完成后一般就可以进入Python命令行界面。

```cmd
C:\User\xxx\>python
Python 3.9.8 (tags/v3.9.8:bb3fdcf, Nov  5 2021, 20:48:33) [MSC v.1929 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

#### 1.1.2 使用WSL配置Python

WSL是指Windows Subsystem for Linux。若要使用WSL，首先打开设置，进入到`应用`拉到最底下`程序和功能`在其左边打开`启动或关闭Windows功能`，选择`适用于Linux的Windows子系统`，然后打开Windows应用商店下载`Ubuntu 20.04`等待安装，安装完成后打开进行配置用户名和密码，即可使用Ubuntu了。

## 2.什么是Jupyter

>Project Jupyter exists to develop open-source software, open-standards, and services for interactive computing across dozens of programming languages.[^3]
>Jupyter计划的存在是为了开发开放源码软件，开放标准并且为十几种编程语言提供互动式计算服务。

### 2.1 JupyterLab环境配置

无论是在Windows，WSL还是Linux中配置python+Jupyter Lab环境都是是比较简单的，配置完Python后在命令提示符中输入：

```cmd
pip install jupyterlab
```

等待安装完成。安装完成后使用命令

```cmd
jupyter lab
```

将会自动打开浏览器进入到jupyterlab。使用WSL的需要手动输入链接才能进入环境链接最后一段会显示token，复制输入进去才行。下次再从WSL中打开时可在地址栏中输入jupyterlab会自动提示，不需要再次输入token了。

## 3.一些使用提示

**1.依赖包版本号过低**
下面介绍一些在配置Jupyterlab中可能会遇到的问题及一些解决方法。
首先是在配置是可能会提示某些依赖包版本过低无法安装（这是本人在ubuntu环境下配置出现的问题）这时需要手动输入命令来升级提示版本过低的包

```bash
pip install 包名+版本号
```

再重新进行jupyterlab的安装这时可能需要把之前安装的依赖包一个个的卸载掉才能重新安装，使用如下操作来逐个卸载包。[^4]

```bash
sudo pip uninstall -y jupyter
sudo pip uninstall -y jupyter_core
sudo pip uninstall -y jupyter-client
sudo pip uninstall -y jupyter-console
sudo pip uninstall -y notebook
sudo pip uninstall -y qtconsole
sudo pip uninstall -y nbconvert
sudo pip uninstall -y nbformat
```

上述操作完成后

```bash
pip install jupyterlab
```

重新安装jupyterlab

**2.中文界面配置**[^5]
下面介绍如何将jupyterlab的语言改为中文在终端或命令行中输入

```bash
pip install jupyterlab-language-pack-zh-CN
```

安装完成之后还需要进入到jupyterlab工作环境中找到setting->language选择中文重新加载环境即可。

**3.更改工作目录**[^6]
由于jupyterlab默认的工作目录可能不符合一些人的要求我们可以手动更改工作目录。在Windows和Linux中操作相同。
首先要找到jupyterlab默认配置文件的位置,输入命令

```bash
jupyter lab --generate-config
```

给出配置文件位置后我们可以打开它，找到

```bash
## The directory to use for notebooks and kernels.
## c.NotebookApp.notebook_dir = ' '
```

将前面的`##`删除，并在`=' '`单引号中输入你想要的位置即可。

WSL配置会稍微麻烦点，如果你的位置不是在C盘的user下需要手动挂载一下你需要的盘到WSL中。

以D盘为例[^7]

```bash
sudo mkdir /mnt/D ##挂载D盘先/mnt下建立D盘挂载的文件夹
sudo mount -t drvfs D: /mnt/D ##挂载D盘在刚刚建立的目录
```

完成刚刚两个步骤即可想之前一样更改jupyterlab的工作目录了。

[^1]:[Python-Jack传道、授业、解惑，分享知识带来的快乐！]<https://www.zhihu.com/people/jackfrued>
[^2]:[Python - 100天从新手到大师]<https://github.com/jackfrued/Python-100-Days>
[^3]:[Project Jupyter]<https://jupyter.org/>
[^4]:[如何不残留地卸载jupyterlab]<https://blog.csdn.net/qq_41782124/article/details/115100718>
[^5]:[Jupyter Lab 3安装和使用（中文界面）]<https://blog.csdn.net/weixin_41103006/article/details/113363256>
[^6]:[jupyter lab中如何更改工作目录]<https://blog.csdn.net/goodgoodstudyddp/article/details/105191408>
[^7]:[Windows Subsystem for Linux （WSL）挂载移动硬盘U盘]<https://www.cnblogs.com/tl542475736/p/8486440.html>
