原文链接：https://blog.csdn.net/as604049322/article/details/120446586


## 掩码umask
### umask的作用
umask值用于设置用户在创建文件时的默认权限，当我们在系统中创建目录或文件时，目录或文件所具有的默认权限就是由umask值决定的。

对于root用户，系统默认的umask值是0022；对于普通用户，系统默认的umask值是0002。执行umask命令可以查看当前用户的umask值。

![image](https://github.com/user-attachments/assets/8a64382b-a676-4b1e-800f-579c9fb0ecb9)

### umask是如何改变新文件的权限
umask值一共有4组数字，其中第1组数字用于定义特殊权限，一般不予考虑，与一般权限有关的是后3组数字。

默认情况下，对于目录，用户所能拥有的最大权限是777；对于文件，用户所能拥有的最大权限是目录的最大权限去掉执行权限，即666。因为x执行权限对于目录是必须的，没有执行权限就无法进入目录，而对于文件则不必默认赋予x执行权限。

对于root用户，他的umask值是022。当root用户创建目录时，默认的权限就是用最大权限777去掉相应位置的umask值权限，即对于所有者不必去掉任何权限，对于所属组要去掉w权限，对于其他用户也要去掉w权限，所以目录的默认权限就是755；当root用户创建文件时，默认的权限则是用最大权限666去掉相应位置的umask值，即文件的默认权限是644。

通过umask命令可以修改umask值，比如将umask值设为0077。

![image](https://github.com/user-attachments/assets/c32bf5e3-1a7f-480d-adcb-7598dea72821)

### 永久修改umask
umask命令只能临时修改umask值，系统重启之后umask将还原成默认值。如果要永久修改umask值，可修改/etc/bashrc或/etc/profile文件。

例如要将默认umask值设置为027，那么可以在文件中增加一行umask 027。
