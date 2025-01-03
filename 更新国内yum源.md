原文链接：https://blog.csdn.net/as604049322/article/details/120446586


## yum安装命令
yum（ Yellow dog Updater, Modified）是一个在Fedora和RedHat以及SUSE中的Shell前端软件包管理器。

基於RPM包管理，能够从指定的服务器自动下载RPM包并且安装，可以自动处理依赖性关系，并且一次安装所有依赖的软体包，无须繁琐地一次次下载、安装。

yum提供了查找、安装、删除某一个、一组甚至全部软件包的命令，而且命令简洁而又好记。

### 更新国内yum源
网易（163）yum源是国内最好的yum源之一 ，无论是速度还是软件版本，都非常的不错。

将yum源设置为163 yum，可以提升软件包安装和更新的速度，同时避免一些常见软件版本无法找到。

首先备份/etc/yum.repos.d/CentOS-Base.repo

![image](https://github.com/user-attachments/assets/28353354-9bcd-4018-8e19-3bbbb78b5fe0)

下载对应版本 repo 文件, 放入 /etc/yum.repos.d/

- CentOS5 ：http://mirrors.163.com/.help/CentOS5-Base-163.repo
- CentOS6 ：http://mirrors.163.com/.help/CentOS6-Base-163.repo
- CentOS7 ：http://mirrors.163.com/.help/CentOS7-Base-163.repo

![image](https://github.com/user-attachments/assets/b388f38c-2b77-4144-a296-9ec328089ada)

运行以下命令生成缓存

![image](https://github.com/user-attachments/assets/6d9a270e-13bf-4375-aa39-45337887d6d8)

除了网易之外，国内还有其他不错的 yum 源，比如中科大和搜狐。

中科大的 yum 源，安装方法查看：https://lug.ustc.edu.cn/wiki/mirrors/help/centos

sohu 的 yum 源安装方法查看: http://mirrors.sohu.com/help/centos.html
