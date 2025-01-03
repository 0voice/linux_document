


## chattr权限
chattr概述：凌驾于r、w、x、suid、sgid之上的权限。

### lsattr：查看特殊权限

![image](https://github.com/user-attachments/assets/6d9f8047-7bb0-4159-989b-3e04cff9e6d6)

### chattr：设置特殊权限

![image](https://github.com/user-attachments/assets/585e7536-9086-42c5-8760-59756db1bfd7)

防止系统中某个关键文件被修改：

![image](https://github.com/user-attachments/assets/4aa95274-0d04-47ae-a407-7466f3ee4dee)

让某个文件只能往里面追加内容，不能删除，一些日志文件适用于这种操作：

![image](https://github.com/user-attachments/assets/0299160e-a3c6-4fc5-a439-9342aff3e564)

