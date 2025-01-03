原文链接：https://blog.csdn.net/as604049322/article/details/120446586


## rpm
RPM是Red Hat公司随Redhat Linux推出了一个软件包管理器，通过它能够更加轻松容易地实现软件的安装。

**常见用法：**

- rpm -ivh <rpm包名> 安装软件
- rpm -e <rpm包名> 卸载安装
- rpm -qi <rpm包名> 显示软件安装信息
- rpm -qa | grep xxx 查询软件是否安装（包括相关依赖）
- rpm -Uvh <rpm包名> 升级一个rpm

**具体参数详解：**

-i, --install 安装包

-v, --verbose 列出更多详细信息，安装进度

-h, --hash 安装时列出hash标记 (与 -v连用)

-e, --erase 卸载安装包

-U, --upgrade=+ 升级包

–replacepkge 无论软件包是否已被安装，都强行安装软件包

–test 安装测试，并不实际安装

–nodeps 忽略软件包的依赖关系强行安装

–force 忽略软件包及文件的冲突

-q,–query:

-a, --all 查询/校验所有的安装包

-p, --package 查询/校验一个安装文件

-l, --list 列出安装文件

-d, --docfiles 列出所有文档文件

-f, --file 查询/校验安装包中所包含的文件

安装软件：

![image](https://github.com/user-attachments/assets/24b6f420-8208-46e9-ada9-e32121b7b1d6)

显示软件安装信息：

![image](https://github.com/user-attachments/assets/e67fde58-754c-45b3-878e-5bbce0e7d81a)


