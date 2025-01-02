原文链接：https://blog.csdn.net/as604049322/article/details/120446586

## Linux 磁盘管理
Linux磁盘管理常用三个命令为df、du和fdisk。

df：列出文件系统的整体磁盘使用量
du：检查磁盘空间使用量
fdisk：用于磁盘分区

### df
获取硬盘被占用了多少空间，目前还剩下多少空间等信息。

语法：

![image](https://github.com/user-attachments/assets/8975c5e0-7bea-40ca-b3b2-04d02a250b33)

选项与参数：

- -a ：列出所有的文件系统，包括系统特有的 /proc 等文件系统；
- -k ：以 KBytes 的容量显示各文件系统；
- -m ：以 MBytes 的容量显示各文件系统；
- -h ：以人们较易阅读的 GBytes, MBytes, KBytes 等格式自行显示；
- -H ：以 M=1000K 取代 M=1024K 的进位方式；
- -T ：显示文件系统类型, 连同该 partition 的 filesystem 名称 (例如 ext3) 也列出；
- -i ：不用硬盘容量，而以 inode 的数量来显示

![image](https://github.com/user-attachments/assets/b7163541-e419-4db7-a15f-eb7d05ea299e)

将系统内的所有特殊文件格式及名称都列出来

![image](https://github.com/user-attachments/assets/11d48db3-b520-4ce7-aa2b-05e071e4aadd)

### du
du命令是对文件和目录磁盘使用的空间的查看.

语法：

![image](https://github.com/user-attachments/assets/5f70cf49-bf52-49c0-ad33-144d16ddaa9f)

选项与参数：

- -a ：列出所有的文件与目录容量，因为默认仅统计目录底下的文件量而已。
- -h ：以人们较易读的容量格式 (G/M) 显示；
- -s ：列出总量而已，而不列出每个各别的目录占用容量；
- -S ：不包括子目录下的总计，与 -s 有点差别。
- -k ：以 KBytes 列出容量显示；
- -m ：以 MBytes 列出容量显示；

du没有加任何选项时，只列出当前目录下的所有文件夹容量（包括隐藏文件夹）:

![image](https://github.com/user-attachments/assets/92c4ae7d-961a-4800-b0b3-1f60563f36f1)

直接输入 du 没有加任何选项时，则 du 会分析当前所在目录的文件与目录所占用的硬盘空间。

加-a选项才显示文件的容量：

![image](https://github.com/user-attachments/assets/382dfe8f-914f-43b2-b37b-467470bb4b17)

检查根目录底下每个目录所占用的容量

![image](https://github.com/user-attachments/assets/c38bce2c-b6f1-4bd8-99d9-a1fac5bd5b13)

### fdisk
fdisk 是 Linux 的磁盘分区表操作工具。

语法：

![image](https://github.com/user-attachments/assets/4e43b3da-175e-4b1a-9c4a-130258235797)

选项与参数：

- -l ：输出后面接的装置所有的分区内容。若仅有 fdisk -l 时， 则系统将会把整个系统内能够搜寻到的装置的分区均列出来。

列出所有分区信息：

![image](https://github.com/user-attachments/assets/0e02db53-99a8-475e-bc77-d3bc765210c6)

查看根目录所在磁盘，并查阅该硬盘内的相关信息：

![image](https://github.com/user-attachments/assets/52c91902-529f-492a-a7e1-875a33176080)

输入 m 后，就会看到底下这些命令介绍

![image](https://github.com/user-attachments/assets/e67c4b86-8864-40cd-b235-b883db545cbe)

离开 fdisk 时按下 q，那么所有的动作都不会生效！相反的， 按下w就是动作生效的意思。

![image](https://github.com/user-attachments/assets/36752dcf-a51f-47e6-a608-e3924e42940c)

使用 p 可以列出目前这颗磁盘的分割表信息，这个信息的上半部在显示整体磁盘的状态。

### 磁盘格式化
磁盘分割完毕后自然就是要进行文件系统的格式化，格式化的命令非常的简单，使用 mkfs（make filesystem） 命令。

语法：

![image](https://github.com/user-attachments/assets/93d1f744-c5c1-45d8-80a4-98c726627a8a)

选项与参数：

- -t ：可以接文件系统格式，例如 ext3, ext2, vfat 等(系统有支持才会生效)

查看 mkfs 支持的文件格式：

![image](https://github.com/user-attachments/assets/69944f63-6898-4648-82c3-8657c1a6008d)

按下两个[tab]，会发现 mkfs 支持的文件格式如上所示。

将分区 /dev/hdc6（可指定其他分区） 格式化为ext3文件系统：

![image](https://github.com/user-attachments/assets/a220f064-c0b9-44b1-b686-2cb3934794fe)

### 磁盘检验
fsck（file system check）用来检查和维护不一致的文件系统。

若系统掉电或磁盘发生问题，可利用fsck命令对文件系统进行检查。

语法：

![image](https://github.com/user-attachments/assets/9b39f375-aa0d-42d8-aac8-605730bcb94c)

选项与参数：

- -t : 给定档案系统的型式，若在 /etc/fstab 中已有定义或 kernel 本身已支援的则不需加上此参数
- -s : 依序一个一个地执行 fsck 的指令来检查
- -A : 对/etc/fstab 中所有列出来的 分区（partition）做检查
- -C : 显示完整的检查进度
- -d : 打印出 e2fsck 的 debug 结果
- -p : 同时有 -A 条件时，同时有多个 fsck 的检查一起执行
- -R : 同时有 -A 条件时，省略 / 不检查
- -V : 详细显示模式
- -a : 如果检查有错则自动修复
- -r : 如果检查有错则由使用者回答是否修复
- -y : 选项指定检测每个文件是自动输入yes，在不确定那些是不正常的时候，可以执行 # fsck -y 全部检查修复。

查看系统有多少文件系统支持的 fsck 命令：

![image](https://github.com/user-attachments/assets/762b93b7-3fc1-4689-90a3-6a4c42ac60fa)

强制检测 /dev/hdc6 分区:

![image](https://github.com/user-attachments/assets/777cfe8e-e068-473a-a3a8-f8c24b7e10b8)

如果没有加上 -f 的选项，则由于这个文件系统不曾出现问题，检查的经过非常快速！若加上 -f 强制检查，才会一项一项的显示过程。

### 磁盘挂载与卸除
Linux 的磁盘挂载使用 mount 命令，卸载使用 umount 命令。

磁盘挂载语法：

![image](https://github.com/user-attachments/assets/073d1b16-cf4f-414a-985b-0bc8dddccedf)

用默认的方式，将刚刚创建的 /dev/hdc6 挂载到 /mnt/hdc6 上面！

![image](https://github.com/user-attachments/assets/ad690280-7f32-4d1d-a76e-fb84437428a3)

磁盘卸载命令 umount 语法：

![image](https://github.com/user-attachments/assets/ba11dbd2-4668-44d1-b4db-f0bd23cf7003)

选项与参数：

- -f ：强制卸除！可用在类似网络文件系统 (NFS) 无法读取到的情况下；
- -n ：不升级 /etc/mtab 情况下卸除。

卸载/dev/hdc6

![image](https://github.com/user-attachments/assets/af6a94fd-8d47-4758-85d8-4b0bc064f084)

