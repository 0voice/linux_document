原文链接：https://blog.csdn.net/as604049322/article/details/120446586


## echo命令
Shell 的 echo 指令与 PHP 的 echo 指令类似，都是用于字符串的输出。命令格式：

![image](https://github.com/user-attachments/assets/5f3c1002-7a95-404a-885f-7a6fd934d073)

显示普通字符串:

![image](https://github.com/user-attachments/assets/06fae384-3d5f-4ac6-95dc-d6dec17f4dcb)

这里的双引号完全可以省略，以下命令与上面实例效果一致：

![image](https://github.com/user-attachments/assets/e65e6102-4c6b-498e-a358-e5e36e4140ed)

显示转义字符:

![image](https://github.com/user-attachments/assets/566bd546-34d9-4b13-ae4c-6fe8f4e450ee)

结果将是:

![image](https://github.com/user-attachments/assets/0acee32d-ea65-421c-9139-314bc1198cf0)

同样，双引号也可以省略

read 命令从标准输入中读取一行,并把输入行的每个字段的值指定给 shell 变量

![image](https://github.com/user-attachments/assets/00d955d2-75bf-4fe8-b446-6f9432ab2325)

以上代码保存为 test.sh，name 接收标准输入的变量，结果将是:

![image](https://github.com/user-attachments/assets/6952f6a6-f17a-4eb9-aa5a-4f09637f3318)

**显示换行**

![image](https://github.com/user-attachments/assets/96670c47-53b3-4ef8-9226-c3fa83edbd6f)

输出结果：

![image](https://github.com/user-attachments/assets/15c387d3-4c59-4e4e-b2ba-203dc1cd4093)

**显示不换行**

![image](https://github.com/user-attachments/assets/063e14db-e91e-4706-9af6-b4a524bbd916)

输出结果：

![image](https://github.com/user-attachments/assets/719bbf29-0543-4752-9475-70b387a28745)

