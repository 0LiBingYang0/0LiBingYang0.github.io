# Java环境配置
1.将下载好的jdk-8u181-linux-x64.tar.gz压缩包放到/usr里面(图1)

![图1.png](https://upload-images.jianshu.io/upload_images/14498135-a746353f0b8f831a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

2.解压压缩包(图2)
tar -zxvf jdk-8u181-linux-x64.tar.gz
![图2.png](https://upload-images.jianshu.io/upload_images/14498135-bbd2cb2c6982dbd0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

3.在/etc/profile中配置环境变量(图3)
vim /etc/profile
![图3.jpg](https://upload-images.jianshu.io/upload_images/14498135-d88daa0f55d5e7f5.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4.重启虚拟机或者执行 source /etc/profile

5.验证jdk安装成功(图4)
java -version
![图4.png](https://upload-images.jianshu.io/upload_images/14498135-d39ae9e082142ab5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)