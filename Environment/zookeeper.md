## zookeeper单点环境配置
- 1.解压zookeeper压缩包
- 2.进入解压后的文件夹下的conf文件夹下 复制zoo_simple.cfg文件命名为zoo.cfg 并编辑该文件
	- cd ~/zookeeper-3.4.6/conf 
	- cp zoo_simple.cfg zoo.cfg
	- vim zoo.cfg
	
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-677b1609fda3ca8e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 3.在bin目录下运行该目录下的skServer.sh文件
	- ./skServer.sh start
- 4.在zookeeper-3.4.6/skdata下将"1"追加进myid
	- echo "1" >> myid
	
	
	
## zookeeper伪分布式环境配置
- 伪分布式(在一台电脑上面模拟出集群运行环境)
- 1.创建sk文件夹将解压三份分别命名为zk1 zk2 zk3
- 2.进入解压后的文件夹下的conf文件夹下 复制zoo_simple.cfg文件命名为zoo.cfg 并编辑该文件以zk1为例
	- cd ~/zookeeper-3.4.6/conf 
	- cp zoo_simple.cfg zoo.cfg
	- vim zoo.cfg(三个端口号必须不相同)
	
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-32238d1e772a37b6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

	
- 3.在bin目录下运行该目录下的skServer.sh文件
	- ./skServer.sh start
- 4.在zookeeper-3.4.6/skdata下将"1,2,3"追加进各自的myid
	- echo "1" >> myid
	
	
## zookeeper完全分布式环境配置
- 完全分布式环境配置与伪分布式大体相同,唯一不同之处在于完全分布式是在多台电脑上面配置(完全分布式与伪分布式配置的时候都需要注意的是配置环境的电脑的个数为奇数)
- 在每个电脑上面配置的文件与步骤与伪分布式相同(配置文件时不用更改端口号三个端口号要保持一致)

![image.png](https://upload-images.jianshu.io/upload_images/14498135-11d657dcc72f6d61.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

