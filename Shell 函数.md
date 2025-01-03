原文链接：https://blog.csdn.net/as604049322/article/details/120446586


## Shell 函数
shell中函数的定义格式如下：

![image](https://github.com/user-attachments/assets/d13ebff5-78b7-405d-b30a-3b7275cbda2f)

说明：

- 1、可以带function fun() 定义，也可以直接fun() 定义,不带任何参数。
- 2、参数返回，可以显示加：return 返回，如果不加，将以最后一条命令运行结果，作为返回值。 return后跟数值n(0-255)

示例：

![image](https://github.com/user-attachments/assets/0796edb0-e332-49a9-a8a6-1469217ad5b2)

输出，类似下面：

![image](https://github.com/user-attachments/assets/f21221b8-cdb1-48c3-8070-c5c2dc57df09)

函数返回值在调用该函数后通过 $? 来获得。

注意：所有函数在使用前必须定义。这意味着必须将函数放在脚本开始部分，直至shell解释器首次发现它时，才可以使用。调用函数仅使用其函数名即可。

在Shell中，调用函数时可以向其传递参数。在函数体内部，通过 $n 的形式来获取参数的值，例如，$1表示第一个参数，$2表示第二个参数…

带参数的函数示例：

![image](https://github.com/user-attachments/assets/2cb6e508-4645-4797-adcf-31cc7b05d9a8)

输出结果：

![image](https://github.com/user-attachments/assets/5d76f721-b3f1-4adc-a2cf-78b279ea3567)

当n>=10时，需要使用${n}来获取参数。

另外，还有几个特殊字符用来处理参数：

![image](https://github.com/user-attachments/assets/98d7cccf-f008-4ca4-9c58-799474999365)
