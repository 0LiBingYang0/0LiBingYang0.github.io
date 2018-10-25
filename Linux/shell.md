# shell

## shell基础

### shell简介
- shell概述	
	- Shell是一个功能强大的编程语言，易编写，易调试，灵活性较强
	- Shell是解释执行的脚本，在shell中可以直接调用Linux系统命令
- shell分类
	- Bourne Shell：从1979年起，Unix就是用Bourne Shell，BourneShell的主文件名为 sh
	- C Shell：C Shell主要在BSD版的Unix系统中使用
- 注意
	- 以上两种语法互不兼容，Bourne 家族主要包括sh，ksh，bash，psh，zsh；  C家族主要包括：csh，tcsh
	- 一个系统可以存在多个shell，可以通过cat /etc/shells命令查看系统中安装的shell，不同的shell可能支持的命令语法是不相同的
- shell基本格式
	- 代码写在普通文本文件中，通常以.sh结尾,例如:[root@master ~]# vim helloworld.sh
	- 写完保存退出
	- 脚本的第一行是固定需要的,表明用哪一种shell解析器来执行我们的这个脚本程序
- shell的执行方式
	- sh方式 例如:sh helloworld.sh 此方式是直接指定用系统默认的bash shell解释执行的
	- source方式 例如: . helloworld.sh
		- source命令也称为“点命令”，也就是一个点符号（.）,是bash的内部命令
		- 使Shell读入指定的Shell程序文件并依次执行文件中的所有语句
		- source命令通常用于重新执行刚修改的初始化文件，使之立即生效，而不必注销并重新登录
	- 直接执行该脚本
	
### shell编程
- 概述
	- Linux环境中，Shell不仅是常用的命令解释程序，而且是高级编程语言。用户可以通过编写Shell程序来完成大量任务的自动化
	- Shell编程语言，它有变量、关键字以及各种控制语句，比如if、case、while、for等语句，支持函数模块，有自己的语法结构。
- shell基本语法
	- 系统变量:通过set命令查看系统变量,常用的系统变量有 $PWD $SHELL #USER $HOME
	- 自定义变量
		- 双引号：允许通过$符号引用其变量值
		- 单引号：禁止引用其他变量值，$视为普通字符
		- 反撇号：命令替换，提取命令执行后的输出结果，也可用$(命令)
	- 从键盘输入内容变为赋值:read  [-p  "提示信息"]  变量名
	- read命令
		* read -p(提示语句)-n(字符个数) -t(等待时间)?
		* read -p "please input your name: " NAME
		* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-300286980bacd687.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 将命令的返回值赋给变量
		* A=`ls -la` 反引号，运行里面的命令，并把结果返回给变量A
		* A=$(ls -la) 等价于反引号
	- 取消变量
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-8c2423757062b978.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 特殊变量
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-7506afd3a43fc95f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 运算符
	- 算数运算
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-c5d7141000a2df7d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 常用运算符
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-7a541b264943ea1e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 条件测试
	- test命令
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-a0d4e8fdceba2b92.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 文件测试
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-28d12b1bf0fdb105.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-0dd6e22d2260ed56.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* eg(返回1表示条件不成立,返回0表示条件成立) echo $? 输出上一条指令结果返回值
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-5294ee208f9f91ef.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 文件权限测试:格式 [ 操作符 文件或目录 ]
	* 常用的测试符操作
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-5fad6ec61e100b7f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* eg:
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-1bb655255e9a2df7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 数值比较
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-816d5443fb7d855f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* eg: 
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-1edbff1f821849d8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 字符串比较
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-3e08a0a40bdf1f24.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-97d01f4f4c15bbfb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 控制流程
	- if语句结构
	* 单分支结构
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-5e1d457be126ce1d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* 双分支结构
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-6c78f6badeba1391.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* 多分支结构
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-48de0ab91e666ce8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-00eb1b69409ef621.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* eg:判断分数范围,分出优秀几个不合格三个成绩档
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-e43b5608e3605f88.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- case语句结构
	* 语法
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-7b80fadf5309e878.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-d2c21c7b13b26116.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* eg:提示用户输入一个字符,判断该字符是字母数字或者其他字符
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-9aa1a23d165cbd29.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 循环语句
	- for语句结构
	* 语法
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-cc22a45a58d4413f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-071278bd0b0abed5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240) 
	eg: 批量添加用户:用户名存放在users.txt文件中,每行一个
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-31162eea4a82b597.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- for....do.....done 的数值处理
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-8bd2bce8ce33911e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)	
	-while语句的结构
	* 语法
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-491e13643ab96a3d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* eg1:批量添加用户
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-9db3995946e30dc6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* eg2:计算1到100数字之和
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-05b8472878c4d365.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* eg3:打印九九乘法表
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-c9eed7a007fbb34e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 综合案例
	- 猜商品价格游戏
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-12923d3226dc8059.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-dbf1fd961d49a736.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- shell自定义函数
	* 1.必须在调用函数地方之前先声明函数,shell脚本是逐行运行的,不会像其他语言一样先预编译
	* 2.函数返回至只能通过$?系统变量获得,可以显示加:return返回,如果不加,蒋怡最后一条命令运行结果,作为返回值.return后跟数值n(0-255)
	* 语法
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-68831612dca76e3b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### Bash
	- 简介
	* Bash（ Bourne Again SHell）是GNU计划的一个组件，与Unix上的Bourne Shell完全兼容，是其增强版本；支持命令行输入、操作历史、快捷键、输入输出重定向、管道、变量等功能。
#### bash命令
	- history 在Bash中输入history指令可以查询用户的过往操作
	* -c:清除历史命令
	* -w:把缓存的历史命令写入历史命令保存文件 保存的位置为 ~/.bash_history
	- Tab按键 补全命令,连续两下[Tab] 可以输出以前面字母开头的所有命令
	- alias
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-114e2df712098ba3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 重定向操作
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-657064f07fee4518.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 管道符
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-277e1fe663ef2612.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 通配符
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-80af32f5025cda21.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 其他特殊符号
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-5edc7cb6f6ccc826.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 常用热键
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-7ef9c6aecf16b03d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- 截取命令(cut)
	* 语法: cut <选项> 文件
	* 常用选项
	* -d:指定分隔符
	* -f:依据 -d的分隔字符将一段信息分割成为数段,用-f取出第几段的意思
	* -c:指定几个字符对应的列
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-85463d693e29c610.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

	
	
	
	
	