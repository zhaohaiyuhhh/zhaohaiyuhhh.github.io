什么是Linux系统，Linux有哪些部分


1.Linux是一套免费使用和自由传播的类Unix操作系统，是一个基于POSIX和UNIX的多用户、多任务、支持多线程和多CPU的操作系统。它能运行主要的UNIX工具软件、应用程序和网络协议。它支持32位和64位硬件。Linux继承了Unix以网络为核心的设计思想，是一个性能稳定的多用户网络操作系统。
2.Linux操作系统诞生于1991 年10 月5 日（这是第一次正式向外公布时间）。Linux存在着许多不同的Linux版本，但它们都使用了Linux内核。Linux可安装在各种计算机硬件设备中，比如手机、平板电脑、路由器、视频游戏控制台、台式计算机、大型机和超级计算机。

3、Linux都用在了哪些地方：和Linux 一样，Windows系列是完全的多任务操作系统。它们支持同样的用户接口、网络和安全性。但是，Linux和Windows的真正区别在于，Linux 事实上是Unix的一种版本，而且来自Unix的贡献非常巨大。是什么使得Unix如此重要？不仅在于对多用户机器来说，Unix是最流行的操作系统，而且在于它是免费软件的基础。在Internet上，大量免费软件都是针对Unix系统编写的。由于有众多的Unix厂商，所以Unix也有许多实现方法。没有一个单独的组织负责Unix的分发。现在，存在一股巨大的力量推动Unix社团以开放系统的形式走向标准化。另一方面Windows系列是专用系统，由开发操作系统的公司控制接口和设计。在这个意义上这种公司利润很高，因为它对程序设计和用户接口设计建立了严格的标准，和那些开放系统社团完全不一样。一些组织正在试图完成标准化Unix程序设计接口的任务。特别要指出的是，Linux完全兼容POSIX.1标准。

4、Linux和Windows有什么区别，Linux有哪些优势   
    Linux提供了相对于Windows更好的安全性能，只有一个方面例外（确信度）。
无论按照什么标准对Windows和Linux进行评估，都存在一定的问题：每个操作系统都不止一个版本。微软的操作系统有Windows98、 Windows NT、 Windows 2000、 Windows 2003 Server和Windows CE，而Linux的发行版由于内核（基于2.2、2.4、2.6）的不同和软件包的不同也有较大的差异。我们本文所使用的操作系统，都是目前的技术而不是那些"古老"的解决方案。
用户需要记住：Linux和Windows在设计上就存在哲学性的区别。Windows操作系统倾向于将更多的功能集成到操作系统内部，并将程序与内核相结合；而Linux不同于Windows，它的内核空间与用户空间有明显的界限。根据设计架构的不同，两者都可以使操作系统更加安全。

5、Linux的基本文件（夹）操作命令有哪些：
一。 通用命令: [6] 
date ：print or set the system date and time
　　2. stty -a: 可以查看或者打印控制字符(Ctrl-C, Ctrl-D, Ctrl-Z等)
　　3. passwd: print or set the system date and time (用passwd -h查看)
　　4. logout, login: 登录shell的登录和注销命令
　　5. pwd: print working directory


