
## hdfs 工作机制(1)

#### 概述

* hdfs集群：NameNode（Secondary NameNode）、DataNode
  * NameNode负责元数据；DataNode负责数据块
* 心跳机制：dataNode 会定期汇报自身情况，nameNode负责保持DataNode数量（文件副本数量;
            当dataNode发生意外，nameNode会把block转移到另一个中
* 客户端看不见hdfs内部机制，通过namenode申请访问

#### 写数据流程

*  客户端将数据进行block分块
*  确认通信，获得通信的dataNode
*  建立通信通道，逐个传递block给对应的dataNode
*  由接受block的dataNode负责向其他dataNode传递副本

  ![image.png](https://upload-images.jianshu.io/upload_images/14466577-3f5593035b3e5898.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
   
  ![image.png](https://upload-images.jianshu.io/upload_images/14466577-0c19e90d2d3955dc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


#### 读数据流程   

* 客户端将路径发给nameNode,从nameNode获取block原信息（主要是block存放位置）返回
* 客户端通过返回信息，找对应dataNode，获取文件block
* 在客户端本地进行数据合并，获得整个文件

  ![image.png](https://upload-images.jianshu.io/upload_images/14466577-13e524724582ce14.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  
  ![image.png](https://upload-images.jianshu.io/upload_images/14466577-9af53e8601bbe8f2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### nameNode工作机制

* 职责：负责客户端请求响应；元数据管理
* 存储形式
  * 元数据meta data：内存中，内存在namenode中
  * 镜像文件fsimage:namenode工作目录中
  * 数据操作日志文件edits:负责衔接metadata和fsimage
  
#### 元数据的checkpoint

* 一段时间，Secondary NameNode将nameNode上积累的所有edits和一个最新的fsimage下载到本地，
  并加载到内存进行merge，这个过程称为checkpoint。
  
  ![image.png](https://upload-images.jianshu.io/upload_images/14466577-ab4aa48f2f4d9a8b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
   
  ![image.png](https://upload-images.jianshu.io/upload_images/14466577-e7c2e77aa2c81251.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 
#### namenode路径/current/目录下文件
* VERSION（java属性文件）
* seen_txid：edits文件滚动序号
* format的同时也会生成fsimage和edits文件，及其对应的md5校验文件。

#### Secondary nameNode
* fsimage 它是在NameNode启动时对整个文件系统的快照；
* edit logs 它是在NameNode启动后，对文件系统的改动序列；
* Secondary NameNode 就是把这两个变成完整数据放到内存中，又叫检查节点，不是nameNode的备份；
* nameNode和Secondary nameNode（检查节点）工作存储目录完全相同；
* 当namenode故障退出需要重新恢复时，可以从secondary namenode的工作目录中将fsimage拷贝到namenode的工作目录，以恢复namenode的元数据
* [相关](https://www.xuebuyuan.com/3196294.html)








