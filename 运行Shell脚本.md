原文链接：https://blog.csdn.net/as604049322/article/details/120446586


## 入门
### 运行Shell脚本
编写shell脚本：

![image](https://github.com/user-attachments/assets/1c74a9f0-460f-45fa-b3dd-44c8ba88585b)

#! 是一个约定的标记，它告诉系统这个脚本需要什么解释器来执行，即使用哪一种 Shell。

echo 命令用于向窗口输出文本。

运行 Shell 脚本有两种方法：

**1、作为可执行程序**

![image](https://github.com/user-attachments/assets/ebb55027-a163-4865-9819-5c7d2487c371)

默认情况下，一定要写成 ./test.sh，而不是 test.sh，运行其它二进制的程序也一样。

除非将当前目录.加入到PATH环境变量中，配置方法：

![image](https://github.com/user-attachments/assets/3514d96d-f1b4-4fe7-982f-c5a2e58f01c5)

**2、作为解释器参数**

直接运行解释器，其参数就是 shell 脚本的文件名：

![image](https://github.com/user-attachments/assets/c9f60835-dd25-4c99-a572-296e119e3c90)

这种方式运行的脚本，不需要在第一行指定解释器信息，写了也没用。