6. more, less, head tail: 显示或部分显示文件内容.
　　7. lp/lpstat/cancel, lpr/lpq/lprm: 打印文件.
　　8. 更改文件权限： chmod u+x...
　　9. 删除非空目录：rm -fr dir
　　10.拷贝目录： cp -R dir
　　11. fg jobid :可以将一个后台进程放到前台。
　　Ctrl-z 可以将前台进程挂起(suspend), 然后可以用bg jobid 让其到后台运行。
　　job & 可以直接让job直接在后台运行。
　　12. kill 的作用: send a signal to a process. eg: kill -9 发送的是SIG_KILL信号。。。 具体发送什么信号 可以通过 man kill 查看。
　　13. ps 的用法， ps -e 或 ps -o pid,ppid,session,tpgid, comm (其中session显示的sessionid, tpgid显示前台进程组id, comm显示命令名称。)
　　二 .ubuntu常用命令: [6] 
1. dpkg: package manager for Debian
　　* 安装： dpkg -i package
　　* 卸载： dpkg -r package
　　* 卸载并删除配置文件: dpkg -P |--purge package
　　* 如果安装一个包时。说依赖某些库。 可以先 apt-get install somelib...
　　* 查看软件包安装内容 :dpkg -L package
　　* 查看文件由哪个软件包提供: dpkg -S filename
　　* 另外 dpkg还有 dselect和aptitude 两个frontend.
　　2. apt
　　* 安装: apt-get install packs
　　* apt-get update : 更新源
　　* apt-get upgrade: 升级系统。
　　* apt-get dist-upgrade: 智能升级。安装新软件包,删除废弃的软件包
　　* apt-get -f install ： -f == --fix broken 修复依赖
　　* apt-get autoremove: 自动删除无用的软件
　　* apt-get remove packages :删除软件
　　* apt-get remove package --purge 删除包并清除配置文件
　　* 清除所以删除包的残余配置文件: dpkg -l |grep ^rc|awk '{print $2}' |tr ["/n"] [" "]|sudo xargs dpkg -P
　　* 安装软件时候包的临时存放目录 : /var/cache/apt/archives
　　* 清除该目录: apt-get clean
　　* 清除该目录的旧版本的软件缓存: apt-get autoclean
　　* 查询软件some的依赖包： apt-cache depends some
　　* 查询软件some被哪些包依赖: apt-get rdepends some
　　* 搜索软件: apt-cache search name|regexp
　　* 查看软件包的作用：apt-cache show package
　　* 查看一个软件的编译依赖库: apt-cache showsrc packagename|grep Build-Depends
　　* 下载软件的源代码 : apt-get source packagename (注: sources.list 中应该有 deb-src 源)
　　* 安装软件包源码的同时, 安装其编译环境 :apt-get build-dep packagename (有deb-src源)
　　* 如何将本地光盘加入安装源列表: apt-cdrom add
　　3. 系统命令:
　　* 查看内核版本： uname -a
　　* 查看ubuntu 版本: cat /etc/issue
　　* 查看网卡状态 : ethtool eth0
　　* 查看内存,cpu的信息： cat /proc/meminfo ; cat /proc/cpuinfo
　　(/proc下面的有很多系统信息)
　　* 打印文件系统空间使用情况: df -h
　　* 查看硬盘分区情况: fdisk -l
　　* 产看文件大小: du -h filename;
　　* 查看目录大小： du -hs dirname ; du -h dirname是查看目录下所有文件的大小
　　* 查看内存的使用： free -m|-g|-k
　　* 查看进程： ps -e 或ps -aux -->显示用户
　　* 杀掉进程: kill pid
　　* 强制杀掉： killall -9 processname
　　4. 网络相关： 
　　* 配置 ADSL: sudo pppoeconf
　　* ADSL手工拨号: sudo pon dsl-provider
　　* 激活 ADSL : sudo /etc/ppp/pppoe_on_boot
　　* 断开 ADSL: sudo poff
　　* 根据IP查网卡地址: arping IP地址
　　* 产看本地网络信息（包括ip等）: ifconfig | ifconfig eth0
　　* 查看路由信息: netstat -r
　　* 关闭网卡： sudo ifconfig eth0 down
　　* 启用网卡： sudo ifconfig eth0 up
　　* 添加一个服务: sudo update-rc.d 服务名 defaults 99
　　* 删除一个服务: sudo update-rc.d 服务名 remove
　　* 临时重启一个服务: /etc/init.d/服务名 restart
　　* 临时关闭一个服务: /etc/init.d/服务名 stop
　　* 临时启动一个服务: /etc/init.d/服务名 start
　　* 控制台下显示中文: sudo apt-get install zhcon
　　* 查找某个文件: whereis filename 或 find 目录 -name 文件名
　　*通过ssh传输文件
　　scp -rp /path/filename username@remoteIP:/path #将本地文件拷贝到服务器上
　　scp -rp username@remoteIP:/path/filename /path #将远程文件从服务器下载到本地
　　5. 压缩:
　　*解压缩 a.tar.gz: tar zxvf a.tar.gz
　　*解压缩 a.tar.bz2: tar jxvf a.tar.bz2
　　*压缩aaa bbb目录为xxx.tar.gz: tar zcvf xxx.tar.gz aaa bbb
　　*压缩aaa bbb目录为xxx.tar.bz2: tar jcvf xxx.tar.bz2 aaa bbb [6] 
6. Nautilus：
　　特殊 URI 地址
　　* computer:/// - 全部挂载的设备和网络
　　* network:/// - 浏览可用的网络
　　* burn:/// - 一个刻录 CDs/DVDs 的数据虚拟目录
　　* smb:/// - 可用的 windows/samba 网络资源
　　* x-nautilus-desktop:/// - 桌面项目和图标
　　* file:/// - 本地文件
　　* trash:/// - 本地回收站目录
　　* ftp:// - FTP 文件夹
　　* ssh:// - SSH 文件夹
　　* fonts:/// - 字体文件夹，可将字体文件拖到此处以完成安装
　　* themes:/// - 系统主题文件夹
　　* 显示隐藏文件: Ctrl+h
　　* 显示地址栏: Ctrl+l
　　* 查看已安装字体: 在nautilus的地址栏里输入”fonts:///“，就可以查看本机所有的fonts [6] 
7.补充部分：
* 查看本地所有的tpc,udp监听端口: netstat -tupln (t=tcp, u=udp, p=program, l=listen, n=numric)
　　* 通过man搜说相关命令: man -k keyword . eg: man -k user
　　* 或者用 apropos
　　* 统计文件所占用的实际磁盘空间： du (du - estimate file space usage)
　　* 统计文件中的字符，字节数: wc -c/-l/-w (wc - print the number of newlines, words, and bytes in files)
　　* 查看文件的内容： od -x/-c/.... (od - dump files in octal and other formats)
　　我认为od最有用的就是文件的字节流了: od -t x1 filename
　　查看文件的 Ascii 码形式: od -t c filename (其中统计信息最左边的是： 字节数)
　　* 查找命令所在文件的位置： which od 输出： /usr/bin/od
　　查看该文件由哪个包提供： dpkg -S /usr/bin/od 输出: coreutils: /usr/bin/od
　　再查看coreutils包的全部内容就知道了linux的核心命令: dpkg -L coreutils
　　然后 info coreutils 哈哈，认真学吧， 满世界都是命令!
　　* 可以用man 命令产看某个命令的所有section 的解释: man -a tty
　　然后用q,和next 转换到下一个section的解释
　　* bash 的好用的快捷键:
　　ctrl+a:光标移到行首。
　　ctrl+b:光标左移一个字母
　　ctrl+c:杀死当前进程。
　　ctrl+d:退出当前 Shell。
　　ctrl+e:光标移到行尾。
　　ctrl+h:删除光标前一个字符，同 backspace 键相同。
　　ctrl+k:清除光标后至行尾的内容。
　　ctrl+l:清屏，相当于clear。
　　ctrl+r:搜索之前打过的命令。会有一个提示，根据你输入的关键字进行搜索bash的history
　　ctrl+u: 清除光标前至行首间的所有内容。
　　ctrl+w: 移除光标前的一个单词
　　ctrl+t: 交换光标位置前的两个字符
　　ctrl+y: 粘贴或者恢复上次的删除
　　ctrl+d: 删除光标所在字母;注意和backspace以及ctrl+h的区别，这2个是删除光标前的字符
　　ctrl+f: 光标右移
　　ctrl+z : 把当前进程转到后台运行，使用’ fg ‘命令恢复。比如top -d1 然后ctrl+z ，到后台，然后fg,重新恢复
　　* 快速粘贴：先在一个地方选中文字，在欲粘贴的地方按鼠标 中键 即可。
　　* 等效中键：a 、按下滑轮等效于中键。b、同时按下鼠标 左右键，等效于中键。
　　* 快速重启X服务： 同时按下： Alt + Ctrl + Backspace 三个键。
　　* 打开"运行"窗口： 同时按下 Alt + F2 键。
　　* 截屏： a、全屏：直接按下 PrtScr 键。
　　b、当前窗口：同时按下 Alt + PrtScr 键。
　　c、延时截屏：在 终端 或 "运行"窗口中输入命令： gnome-screenshot --delay 3 ，将延时 3 秒后截屏。
　　* 直接将 文件管理器 中的文件拖到 GNOME终端 中就可以在终端中得到完整的路径名。 [6]  8.ulimit
　　ulimit：显示（或设置）用户可以使用的资源的限制（limit），这限制分为软限制（当前限制）和硬限制（上限），其中硬限制是软限制的上限值，应用程序在运行过程中使用的系统资源不超过相应的软限制，任何的超越都导致进程的终止。
　　ulimited 不限制用户可以使用的资源，但本设置对可打开的最大文件数（max open files）
　　和可同时运行的最大进程数（max user processes）无效
　　-a 列出所有当前资源极限
　　-c 设置core文件的最大值.单位:blocks
　　-d 设置一个进程的数据段的最大值.单位:kbytes
　　-f Shell 创建文件的文件大小的最大值，单位：blocks
　　-h 指定设置某个给定资源的硬极限。如果用户拥有 root 用户权限，可以增大硬极限。任何用户均可减少硬极限
　　-l 可以锁住的物理内存的最大值
　　-m 可以使用的常驻内存的最大值,单位：kbytes
　　-n 每个进程可以同时打开的最大文件数
　　-p 设置管道的最大值，单位为block，1block=512bytes
　　-s 指定堆栈的最大值：单位：kbytes
　　-S 指定为给定的资源设置软极限。软极限可增大到硬极限的值。如果 -H 和 -S 标志均未指定，极限适用于以上二者
　　-t 指定每个进程所使用的秒数,单位：seconds
　　-u 可以运行的最大并发进程数
　　-v Shell可使用的最大的虚拟内存，单位：kbytes
　　eg: ulimit -c 1000(可以先通过ulimit -c 查看原来的值)
6.
      什么是开源软件：英文表示是open source software，简称为OSS，直接的字面意思是公开源代码的软件。软件既然连源代码都公开，因此开源软件具备可以免费使用和公布源代码的主要特征。


