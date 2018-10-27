#sed & awk

##sed

格式:sed 选项 '动作' filename
选项
-n 安静模式,即 sed -n 'p' aaa.txt 完整输出文件中内容
-e 直接在指令列模式上进行sed动作编辑
-f 直接将sed的 动作写在一个档案内,-f filename 则可以执行 filename内的sed动作
-r sed的动作支持的是延伸型正规表示法的语法.(默认的是基础正规表示法语法)
-i 直接修改读取的档案内容,而不是由屏幕输出
动作
- a 新增,a的后面可以接字符串,这些字符串会在新的一行出现(目前的下一行) 
	- 在第一行下面插入:sed '1a asd' 123.txt(1)
	- ![1.png](https://upload-images.jianshu.io/upload_images/14498135-8321ef9f5dc401ba.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 在每一行下面增加:sed 'a asd' 123.txt(2)
	- ![2.png](https://upload-images.jianshu.io/upload_images/14498135-4ef71c082ef2eb88.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 在1-5行下面插入:sed '1,5a asd' 123.txt(3)
	- sed ![3.png](https://upload-images.jianshu.io/upload_images/14498135-dd588882e20ed7d3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- i 插入,i的后面可以接字符串,二这些字符串会在新的一行出现(当前行的上一行)具体的用法与-a相同
	- eg:在第一行上面插入: sed '1i asd' 123.txt(4)
	- ![4.png](https://upload-images.jianshu.io/upload_images/14498135-f01d0547500120c7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- c 取代,c的后面可以接字符串,这些字符串可以取代多行间的内容
	- 替换掉所有的内容:sed 'c asd' 123.txt
	- ![image.png](https://upload-images.jianshu.io/upload_images/14498135-8666735bdd315c2d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	d 删除
	p 输出 1p 打印第一行 1,5拍打印1-5行  5,p 从第五行打印到结尾
	s 替换经常配合正则进行操作
	w 写入 sed 'w 要被写入的文件(目标文件)' 读取内容的文件(源文件)只要是w向文件
	中进行写入就会将目标文件之前的内容全部干掉
	r读取 sed '2r 要读取的文件' 加入数据的文件(目标文件)
高级操作
	| 管道符,使用该符号配合其他命令
	{} 可以让sed执行多个动作,只是动作之间要用";"分号隔开
	&替换 
	&相当于占位符的作用 就是我们 s/查询条件/查询到的内容
	可以在s/查询条件/要替换成的内容中进行使用,实现追加的效果
	\u转成大写可以配合我们的&来实现将匹配内容转换成大写的操作
	
	在passwd文件中获取username.userid,groupid进行展示()分组功能
	sed 's/\([a-z0-9_-]\+\):x:\([0-9]\+\):\([0-9]\+\):.*$/user: \1/' passwd
	怎么在sed中获取分组得到的内容呢?
	首先分组的序号是从1开始的并且是按照从左到右的顺序排的
	要获取使用\分组的序号来进行获取,例如\1就是个占位符
	
## awk

### awk [选项] 'command' filename

-F 设置分隔符,默认使用" "空格来切割  NR 行号   NF 列号(通过分隔符分成的组数)   $n 以分隔符分隔后的n段数据以$1-$n表示
awk -F ':' '{print NR}' /etc/passwd 以":"为分隔符将/etc/passwd中的行数输出
eg: awk -F ':' '{printf("Line:%s Col:%s User:%s\n",NR,NF,$1)}' /etc/passwd


- 输出：
  - {print "输出内容"}直接输出
  - {prinf("%s\n",$n)}输出内容的格式,内容
- 使用正则：
~/正则规则/
！~// 正则规则取非
- if语句  
  
### 拓展格式：
### awk [选项] 'BEGIN{} {} END{}' filename
- 在开始/结束时执行一遍
- 初始化变量：eg:BEGIN{count=0}
- for循环

* 获取uid>500的用户信息

![11.png](https://upload-images.jianshu.io/upload_images/14466577-99199e0e6c71cfe9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  
* 获取以j开头的用户信息，遍历输出

![22.png](https://upload-images.jianshu.io/upload_images/14466577-224fac0b52fab746.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	