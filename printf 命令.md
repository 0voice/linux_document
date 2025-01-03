原文链接：https://blog.csdn.net/as604049322/article/details/120446586


## printf 命令
printf 命令的语法：

![image](https://github.com/user-attachments/assets/51b31f21-dc28-4e74-9f81-273af36de435)

**参数说明：**

- format-string: 为格式控制字符串
- arguments: 为参数列表。

实例如下：

![image](https://github.com/user-attachments/assets/aa2cc8c8-824b-46cf-9f7f-4b4a9620ebc8)

执行脚本，输出结果如下所示：

![image](https://github.com/user-attachments/assets/08451484-77a9-4e71-93c8-7d6f54262355)

- %s %c %d %f都是格式替代符
- %-10s 指一个宽度为10个字符（-表示左对齐，没有则表示右对齐），任何字符都会被显示在10个字符宽的字符内，如果不足则自动以空格填充，超过也会将内容全部显示出来。
- %-4.2f 指格式化为小数，其中.2指保留2位小数。

printf的转义序列：

![image](https://github.com/user-attachments/assets/59d99bf0-fdbb-4562-a426-a73bf509e67f)

例子：

![image](https://github.com/user-attachments/assets/5a69a278-d8dd-4d5c-b5e4-761011a0e4eb)
