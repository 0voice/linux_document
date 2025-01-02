原文链接：https://blog.csdn.net/as604049322/article/details/120446586


## 设置或显示环境变量：export
在 shell 中执行程序时，shell 会提供一组环境变量。export 可新增，修改或删除环境变量，供后续执行的程序使用。export 的效力仅限于该次登陆操作。

![image](https://github.com/user-attachments/assets/82b34ec1-a4cc-4a76-ac9f-505f97adabd6)

参数说明：

- -f 　代表[变量名称]中为函数名称。
- -n 　删除指定的变量。变量实际上并未删除，只是不会输出到后续指令的执行环境中。
- -p 　列出所有的shell赋予程序的环境变量。

![image](https://github.com/user-attachments/assets/c626bfd4-c27e-436e-ad2e-894ec4f6d2c8)
