##azkaban工作流调度器配置步骤

- 1.将azkaban-executor-server-2.5.0.tar.gz(存放了执行器) azkaban-web-server-2.5.0.tar.gz(存放了web服务器) 
azkaban-sql-script-2.5.0.tar.gz  (存放了azkaban运行时需要的sql) 三个压缩包解压
- 2.创建文件夹azkaban将三个压缩包解压后的文件夹移动至该目录下:mv 文件名 /azkaban
- 3.azkaban脚本导入:进入mysql 创建azkaban数据库并使用azkaban数据库在azkaban中执行azkaban中的create-all-sql-2.5.0.sql文件:source /home/111/azkaban/azkaban-2.5.0/create-all-sql-2.5.0.sql

![image.png](https://upload-images.jianshu.io/upload_images/14498135-2e98be6250bd4229.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![image.png](https://upload-images.jianshu.io/upload_images/14498135-90265140d526adda.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 4. 创建SSL配置:keytool -keystore keystore -alias jetty -genkey -keyalg RSA输入密码后所有选项全部回车即可
输入jetty的秘钥口令如果想和秘钥库口令相同会回车即可

![image.png](https://upload-images.jianshu.io/upload_images/14498135-8f8d70c4f5b24613.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 5.将生成的秘钥拷贝到azkaban-web目录下(6-7设置均在该目录下进行)

![image.png](https://upload-images.jianshu.io/upload_images/14498135-60d005b8aeed06d8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 6.修改azkaban.properties文件:vim conf/azkaban.properties

![image.png](https://upload-images.jianshu.io/upload_images/14498135-af63bf97a6b2148a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![image.png](https://upload-images.jianshu.io/upload_images/14498135-678aede80acee573.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![image.png](https://upload-images.jianshu.io/upload_images/14498135-841acac69d76c00f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 7.修改azkaban-users.xml(设置用户名及权限添加超级用户)

![image.png](https://upload-images.jianshu.io/upload_images/14498135-7e70c50e3fa0a428.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![image.png](https://upload-images.jianshu.io/upload_images/14498135-73b33f472eb991a0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 8.azkaban执行器的配置切换到azkaban-excutor-2.5.0目录下

![image.png](https://upload-images.jianshu.io/upload_images/14498135-cffe651f2d8e1a09.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 9.修改azkaban.properties文件

![image.png](https://upload-images.jianshu.io/upload_images/14498135-f2a998cdd041f88b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 10.因为没有配置azkaban的环境变量,并且azkaban配置文件中写的路径都是相对于执行器或者web的路径,
所以开启服务要在执行器和web的根目录下执行命令 bin/azkaban-xxxxxxx-start.sh 
在两个服务进程全部开启以后访问浏览器https://ip:8443(因为进行了SSL设置)即可进入azkaban网页登录界面

![image.png](https://upload-images.jianshu.io/upload_images/14498135-e0f57b8d1b2e453c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

