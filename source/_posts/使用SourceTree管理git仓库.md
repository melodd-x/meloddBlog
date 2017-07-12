---
title: 使用SourceTree管理git仓库
date: 2017-06-13 14:57:07
tags: git
categories: 教程
---

<img src="/images/03/01.png" class="full-image" />

{% note info %} 使用Terminal或CMD管理git仓库太麻烦,我们可以使用SourceTree这样的图形界面软件来轻松的管理我们的git仓库{% endnote %}

<!-- more -->





好,首先不管使用Terminal还是SourceTree管理git仓库,首先我们得有仓库可以管理.

{% note success %} 我们先去github上面新建一个我们的仓库 {% endnote %}
登录自己的github帐号,然后点击右上角的加号,选择你一个选项:new repository(一个新的仓库)
![](/images/03/03.png)
接下来就是设置我们的新仓库
![](/images/03/04.png)
> 因为我的项目是使用框架搭建起来的,里面有用到一些公共npm依赖包,他们都在node_modules文件夹下,所有,我选择过滤node_modules,如果一不小心写错的话,你还是可以自己去仓库里面的.gitgnore文件下更改.

创建好我们的仓库了,我们只需要我们远程的仓库的地址就可以,现在clone下我们的仓库地址就可以了,
![](/images/03/05.png)

### github仓库我们已经建立好了,接下来,该SourceTree登场
{% note success %} SourceTree的下载和安装过程,在这里我就不说了,一直next就可以,安装过程中需要你科学上网,注册一个他们的帐号. {% endnote %}

#### 和使用Terminal一样,第一步就是clone我们的远程仓库到本地来
点击新仓库,然后从URLclone
![](/images/03/06.png)
把你的远程仓库的地址粘贴到这里
![](/images/03/07.png)
你的仓库地址
![](/images/03/09.png)
默认本地仓库地址是:`/Users/WXK/xiaozhangzhang`
我在自己的桌面上新建了一个同名的文件夹,本地仓库的地址改成了桌面的同名文件夹
你们自己随意.
![](/images/03/08.png)
本地仓库操作界面
![](/images/03/11.png)

这个时候,你就可以把你的项目考进本地仓库里,或者在这直接开始新建你的工程
![](/images/03/12.png)
#### 这时候,我刚把我的项目都考进了我的本地仓库下
Atom编译器里绿色的都表示我在工作区新添加的文佳,但是没有加到本地仓库的缓存区里面
![](/images/03/13.png)
![](/images/03/14.png)
![](/images/03/15.png)

#### 这时候提交,上传到本地仓库
![](/images/03/17.png)
这时,你的项目已经存到了你的本地仓库了,但是还需要push到你的远程github仓库上.
![](/images/03/18.png)
![](/images/03/19.png)
`git push oringin master` 完成,你可以去github仓库,查看你刚刚上传的代码了
![](/images/03/20.png)
