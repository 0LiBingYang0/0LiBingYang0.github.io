# Hadoop分布式配置

- 准备阶段:一个新的关闭防火墙的并且能够执行ifconfig以及vim的虚拟机(root用户和普通用户)普通用户具有sudo权限,在普通用户的根目录下有解压的Jdk以及Hadoop文件夹 将此虚拟机克隆三份
一个伪分布式安装好[Hadoop伪分布式](https://0libingyang0.github.io/Environment/Hadoop02)的虚拟机 
- 配置阶段:

1.将三台克隆机的Java与Hadoop单点环境配置好 将配置好的伪分布式作为namenode将三台新的克隆机作为datanode
2.利用远程文件拷贝命令(scp)将文件夹及其目录下的文件传到另外的三个克隆机上 scp -r 目标文件夹 用户名:ip:存放的路径()

![image.png](https://upload-images.jianshu.io/upload_images/14498135-eee6591b91a29711.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

3.设置 sudo vim /etc/hosts 按照下图的格式添加节点

![image.png](https://upload-images.jianshu.io/upload_images/14498135-6a088512e0219bef.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4.设置 ~/hadoop2.7.3/etc/hadoop/slaves 将三个datanode的ip写进去

5.设置免密
(1) ssh-keygen


(2) ssh-copy-id 设置免密的用户名@ip(因为是四台虚拟机所以需要执行4次,一台namenode三台datanode)

6.start-all.sh 

在namenode中执行jps

![image.png](https://upload-images.jianshu.io/upload_images/14498135-44b6c30a76073647.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

在datanode中执行jps

![image.png](https://upload-images.jianshu.io/upload_images/14498135-dd0b4a48f1935d04.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

即证明分布式配置成功

- 免密原理图

![123.jpg](https://upload-images.jianshu.io/upload_images/14498135-107a37cc78e5520e.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)