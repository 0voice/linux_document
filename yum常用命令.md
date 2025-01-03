原文链接：https://blog.csdn.net/as604049322/article/details/120446586


## yum常用命令
yum 语法：

![image](https://github.com/user-attachments/assets/e870e089-44d4-4188-a7b2-3d84e27e8a42)

选项：

- **options：**可选，选项包括-h（帮助），-y（当安装过程提示选择全部为"yes"），-q（不显示安装的过程）等等。
- **command：**要进行的操作。
- **package：**操作的对象。

实例：

- 列出所有可更新的软件清单命令：yum check-update
- 更新所有软件命令：yum update
- 仅安装指定的软件命令：yum install <package_name>
- 仅更新指定的软件命令：yum update <package_name>
- 显示包信息：yum info <package_name>
- 列出所有可安裝的软件清单命令：yum list
- 删除软件包命令：yum remove <package_name>
- 查找软件包 命令：yum search <keyword>
- 清除缓存命令:

1.yum clean packages: 清除缓存目录下的软件包
  
2.yum clean headers: 清除缓存目录下的 headers

3.yum clean oldheaders: 清除缓存目录下旧的 headers

4.yum clean, yum clean all (= yum clean packages; yum clean oldheaders) :清除缓存目录下的软件包及旧的headers

