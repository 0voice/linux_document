原文链接：https://blog.csdn.net/as604049322/article/details/120446586

## 其他命令
### 远程文件复制：scp
scp 命令用于 Linux 之间复制文件和目录，scp是 secure copy 的缩写是linux系统下基于ssh登陆进行安全的远程文件拷贝命令。

scp 是加密的，rcp 是不加密的，scp 是 rcp 的加强版。

使用scp命令要确保使用的用户具有可读取远程服务器相应文件的权限，否则scp命令是无法起作用的。

从本地复制到远程命令格式：

![image](https://github.com/user-attachments/assets/f224abe6-ff73-4c5b-ba0e-0f266e2702bb)

实例：

![image](https://github.com/user-attachments/assets/65cdb656-b1ed-47dd-a7df-3d16576ac8e8)

从远程复制到本地：

![image](https://github.com/user-attachments/assets/4a307c74-9ddb-4c98-b163-e0f59bf7229d)

-P 参数来设置命令的端口号：

![image](https://github.com/user-attachments/assets/fefcc24e-e811-4ba4-9d1e-80e4d42a498d)