7.开源社区有哪些： http://sourceforge.net/
http://www.apache.org/
这两个就N经典了,好多东西都是他们上面提供支持的.

其他的有些干专项的.
比如http://www.open-open.com/java开源大全
还有开源文档的满江红开源http://wiki.redsaga.com/confluence/display/RSTEAM/Home


8.为什么要有版本控制：       更加简明一些，首先是一个存放代码的仓库，其次是一套管理这个仓库的工具，整个构成了一套版本控制系统。

    这一段大概就比较明确了。除了最常用的存放程序代码，版本库还可以存放许多其他的东西，比如这篇文章。这篇文章就是在Git版本控制系统的管理下。



9.         GIT常用命令：  常用命令:# 提交暂存区到仓库区
$ git commit -m [message]

# 提交暂存区的指定文件到仓库区
$ git commit [file1] [file2] ... -m [message]

# 提交工作区自上次commit之后的变化，直接到仓库区
$ git commit -a

# 提交时显示所有diff信息
$ git commit -v

# 使用一次新的commit，替代上一次提交
# 如果代码没有任何新变化，则用来改写上一次commit的提交信息
$ git commit --amend -m [message]

# 重做上一次commit，并包括指定文件的新变化
$ git commit --amend [file1] [file2] ...



10.   和GitHub有什么关系：Git比GitHub出生的早。事件回到2005年，有个公司不允许linux系统继续免费使用它们的版本控制软件了，然后linux系统创始人Torvalds一气之下花了10天时间创造了Git（第一个版本），并且开源给所有人免费试用。3年后，Tom Preston使用Git作为版本控制软件创建了http://Github.com，一个专门托管代码并且可以实现版本控制的网站。Tom之所以把网站叫做Github，是因为其核心部分版本控制是用Git来处理的。
--------------------- 



