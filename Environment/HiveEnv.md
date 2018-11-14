## Hive环境搭建
- 搭建hive环境之前要首先保证[MySQL环境](https://0libingyang0.github.io/Environment/MySQLEnv)搭建成功
- 1.上传apache-hive-1.2.1-bin.tar.gz压缩包到服务器
- 2.解压压缩包:tar -zxvf apache-hive-1.2.1-bin.tar.gz 
- 3.将解压后压缩包的文件夹名字改为hive(可做可不做,方便以下的环境配置)
- 4.将MySQL的驱动包放到/hive/lib下
- 5.在/etc/profile中配置Hive环境变量并把hive加入PATH中,配置结束后执行该文件
	- (1)sudo vim /etc/profile 
	- (2)export HIVE_HOME=/home/111/hive(解压后的文件夹的路径)
	- (3)export PATH=$PATH:$HIVE_HOME/bin
	- (4). /etc/profile(执行该文件)
	
![image.png](https://upload-images.jianshu.io/upload_images/14498135-a271ed8e0121acb1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 6.在hive/conf/目录下创建hive-site.xml将配置写入

`<`configuration`>`
	`<`property`>`
		`<`name`>`javax.jdo.option.ConnectionURL`<`/name`>`
		`<`value`>`jdbc:mysql://localhost:3306/hivedb?createDatabaseIfNotExist=true`<`/value`>`
	`<`/property`>`
	`<`property`>`
		`<`name`>`javax.jdo.option.ConnectionDriverName`<`/name`>`
		`<`value`>`com.mysql.jdbc.Driver`<`/value`>`
	`<`/property`>`
	`<`property`>`
		`<`name`>`javax.jdo.option.ConnectionUserName`<`/name`>`
		`<`value`>`root`<`/value`>`
	`<`/property`>`
	`<`property`>`
		`<`name`>`javax.jdo.option.ConnectionPassword`<`/name`>`
		`<`value>123456</value`>`
	`<`/property`>`
`<`/configuration`>`


![image.png](https://upload-images.jianshu.io/upload_images/14498135-aaf7699f5719a770.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 7.配置完成以后在命令行输入hive

![image.png](https://upload-images.jianshu.io/upload_images/14498135-dc893f397c2ac82a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

