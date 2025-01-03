原文链接：https://blog.csdn.net/as604049322/article/details/120446586


## ssh免密登陆
假如 A 要登陆 B

在A上操作：

首先生成密钥对

![image](https://github.com/user-attachments/assets/429252c7-5754-49dc-a4f0-e4cd44dfe953)

再将A自己的公钥拷贝并追加到B的授权列表文件authorized_keys中

![image](https://github.com/user-attachments/assets/5e6362c4-67c1-4419-9b31-474571697798)
