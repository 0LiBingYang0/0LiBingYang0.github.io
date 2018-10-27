# Hadoop伪分布式环境配置
- 伪分布式环境配置的前提是Hadoop单点环境的配置,如果未配置单点环境,
请参考[Hadoop单点环境配置](https://0libingyang0.github.io/Environment/Hadoop01)
- 步骤
进入目录下hadoop-2.7.3/etc/hadoop/进行配置


- 1.vim haooop-env.sh 将$JAVA_HOME的路径设置为当前系统Java_HOME的路径
	
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-c2159d56e5c90149.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 2.vim core-site.xml将
	`<`property`>`  
        `<`name`>`hadoop.tmp.dir`<`/name`>`  
        `<`value`>`/home/111/tmp`<`/value`>`
    `<`/property`>`  
    `<`property`>`  
        `<`name`>`fs.defaultFS`<`/name`>`  
        `<`value`>`hdfs://localhost:9000`<`/value`>`  
    `<`/property`>`
    写入	
	
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-3a14e08374d90be5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 3.vim hdfs-site.xml将 
    `<`property`>`    
        `<`name`>`dfs.namenode.name.dir`<`/name`>`    
        `<`value`>`file:/home/111/dfs/name`<`/value`>`    
    `<`/property`>`    
    `<`property`>`    
        `<`name`>`dfs.datanode.data.dir`<`/name`>`    
        `<`value`>`file:/home/111/dfs/data`<`/value`>`    
    `<`/property`>`
	写入
	
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-57b6179e5d090977.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	
- 4.vim yarn-site.xml 将

	`<`property`>`  
		`<`name`>`mapreduce.framework.name`<`/name`>`  
		`<`value`>`yarn`<`/value`>`  
	`<`/property`>`  
  
	`<`property`>`  
		`<`name`>`yarn.nodemanager.aux-services`<`/name`>`  
		`<`value`>`mapreduce_shuffle`<`/value`>`  
	`<`/property`>`
	
写入

	![image.png](https://upload-images.jianshu.io/upload_images/14498135-7152cc70687e93a4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	
- 5.配置mapred-site.xml 
	- (1) cp mapred-site.xml.template mapred-site.xml(从mapred-site.xml.template(msx模板)将msx复制出来)
	- (2) vim mapred-site.xml将
		`<`property`>`
			`<`name`>`mapreduce.framework.name`<`/name`>`
			`<`value`>`yarn`<`/value`>`
		`<`/property`>`
		写入
		
		![image.png](https://upload-images.jianshu.io/upload_images/14498135-48f021aff221fd58.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 6.配置完成以后将namenode的存储位置进行格式化
	- hadoop namenode -format
		出现 storage.......successfully证明配置成功
		
		![image.png](https://upload-images.jianshu.io/upload_images/14498135-b32e15b71bef2db1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
		
		然后开启所有服务 start-all.sh	然后jps 出现 SecondaryNameNode  ResourceManager NameNode DataNode NodeManager Jps 这六个即可证明配置为分布式成功
	
		![image.png](https://upload-images.jianshu.io/upload_images/14498135-bbeb0d8bae6ca224.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)




	
		




	
	