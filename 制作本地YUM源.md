原文链接：https://blog.csdn.net/as604049322/article/details/120446586


## 制作本地YUM源
上传CentOS-6.7-x86_64-bin-DVD1.iso到服务器

将CentOS-6.7-x86_64-bin-DVD1.iso镜像挂载到某个目录:

![image](https://github.com/user-attachments/assets/1307b225-46b3-4ad7-9720-fec1f7335db3)

安装并启动Apache服务器：

![image](https://github.com/user-attachments/assets/72a06075-22ef-421a-bf07-5c80a81670ed)

使用浏览器访问http://192.168.100.101（如果访问不通，检查防火墙是否开启了80端口或关闭防火墙）

将YUM源配置到httpd中：

![image](https://github.com/user-attachments/assets/9aaa3971-d48d-47cb-97c8-8816e9099bde)

在浏览器中访问http://192.168.100.101/CentOS-6.7/

![image](https://github.com/user-attachments/assets/f2f5b28e-e4c0-4391-8691-b6866f35ed87)

**配置使用YUM源：**

备份原有的YUM源的配置文件

![image](https://github.com/user-attachments/assets/35aa3ee1-c9b5-4f5d-beae-b4f2db0b0ba0)

修改YUM源配置文件

![image](https://github.com/user-attachments/assets/e8674601-9834-44b4-823e-3dc86aa9bb47)

重建yum缓存

![image](https://github.com/user-attachments/assets/208b9199-ba72-4167-a2f2-d98e3aaee430)

**rpm包生成yum源目录**

如果已经下载好了rpm包，可以自行制作一个yum源（yum仓库）。将下载的rpm包上传到centos服务器上（比如/data/rpm目录下），然后进入存放rpm包的目录，执行以下命令：

![image](https://github.com/user-attachments/assets/9bb7733a-c3d9-47ea-a021-97201305a4b8)

这样，rpm包存放的目录就可以作为yum源目录使用。

如果提示找不到createrepo命令，可以使用yum install createrepo安装该程序。
