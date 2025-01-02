原文链接：https://blog.csdn.net/as604049322/article/details/120446586


## locate查找
locate命令会去保存文档和目录名称的数据库内，查找文件或目录。

一般情况我们只需要输入locate your_file_name 即可查找指定文件。

参数：

- -d或–database= 配置locate指令使用的数据库。locate指令预设的数据库位于/var/lib/mlocate目录里，文档名为mlocate.db。

查找passwd文件，输入以下命令：

![image](https://github.com/user-attachments/assets/4f712959-a0b3-4c88-a6fd-92ee2a5861bc)

locate与find的区别: find 是去硬盘找，locate 只在/var/lib/slocate资料库中找。

locate的速度比find快，它并不是真的查找，而是查数据库，一般文件数据库在/var/lib/mlocate/mlocate.db中，所以locate的查找并不是实时的，而是以数据库的更新为准，一般是系统自己维护，也可以手工升级数据库 ，命令为：

![image](https://github.com/user-attachments/assets/e9ec9c10-1b84-4d81-a193-07259359c5ad)