11.ARM架构处理器都有哪些：  官方架构的cpu核心，现在大家比较熟悉的有
ARMv7架构的Cortex-A5,A7,A8,A9,A12,A15，
ARMv8架构的Cortex-A53,A57，A72。


12. 特点：1、体积小、低功耗、低成本、高性能；
　　2、支持Thumb（16位）/ARM（32位）双指令集，能很好的兼容8位/16位器件；
　　3、大量使用寄存器，指令执行速度更快；
　　4、大多数数据操作都在寄存器中完成；
　　5、寻址方式灵活简单，执行效率高；
　　6、指令长度固定。


13.处理器的结构都有哪些： ARM和Thumb状态 
RISC技术 
流水线技术 
超标量技术

 

ARM和Thumb状态 
V4版以后有： 
（1）32位ARM指令集 
（2）16位Thumb指令集，功能是ARM指令集的功能子集。 
ARM7TDMI核以后，T变种的ARM微处理器有两种工作状态： 
（1）ARM状态 
（2）Thumb状态。 
当ARM微处理器执行32位的ARM指令集时，工作在ARM状态； 
当ARM微处理器执行16位的Thumb指令集时，工作在Thumb状态



14.方法一：使用命令修改（直接即时生效,重启失效）

 ＃ifconfig eth0 192.168.0.1 netmask 255.255.255.0 up说明：eth0是第一个网卡，其他依次为eth1，eth*192.168.0.1是给网卡配置的第一个网卡配置的ip地址netmask 255.255.255.0 配置的是子网掩码up是表示立即激活ifconfig的更多参数说明查看相关帮助　　gateway:　　# route add default gw 192.168.30.1 eth0　　dns:# vi etc/resolv.confnameserver 202.131.80.1　　nameserver 202.131.80.5如果要重起生效,就把这些写到起动脚本 rc.local中



