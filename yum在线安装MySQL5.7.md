原文链接：https://blog.csdn.net/as604049322/article/details/120446586


## yum在线安装MySQL5.7
Step1: 检测系统是否自带安装mysql

![image](https://github.com/user-attachments/assets/f6f5209d-ce32-4a61-8ec4-bfdcd3534a72)

Step2: 删除系统自带的mysql及其依赖

![image](https://github.com/user-attachments/assets/08dd7f37-39b5-4eb0-94e7-10d4bc4eedbe)

Step3: 给CentOS添加rpm源，并且选择较新的源

![image](https://github.com/user-attachments/assets/123b4393-efa8-44be-8224-dbac87088314)

Step4:安装mysql 服务器

![image](https://github.com/user-attachments/assets/994d5573-c3e0-45c8-8516-52fe04e10643)

Step5: 启动mysql

![image](https://github.com/user-attachments/assets/927a9779-325b-4499-baa8-7d6d055b158a)

grep “password” /var/log/mysqld.log(查看临时密码)

![image](https://github.com/user-attachments/assets/49e10bea-1496-40e3-8ad9-034f1908c76b)

默认的要求必须的设置格式：

**包含数字、小写或大写字母以及特殊字符**

默认的要求必须的设置格式：

**包含数字、小写或大写字母以及特殊字符**

如果不想复杂，可以使用以下方式

![image](https://github.com/user-attachments/assets/79ef6bda-6622-4fa5-89bc-48f0e282164e)

Step6: 查看mysql是否自启动,并且设置开启自启动

![image](https://github.com/user-attachments/assets/e7d8dad6-7401-43dc-8635-ea6c600ebb19)

Step7: mysql安全设置

![image](https://github.com/user-attachments/assets/a9ab7c60-e2c8-4807-8c86-9f017dbc7dd8)
