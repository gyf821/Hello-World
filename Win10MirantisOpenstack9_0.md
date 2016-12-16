#  #第一章 安装准备
安装系统用的硬件越高越好，至少要满足：8G内存、300G的硬盘空间。本说明的安装的环境是在Win10系统下，12G内存，I盘空间有318G。另外，还需要准备下述的工具和文件。  
1、	工具  
Cygwin  
Xshell  
Xftp  
VirtualBox及其扩展包  
2、	MOS9.0版本    
在下面地址下载：https://www.mirantis.com/software/openstack/  
3、	本地源文件  
 MOS9.0本地源下载：http://pan.baidu.com/s/1gfe69iV 密码：b2m5  
MOS9.0 bootstrap下载：http://pan.baidu.com/s/1gfc4w6n 密码：o9x4  
链接参考来源：http://blog.csdn.net/qq_20154221/article/details/51906866  

 
#  #第二章	安装过程
一 安装master节点：
master安装时，必须使用fuelmenu取消bootstrap设置：  
 ![img](https://raw.githubusercontent.com/gyf821/Hello-World/master/pic/bootstrap.png)  
输入enter后，切换到Bootstrap Image:  
![img](https://raw.githubusercontent.com/gyf821/Hello-World/master/pic/bootstrap01.png)  
设置成功后的这样：  
![img](https://raw.githubusercontent.com/gyf821/Hello-World/master/pic/bootstrap02.png)  
之后一直等待，直到成功：  
![img](https://raw.githubusercontent.com/gyf821/Hello-World/master/pic/mastersucess.png)  
 二 设置bootstrap:  
 使用xshell连接到master节点的10.20.0.2:22上。使用fuel-bootstrap list查看是空的：  
 ![img](https://raw.githubusercontent.com/gyf821/Hello-World/master/pic/bootstrap201.png)  
使用Xftp上传解压后的bootstrap和mirror文件夹到master节点的10.20.0.2上的/var/www/nailgun下面，并覆盖bootstrap文件夹。  
![img](https://raw.githubusercontent.com/gyf821/Hello-World/master/pic/bootstrap202.png)   

之后，  
![img](https://raw.githubusercontent.com/gyf821/Hello-World/master/pic/bootstrap203.png)   
然后激活，注意激活过程可能等的时间比较长（大约几分钟）：  
![img](https://raw.githubusercontent.com/gyf821/Hello-World/master/pic/bootstrap204.png)   


三 安装slave节点：  
使用launch.sh安装过程中master安装后就失败了：  
 ![img](https://raw.githubusercontent.com/gyf821/Hello-World/master/pic/bootstrap301.png)  
使用编辑后的slavelaunch.sh安装slave节点：  
 ![img](https://raw.githubusercontent.com/gyf821/Hello-World/master/pic/bootstrap302.png)  
等着三个slave节点自动完成即可，下面的选择也不用改变：  
 ![img](https://raw.githubusercontent.com/gyf821/Hello-World/master/pic/bootstrap303.png)  
安装成功后的情况：  

![img](https://raw.githubusercontent.com/gyf821/Hello-World/master/pic/bootstrap304.png)  
 

 

登录之后查看设备中的新增的3个slave节点：  
 
![img](https://raw.githubusercontent.com/gyf821/Hello-World/master/pic/bootstrap305.png)  
