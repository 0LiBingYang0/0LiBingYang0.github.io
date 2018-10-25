# Hadoop单点环境配置
- 在配置Hadoop环境之前先确保系统中Java环境已经配置好
	- 验证Java配置好的Java环境
	- ![image.png](https://upload-images.jianshu.io/upload_images/14498135-5624ff1b2dfd1e51.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 如果还未配置,先配置环境 [Java环境](https://0libingyang0.github.io/Environment/Java)
- 配置好Java环境后
	- 1.将hadoop2.7.3解压 tar -zxvf hadoop2.7.3.gz.tar
	- 2.解压完毕后编辑.bash_profile或者/etc/profile文件
	
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-f7ed921df927664f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 3. 编辑完毕后退出并执行该文件 (. .bash_profile或者. /etc/profile)
	- 4. 验证Hadoop安装成功
		- 1.hadoop version
		* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-fe5b6f96f961e88f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
		- 2.成功后使用 /hadoop-2.7.3/share/hadoop/mapreduce/hadoop-mapreduce-examples-2.7.3.jar 中的wordcount命令进一步验证(wordcount命令是统计文件中的所有
		词语,并分项统计)
		* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-507cf685e5b0be2e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
		* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-b8d21dfc884f534e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
		* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-1e858515d16ed507.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
		* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-97da3f98dbf48206.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
		