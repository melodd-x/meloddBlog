---
title: 打造Mac下的终极Shell
date: 2017-05-13 21:24:08
tags: Shell
categories: 教程
---

<img src="/images/Shell/Shell1.png" class="full-image" />
{% note info %} 还在用Mac自带终端的同学们,你们有福了,我来拯救你们了. {% endnote %}
<!-- more -->

## 正文开始
> 上图就是系统默认的终端,可能你们也是这样的,下图就是我配置完的
> ||V||

![](/images/Shell/Shell2.png)

> 好了!  炫耀完毕,再见.


### 首先:介绍下几个概念?

#### -- Shell
> 是指“提供使用者使用界面”的软件（命令解析器）,它接收用户命令，然后调用相应的应用程序.
> Shell是Linux/Unix的一个外壳，你理解成衣服也行。它负责外界与Linux内核的交互，接收用户或其他应用程序的命令，然后把这些命令转化成内核能理解的语言，传给内核，内核是真正干活的，干完之后再把结果返回用户或应用程序。

基本上shell分两大类：
一：图形界面shell（Graphical User Interface shell 即 GUI shell）
例如：应用最为广泛的 Windows Explorer （微软的windows系列操作系统），还有也包括广为人知的 Linux shell，其中linux shell 包括 X window manager (BlackBox和FluxBox），以及功能更强大的CDE、GNOME、KDE、 XFCE。
二：命令行式shell（Command Line Interface shell ，即CLI shell）
例如：
bash / sh / ksh / csh（Unix/linux 系统）
（MS-DOS系统）
cmd.exe/ 命令提示字符（Windows NT 系统）
Windows PowerShell（支持 .NET Framework 技术的 Windows NT 系统）
传统意义上的shell指的是命令行式的shell，以后如果不特别注明，shell是指命令行式的shell。
文字操作系统与外部最主要的接口就叫做shell。shell是操作系统最外面的一层。shell管理你与操作系统之间的交互：等待你输入，向操作系统解释你的输入，并且处理各种各样的操作系统的输出结果。

想知道你的系统有几种shell，可以通过以下命令查看：
`cat /etc/shells`
显示如下：
```bash
/bin/bash
/bin/csh
/bin/ksh
/bin/sh
/bin/tcsh
/bin/zsh
```

在 Linux 里执行这个命令和 Mac 略有不同，你会发现 Mac 多了一个 zsh，也就是说 OS X 系统预装了个 zsh，这是个神马 Shell 呢？

目前常用的 Linux 系统和 OS X 系统的默认 Shell 都是 bash，但是真正强大的 Shell 是深藏不露的 zsh， 这货绝对是马车中的跑车，跑车中的飞行车，史称『终极 Shell』，但是由于配置过于复杂，所以初期无人问津，很多人跑过来看看 zsh 的配置指南，什么都不说转身就走了。直到有一天，国外有个穷极无聊的程序员开发出了一个能够让你快速上手的zsh项目，叫做「oh my zsh」，Github 网址是：https://github.com/robbyrussell/oh-my-zsh。这玩意就像「X天叫你学会 C++」系列，可以让你神功速成，而且是真的。

#### -- 终端模拟器
> 就是用来跑Shell的工具

Mac自带的是terminal.app ,就是Terminal
就是它
![](/images/Shell/Shell3.png)

然而还有个比Terminal功能强大更多的iTerm2
![](/images/Shell/Shell4.png)

#### 所以
##### 到这,你们应该大致的明白了,你们用的就是`terminal` + `bash`
##### 而我用的是`iTerm2` + `oh my zsh` + `iterm2-colors-solarized` + `Powerline fonts` + `agnoster.zsh-theme`
![](/images/Shell/Shell5.jpg)

### 开始安装
#### iTerm2
- 下载安装iTerm2
- [去官网下载](http://www.iterm2.com/)
- 然后自己双击打开安装

#### Oh My Zsh
- 先打开终端,输入`zsh --version` 查看zsh版本和是否有zsh,有就继续,  Mac自带.
- 上文说了zsh配置不是人干的事,我们可以用「oh my zsh」来帮助我们
- 安装方法一:
> via curl


```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
- 安装方法二:
> via wget


```bash
sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```
- 把 zsh 设置成默认的 shell:`chsh -s /bin/zsh`
- 接下来我们要修改zsh主题
- [官方文档](https://github.com/robbyrussell/oh-my-zsh)

#### agnoster
- 查看你当前zsh用的什么主题`echo $ZSH_THEME`
- 查看所有的zsh主题 先进入themes目录`~/.oh-my-zsh/themes`,再`ls`查看
![](/images/Shell/Shell7.png)
- 修改zsh主题`vim ~/.zshrc`
![](/images/Shell/Shell8.png)
- 按`i`健进入插入模式编辑,`esc`进入正常模式,输入`:wq`保存退出 ---->[vim 命令详解](http://www.cnblogs.com/usergaojie/p/4583796.html)
- 好了,重启下iTerm2,如果你的结果是这样的
![](/images/Shell/Shell9.png)
- 这就说明你电脑里没有Powerline fonts字体,这个字体必须需要这种字体支持
- 接下来安装字体

#### Powerline fonts
- 进入你想放字体文件的目录
- 克隆字体库到当前目录下:
```bash
git clone https://github.com/powerline/fonts.git
```
- 进入fonts文件夹,并且安装字体
```bash
cd fonts
./install.sh
```
- 好了,字体安好了,就设置iTerm2让他用这种字体,打开偏好设置
![](/images/Shell/Shell10.png)
![](/images/Shell/Shell11.png)
![](/images/Shell/Shell12.png)
![](/images/Shell/Shell13.png)
- 好了字体能正确显示,但是你们可能是这种颜色配置,
![](/images/Shell/Shell14.png)
- 你们看着不难受的话,今天就到这了,如果感觉颜色不好看的话,可以自己换色啊

#### iterm2-colors-solarized
- 你们可以先试试其他的颜色配置方案
![](/images/Shell/Shell15.png)
- 或者使用Solarized配色,这个你们需要自己去下载,然后点击`import`导入就可以了
- iterm2-colors-solarized [下载地址](https://github.com/altercation/solarized/tree/master/iterm2-colors-solarized)
![](/images/Shell/Shell16.png)

### 好了,可以拿去炫耀了
![](/images/Shell/Shell2.png)


## 正文结束

>如果您看了本篇博客,觉得对您有所收获，请点击右下角的 ~~[分享]~~，没有！
如果您想转载本博客，请注明出处
如果您对本文有意见或者建议，欢迎 ~~[留言]~~，留个屁！
感谢您的阅读，请关注我的后续博客
