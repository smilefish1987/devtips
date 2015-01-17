# ZSH使用指南

1.安装zsh
``` shell
sudo apt-get install zsh

```

2.切换zsh

a.通过命令修改

``` shell
chsh -s /usr/bin/zsh

```
b.修改/etc/passwd文件中对应用户最后的shell变量

3.安装oh-my-zsh 
``` shell

wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh

```
4.在用户主目录下的.zshrc文件中配置zsh

a.新增一下内容：

``` shell

alias cls='clear'
alias ll='ls -l'
alias la='ls -a'
alias javac="javac -J-Dfile.encoding=utf8"
alias grep="grep --color=auto"
alias -s html=vim   # 在命令行直接输入后缀为 html 的文件名，会在 TextMate 中打开
alias -s py=vim       # 在命令行直接输入 python 文件，会用 vim 中打开，以下类似
alias -s js=vim
alias -s c=vim
alias -s java=vim
alias -s txt=vim
alias -s gz='tar -xzvf'
alias -s tgz='tar -xzvf'
alias -s zip='unzip'
alias -s bz2='tar -xjvf'

```

5.安装autojump

``` shell
git clone git://github.com/joelthelion/autojump.git

```
进入目录后执行

``` shell
./install.py

```

然后把一下代码加入.zshrc

``` shell

[[ -s /home/smilefish1987/.autojump/etc/profile.d/autojump.sh ]] && source /home/smilefish1987/.autojump/etc/profile.d/autojump.sh

```

最后把/home/smilefish1987/.autojump/bin 加入环境PATH就可以了


5.zsh的使用说明：

a.git：当你处于一个 git 受控的目录下时，Shell 会明确显示 「git」和 branch，如上图所示，另外对 git 很多命令进行了简化，例如 gco=’git checkout’、gd=’git diff’、gst=’git status’、g=’git’等等，熟练使用可以大大减少 git 的命令长度，命令内容可以参考~/.oh-my-zsh/plugins/git/git.plugin.zsh

b.强大的历史纪录功能，输入 grep 然后用上下箭头可以翻阅你执行的所有 grep 命令

c.智能拼写纠正，输入gtep mactalk * -R，系统会提示：zsh: correct ‘gtep’ to ‘grep’ [nyae]? 比妹纸贴心吧，她们向来都是让你猜的……

d.各种补全：路径补全、命令补全，命令参数补全，插件内容补全等等。触发补全只需要按一下或两下 tab 键，补全项可以使用 ctrl+n/p/f/b上下左右切换。比如你想杀掉 java 的进程，只需要输入 kill java + tab键，如果只有一个 java 进程，zsh 会自动替换为进程的 pid，如果有多个则会出现选择项供你选择。ssh + 空格 + 两个tab键，zsh会列出所有访问过的主机和用户名进行补全

e.智能跳转，安装了autojump之后，zsh 会自动记录你访问过的目录，通过 j + 目录名 可以直接进行目录跳转，而且目录名支持模糊匹配和自动补全，例如你访问过hadoop-1.0.0目录，输入j hado 即可正确跳转。j –stat 可以看你的历史路径库。

f.目录浏览和跳转：输入 d，即可列出你在这个会话里访问的目录列表，输入列表前的序号，即可直接跳转。

g.在当前目录下输入 .. 或 … ，或直接输入当前目录名都可以跳转，你甚至不再需要输入 cd 命令了。

h.通配符搜索：ls -l **/*.sh，可以递归显示当前目录下的 shell 文件，文件少时可以代替 find，文件太多就歇菜了。

i.zsh所有活动的shell窗口共享命令的历史，而不是bash一样，每个bash有自己的命令历史

j.环境变量的展开 

``` shell

-> $PWD<TAB>
-> $/home/smilefish1987

```


参考文章：
[终极 Shell](http://macshuo.com/?p=676)