15、为什么在路由器中可以安装Linux，在路由器中使用的Linux和在桌面端使用的有什么区别：windows是图形界面操作系统，方便用户使用，可是不开放源代码，安全性不太高
LINUX是开放源代码的操作系统，可以很好的与机器结合起来，而且安全性更高


16.为什么要有操作系统：我认为操作系统的第一层含义，它其实是一种驱动程序。让人们不需要关心一些硬件细节，就可以使用硬件。
有了驱动程序我们就可以通过程序调用的方式使用硬件了。如果只有一个程序想使用硬件，其实操作系统到了驱动程序这一层就可以结束了，但情况远远没有结束。有需求都想使用同一个硬件，这样直接调用的方式去使用硬件看来就不太现实了。
所以我认为操作系统的第二层含义，它其实是为了共享使用硬件资源；为使用者指定一些规范，让不同的使用者可以共享使用硬件。（生活中的红绿灯就是一种规范）
--------------------- 



17、自己对计算机分层思想的理解：分层模型中，不同的层次意味着不同的抽象级别； 
抽象也是一种凝聚
附庸的附庸不是附庸； 
每一层只需考虑与其相邻的上下两层，而无需考虑更高或者更低的层次；
不考虑，也即不关心（仅考虑自身），也即看不见，看不见更低和更高的层次；
底层向高层提供服务；
将物理层向上抽象为逻辑层，逻辑层向上提供公共接口，这样上层直接面对逻辑层，而无需直接跟复杂异构的物理层交互，这也是一种抽象和分层。 
--------------------- 


18、　UART串口通信的层次结构是怎样的：　UART的设计采用模块化的设计思想，主要分为 3个模块：数据发送模块、数据接收模块及波特率发生器控制模块。发送模块实现数据由并行输入到串行输出，接收模块实现数据由串行输入到并行输出，波特率发生器模块控制产生UART时钟频率。


19、为什么Qt可以跨平台使用而VS不能：在使用到一些类时，可能因为没有引用相应的头而提示类型不完整或者编译错误等。这时我们需要引用相应的头。一般引用头，直接和类名对应就可以了。比如我们使用了QMessageBox，引用的头就是#include <QMessageBox>。如果我们打开QMessageBox，会发现里面其实就是一个头的引用qmessagebox.h.

如果没有引用到相应的模块，有可能还需要加上QtCore、QtGui、QtWidgets等作为前置路径，如#include<QtWidgets/QLabel>。如果有引用QtWidget，那么就可以直接写#include <QLabel>


20、C语言开发软件：c-free visualc++


21、c语言中的返回值：main函数的返回值用于说明程序的退出状态。如果返回0，则代表程序正常退出。返回其它数字的含义则由系统决定。通常，返回非零代表程序异常退出。利用程序的返回值，我们可以控制要不要执行下一个程序。这就是int main的好处。


22、主函数参数如何确定：这两个参数名字可以自定，但前者必须整形，后者是一个字符型指针数组，这个指针数组每个指针都指向一个字符串，前者就表示字符串的个数。
运行的时候可以打开命令提示符输入命令行进行操作，比如文件名为myc.exe，就在命令行中找到相应的根目录输入myc执行它，然后 argv[0]中就存放字符串“myc”的首地址，这时argc就为1，且至少为1，argv[1]则由系统置'\0'，假如输入myc good! work然后回车，这时argv[0]还是myc首地址，依次类推，argv[1]放的就是good!的首地址，argv[2]就是work的首地址，argv[3]为'\0'，这时argc就为3，字符串之间由空格或者TAB做分隔。














