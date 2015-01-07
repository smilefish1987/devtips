# 打造自己的Vim IDE开发环境

这两天在玩vagrant,用vagrant在自己的win7上搭建了几台linux环境，两台ubuntu14/64:一台是golang-dev,一台是web-dev,还有两台centos的服务器。样子大概如下图所示：

![](../images/vim1.jpg?raw=true)

首先看一下我ubuntu系统的版本和内核版本：

![](../images/vim2.jpg?raw=true)

再看一下我的vim的版本：

![](../images/vim3.jpg?raw=true)

言归正传，我们开始我们的搭建过程：

1.对ubuntu系统进行换源：

``` shell

a.$cd /etc/apt
b.$sudo mv sources.list sources.list.backup
c.$sudo vim sources.list
d.在文件中输入下面搜狐的源的内容：

  deb http://mirrors.sohu.com/ubuntu/ trusty multiverse universe restricted main
  deb http://mirrors.sohu.com/ubuntu/ trusty-updates multiverse universe restricted main
  deb http://mirrors.sohu.com/ubuntu/ trusty-backports multiverse universe restricted main
  deb http://mirrors.sohu.com/ubuntu/ trusty-security multiverse universe restricted main
  deb http://mirrors.sohu.com/ubuntu/ trusty-proposed multiverse universe restricted main
f.$sudo apt-get update

```
