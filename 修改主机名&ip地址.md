原文链接：https://blog.csdn.net/as604049322/article/details/120446586


## 修改主机名&ip地址
显示主机名：hostname

临时修改：hostname xxx

**永久修改**

对于Ubuntu 系统

![image](https://github.com/user-attachments/assets/649679b8-b3cd-4be1-8cb1-163f3d705a8e)

对于centos系统

![image](https://github.com/user-attachments/assets/28447559-1ae7-4fab-9c98-47017165cb18)

在此配置文件中添加一条HOSTNAME=node1

针对centos7系统，可以使用如下命令

![image](https://github.com/user-attachments/assets/db191330-957c-454a-9990-5452ed8a6977)

一般需要重开shell甚至重启操作系统才能生效。

**修改IP地址**

ifconfig eth0 192.168.12.22(重启后无效)

![image](https://github.com/user-attachments/assets/c1223ac4-f88e-464d-8873-39953a99d2ec)
