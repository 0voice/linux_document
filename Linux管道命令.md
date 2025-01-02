原文链接：https://blog.csdn.net/as604049322/article/details/120446586

## Linux管道命令
Linux的管道命令是’|’，通过它可以对数据进行连续处理，其示意图如下：
![image](https://github.com/user-attachments/assets/350b7eab-b157-4dc2-a69d-ed00993fa7de)

注意：

1）管道命令仅处理标准输出，对于标准错误输出，将忽略

2）管道命令右边命令，必须能够接收标准输入流命令才行，否则传递过程中数据会抛弃。

常用来作为接收数据管道命令有： less,more,head,tail，而ls, cp, mv就不行。

### wc - 统计字数
可以计算文件的Byte数、字数、或是列数，若不指定文件名称、或是所给予的文件名为"-"，则wc指令会从标准输入设备读取数据。

![image](https://github.com/user-attachments/assets/8ccca34b-cbe7-46f2-a423-8436645cf0b6)

在默认的情况下，wc将计算指定文件的行数、字数，以及字节数。使用的命令为：

![image](https://github.com/user-attachments/assets/3e8ceccd-921a-4d80-8027-b3873bf14c12)

其中，3 个数字分别表示testfile文件的行数、单词数，以及该文件的字节数。

如果想同时统计多个文件的信息，例如同时统计testfile、testfile_1、testfile_2，可使用如下命令：

![image](https://github.com/user-attachments/assets/cc494cef-43e5-434e-9c2b-d7227e2f810d)

### cut - 列选取命令
![image](https://github.com/user-attachments/assets/bfd07d60-336a-4e1c-b43f-30cbef1d4b2d)

cut以行为单位，根据分隔符把行分成若干列，这样就可以指定选取哪些列了。

![image](https://github.com/user-attachments/assets/efd4146f-683a-485e-b77e-0c7f39911a26)

只显示/etc/passwd的用户和shell：

![image](https://github.com/user-attachments/assets/9c7f440a-924e-4604-9f2c-58138af82d0a)

### grep - 行选取命令
grep一般格式为：

![image](https://github.com/user-attachments/assets/586228f0-0ed3-401e-89a6-f94328914ca0)

在grep命令中输入字符串参数时，最好引号或双引号括起来。例如：grep 'a' 1.txt。

常用选项说明：

![image](https://github.com/user-attachments/assets/467897e9-8c58-4282-a61c-faced4a6d88f)

grep搜索内容串可以是正则表达式，常用正则表达式：

![image](https://github.com/user-attachments/assets/b876f318-4c04-4af5-872a-b40beeaa583c)

实例：

显示所有以“h”结尾的行

grep h$

匹配所有以“a”开头且以“e”结尾的，中间包含2个字符的单词

grep ‘<a…e>’

显示所有包含一个”y”或”h”字符的行

grep [yh]

显示不包含字母a~k 且后紧跟“pple”的单词

grep [^a-k]pple

从系统词典中选择所有以“c”开头且以“o”结尾的单词

grep '\<c.*o\>'

找出一个文件中或者输出中找到包含*的行

grep '\*'

显示所有包含每个字符串至少有20个连续字母的单词的行

grep [a-Z]\{20,\}

### sort - 排序
语法：

![image](https://github.com/user-attachments/assets/223e9bb5-36af-4740-9156-8ae64b858353)

参数说明：

- -f ：忽略大小写的差异，例如 A 与 a 视为编码相同；
- -b ：忽略最前面的空格符部分；
- -M ：以月份的名字来排序，例如 JAN, DEC 等等的排序方法；
- -n ：使用『纯数字』进行排序(默认是以文字型态来排序的)；
- -r ：反向排序；
- -u ：就是 uniq ，相同的数据中，仅出现一行代表；
- -t ：分隔符，默认是用 [tab] 键来分隔；
- -k ：以哪个区间 (field) 来进行排序

默认是以第一个字符升序排序:

![image](https://github.com/user-attachments/assets/75a96e56-f402-4779-a149-4ccef2cc0b20)

以第3列排序：

![image](https://github.com/user-attachments/assets/6128dbe7-1833-49ce-8bd2-cb6a535a6273)

使用数字排序：

![image](https://github.com/user-attachments/assets/cc6cc371-3eae-4df4-991b-335bd7d72573)

倒序排序：

![image](https://github.com/user-attachments/assets/2f07cd76-570a-4665-a4af-8131301af974)

先以第六个域的第2个字符到第4个字符进行正向排序，再基于第一个域进行反向排序：

![image](https://github.com/user-attachments/assets/1df83462-fd9f-47c5-a4b7-e7a7f39923a0)

查看/etc/passwd有多少个shell:

方法对/etc/passwd的第七个域排序并去重，然后统计行数：

![image](https://github.com/user-attachments/assets/2ec76000-8f66-4267-b026-ca2b3376e92d)

### uniq - 去重
![image](https://github.com/user-attachments/assets/02cde232-9ca2-4b5e-ba49-5275dcf73c4d)

该命令用于排完序之后，对排序结果进行去重

![image](https://github.com/user-attachments/assets/c13a6fbd-a3d9-4378-9e36-ccace514de5f)

排序文件，默认是去重：

![image](https://github.com/user-attachments/assets/258a99ef-42e3-48e8-b97b-dd3c4ca17abc)

排序之后删除了重复行，同时在行首位置输出该行重复的次数：

![image](https://github.com/user-attachments/assets/e5eabb6a-53e2-4b91-af80-dafa1b8f03d5)

仅显示存在重复的行，并在行首显示该行重复的次数：

![image](https://github.com/user-attachments/assets/8c1c573c-daa4-42d4-a952-1286a30bdc81)

仅显示不重复的行：

![image](https://github.com/user-attachments/assets/320ece5e-18ff-49d8-86a1-5399a19b9167)

### tee - 同时输出多个文件
从标准输入设备读取数据，将其内容输出到标准输出设备，同时保存成文件。

一般情况下用重定向实现，需要同时输出多个文件时可以使用该命令。

参数：

- -a或–append 　附加到既有文件的后面，而非覆盖它．

将输出同时保存到多个文件中，同时将输出内容显示到控制台：

![image](https://github.com/user-attachments/assets/cb932a4b-8379-42cf-8798-defb8e9b3c07)

### tr - 替换指定的字符
不指定参数时，即表示替换指定的字符为另一个字符，支持指定的字符集合。

参数说明：

- -d, --delete：删除指定的字符
- -s, --squeeze-repeats：缩减连续重复的字符成指定的单个字符

字符集合的范围：

- \NNN 八进制值的字符 NNN (1 to 3 为八进制值的字符)
- \ 反斜杠
- \a Ctrl-G 铃声
- \b Ctrl-H 退格符
- \f Ctrl-L 走行换页
- \n Ctrl-J 新行
- \r Ctrl-M 回车
- \t Ctrl-I tab键
- \v Ctrl-X 水平制表符
- CHAR1-CHAR2 ：字符范围从 CHAR1 到 CHAR2 的指定，范围的指定以 ASCII 码的次序为基础，只能由小到大，不能由大到小。
- [CHAR*] ：这是 SET2 专用的设定，功能是重复指定的字符到与 SET1 相同长度为止
- [CHAR*REPEAT] ：这也是 SET2 专用的设定，功能是重复指定的字符到设定的 REPEAT 次数为止(REPEAT 的数字采 8 进位制计算，以 0 为开始)
- [:alnum:] ：所有字母字符与数字
- [:alpha:] ：所有字母字符
- [:blank:] ：所有水平空格
- [:cntrl:] ：所有控制字符
- [:digit:] ：所有数字
- [:graph:] ：所有可打印的字符(不包含空格符)
- [:lower:] ：所有小写字母
- [:print:] ：所有可打印的字符(包含空格符)
- [:punct:] ：所有标点字符
- [:space:] ：所有水平与垂直空格符
- [:upper:] ：所有大写字母
- [:xdigit:] ：所有 16 进位制的数字
- [=CHAR=] ：所有符合指定的字符(等号里的 CHAR，代表你可自订的字符)

将文件testfile中的小写字母全部转换成大写字母：

![image](https://github.com/user-attachments/assets/451f83d6-daa5-40a3-9c13-5b4397256541)

缩减连续重复的字符成指定的单个字符：

![image](https://github.com/user-attachments/assets/23b5a452-4f09-46cd-83cd-16ff063a3598)

删除指定的字符：

![image](https://github.com/user-attachments/assets/0bc931a2-d94c-4199-bd0b-41303549c73f)

### join - 文件按行连接
将两个文件中指定栏位相同的行连接起来。即按照两个文件中共同拥有的某一列，将对应的行拼接成一行。

注意：在使用join之前所处理的文件要事先经过排序。

![image](https://github.com/user-attachments/assets/fa0ecd18-9c4d-4e78-a73b-39309c1e4855)

使用join命令，将两个文件连接：

![image](https://github.com/user-attachments/assets/76388ce1-d482-4d2e-90ee-ab925b2150f1)

两个文件互换，输出结果的变化：

![image](https://github.com/user-attachments/assets/e1281a47-42c1-4fcc-9dd0-883aee9fb0ba)

参数：

- -a<1或2> 除了显示原来的输出内容之外，还显示指令文件中没有相同栏位的行。
- -e<字符串> 若[文件1]与[文件2]中找不到指定的栏位，则在输出中填入选项中的字符串。
- -i或–igore-case 比较栏位内容时，忽略大小写的差异。
- -o<格式> 按照指定的格式来显示结果。
- -t<字符> 使用栏位的分隔字符。
- -v<1或2> 跟-a相同，但是只显示文件中没有相同栏位的行。
- -1<栏位> 连接[文件1]指定的栏位。
- -2<栏位> 连接[文件2]指定的栏位。

### paste-将多个文件对应行链接在一起
paste 指令会把每个文件以列对列的方式，一列列地加以合并。

语法：

![image](https://github.com/user-attachments/assets/337146ab-972f-4dd5-b415-b57b34ce6ddb)

参数：

- -d<间隔字符>或–delimiters=<间隔字符> 　用指定的间隔字符取代跳格字符。
- -s或–serial 　串列进行而非平行处理。
- [文件…] 指定操作的文件路径

使用paste指令将文件"file"、“testfile”、"testfile1"进行合并，输入如下命令：

![image](https://github.com/user-attachments/assets/cc773dbc-e509-4e63-9f04-12080d9520f9)

参数"-s"可以将一个文件中的多行数据合并为一行进行显示：

![image](https://github.com/user-attachments/assets/f788b6fb-b4f8-4f99-ba0f-50505a8019d1)

如果将文件位置改为-，表示接收标准输入：

![image](https://github.com/user-attachments/assets/4c81b2e5-15f3-499f-9db2-76c0f3680d63)

### split - 文件切割
split命令用于将一个文件分割成数个。

该指令将大文件分割成较小的文件，在默认情况下将按照每1000行切割成一个小文件。

语法：

![image](https://github.com/user-attachments/assets/b29f031d-8d39-4bfa-9e11-e5eea1325dc1)

参数说明：

- -<行数> : 指定每多少行切成一个小文件
- -b<字节> : 指定每多少字节切成一个小文件
- -C<字节> : 与参数"-b"相似，但是在切 割时将尽量维持每行的完整性
- [输出文件名] : 设置切割后文件的前置文件名， split会自动在前置文件名后再加上编号

使用指令"split"将文件"README"每6行切割成一个文件，输入如下命令：

![image](https://github.com/user-attachments/assets/bc23b7d0-d33e-431a-b16e-77a19d02fbdb)

以上命令执行后，指令"split"会将原来的大文件"README"切割成多个以"x"开头的小文件。而在这些小文件中，每个文件都只有6行内容。

以大小切割：

![image](https://github.com/user-attachments/assets/640c407c-4a7f-4d19-9491-58c0dedc781d)

### xargs - 参数代换
不是所有的命令都支持管道，如ls，对于不支持管道的命令，可以通过xargs让其有管道命令的效果，如下所示：

![image](https://github.com/user-attachments/assets/6d5d99b1-d300-443d-bab4-241e1b165c23)

如果没有xargs，ls -l的结果将不是前面find的标准输出，因为ls不支持管道命令。

xargs 用作替换工具，读取输入数据重新格式化后输出。

定义一个测试文件，内有多行文本数据：

![image](https://github.com/user-attachments/assets/83f38859-bf7c-4d57-8320-8eead6e53f29)

多行输入单行输出：

![image](https://github.com/user-attachments/assets/f63a15de-d001-4e45-aedc-ac8b50596070)

-n 选项多行输出：

![image](https://github.com/user-attachments/assets/01ecac0b-2238-4707-987d-e8509e04cf82)

-d 选项可以自定义一个定界符：

![image](https://github.com/user-attachments/assets/b71feb0a-5593-4945-800f-9304980de8cc)

结合 -n 选项使用：

![image](https://github.com/user-attachments/assets/3192fde6-07de-4094-8344-85301d1a6ec0)

读取 stdin，将格式化后的参数传递给命令:

![image](https://github.com/user-attachments/assets/8e02252f-9344-4165-a58b-04c458267386)

选项-I指定一个替换字符串 {}，这个字符串在 xargs 扩展时会被替换掉。

复制所有图片文件到 /data/images 目录下：

![image](https://github.com/user-attachments/assets/698a99ed-9356-4264-9397-69da5e1ed019)

选项-n 后面加次数，表示命令在执行的时候一次用的argument的个数，默认是用所有的。

xargs 结合 find 使用

用 rm 删除太多的文件时候，可能得到一个错误信息：/bin/rm Argument list too long. 用 xargs 去避免这个问题：

![image](https://github.com/user-attachments/assets/97257714-e6c6-4c54-90bc-35301112305a)

xargs -0 将 \0 作为定界符。

统计一个源代码目录中所有 php 文件的行数：

![image](https://github.com/user-attachments/assets/90b81d90-bcf7-4d00-9d51-16c962e85006)

查找所有的 jpg 文件，并且压缩它们：

![image](https://github.com/user-attachments/assets/82e186ec-9280-45e2-8df7-fbcb4130fb49)

批量下载：

![image](https://github.com/user-attachments/assets/e96b0721-c1bc-4dae-9f2f-8b64d9c7fb04)

wget的-c选项表示断点续传。
