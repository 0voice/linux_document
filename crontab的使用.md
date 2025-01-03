原文链接：https://blog.csdn.net/as604049322/article/details/120446586


## crontab的使用
crontab命令是cron table的简写，它是cron的配置文件，也可以叫它作业列表。

相关配置文件如下：

- /var/spool/cron/ 目录下存放的是每个用户包括root的crontab任务，每个任务以创建者的名字命名
- /etc/crontab 这个文件负责调度各种管理和维护任务。
- /etc/cron.d/ 这个目录用来存放任何要执行的crontab文件或脚本。
- 还可以把脚本放在/etc/cron.hourly、/etc/cron.daily、/etc/cron.weekly、/etc/cron.monthly目录中，让它每小时/天/星期、月执行一次。

命令格式：

![image](https://github.com/user-attachments/assets/ba49a2cd-cf78-4302-ae12-02b01b311d9b)

**crontab -e**进入当前用户的工作表编辑，是常见的vim界面。每行是一条命令。

crontab的命令构成为 时间+动作，其时间有**分、时、日、月、周**五种，操作符有

- ***** 取值范围内的所有数字
- / 每过多少个数字
- - 从X到Z
- **，**散列数字
  
基本格式 :

![image](https://github.com/user-attachments/assets/ad6fbea9-84b8-4bb3-8ecf-2ba01ccdcaac)

![image](https://github.com/user-attachments/assets/426ed76b-27ee-4448-9420-732c9cd7169f)

- 其中 f1 是表示分钟，f2 表示小时，f3 表示一个月份中的第几日，f4 表示月份，f5 表示一个星期中的第几天。command表示要执行的命令。
- 当 f1 为 * 时表示每分钟都要执行 program，f2 为 * 时表示每小时都要执行程序，以此类推
- 当 f1 为 a-b 时表示从第 a 分钟到第 b 分钟这段时间内要执行，f2 为 a-b 时表示从第 a 到第 b 小时都要执行，以此类推
- 当 f1 为 */n 时表示每 n 分钟个时间间隔执行一次，f2 为 */n 表示每 n 小时个时间间隔执行一次，以此类推
- 当 f1 为 a, b, c,… 时表示第 a, b, c,… 分钟要执行，f2 为 a, b, c,… 时表示第 a, b, c…个小时要执行，以此类推

在 12 月内, 每天的早上 6 点到 12 点，每隔 3 个小时 0 分钟执行一次 /usr/bin/backup

![image](https://github.com/user-attachments/assets/1786b4e6-a888-40a3-a5e4-fbc6872e3af6)

周一到周五每天下午 5:00 寄一封信给 alex@domain.name

![image](https://github.com/user-attachments/assets/5218ae3a-6863-42ac-b8c3-e54031939e0a)

每月每天的午夜 0 点 20 分, 2 点 20 分, 4 点 20 分…执行 echo “haha”

![image](https://github.com/user-attachments/assets/7966e7a6-909a-467e-a669-e4d7fbf12d07)

示例1：

![image](https://github.com/user-attachments/assets/44b4bb24-770b-49a5-917b-eecb35df5f58)

示例2：

![image](https://github.com/user-attachments/assets/bd3bae38-d7e9-41a1-a03b-72c6699614a3)

**环境变量问题：**

有时创建了一个crontab，但是这个任务却无法自动执行，而手动执行这个任务却没有问题，这种情况一般是由于在crontab文件中没有配置环境变量引起的。

所以注意如下3点：

1）脚本中涉及文件路径时写全局路径；

2）脚本执行要用到java或其他环境变量时，通过source命令引入环境变量，如：

![image](https://github.com/user-attachments/assets/abbba1e0-083c-4d75-a751-ee333279885b)

3）当手动执行脚本OK，但是crontab死活不执行时，可以尝试在crontab中直接引入环境变量解决问题。如：

![image](https://github.com/user-attachments/assets/17de4fdc-e7b8-4563-988b-f0bfd82088af)
