# shell

## shell����

### shell���
- shell����	
	- Shell��һ������ǿ��ı�����ԣ��ױ�д���׵��ԣ�����Խ�ǿ
	- Shell�ǽ���ִ�еĽű�����shell�п���ֱ�ӵ���Linuxϵͳ����
- shell����
	- Bourne Shell����1979����Unix������Bourne Shell��BourneShell�����ļ���Ϊ sh
	- C Shell��C Shell��Ҫ��BSD���Unixϵͳ��ʹ��
- ע��
	- ���������﷨�������ݣ�Bourne ������Ҫ����sh��ksh��bash��psh��zsh��  C������Ҫ������csh��tcsh
	- һ��ϵͳ���Դ��ڶ��shell������ͨ��cat /etc/shells����鿴ϵͳ�а�װ��shell����ͬ��shell����֧�ֵ������﷨�ǲ���ͬ��
- shell������ʽ
	- ����д����ͨ�ı��ļ��У�ͨ����.sh��β,����:[root@master ~]# vim helloworld.sh
	- д�걣���˳�
	- �ű��ĵ�һ���ǹ̶���Ҫ��,��������һ��shell��������ִ�����ǵ�����ű�����
- shell��ִ�з�ʽ
	- sh��ʽ ����:sh helloworld.sh �˷�ʽ��ֱ��ָ����ϵͳĬ�ϵ�bash shell����ִ�е�
	- source��ʽ ����: . helloworld.sh
		- source����Ҳ��Ϊ���������Ҳ����һ������ţ�.��,��bash���ڲ�����
		- ʹShell����ָ����Shell�����ļ�������ִ���ļ��е��������
		- source����ͨ����������ִ�и��޸ĵĳ�ʼ���ļ���ʹ֮������Ч��������ע�������µ�¼
	- ֱ��ִ�иýű�
	
### shell���
- ����
	- Linux�����У�Shell�����ǳ��õ�������ͳ��򣬶����Ǹ߼�������ԡ��û�����ͨ����дShell��������ɴ���������Զ���
	- Shell������ԣ����б������ؼ����Լ����ֿ�����䣬����if��case��while��for����䣬֧�ֺ���ģ�飬���Լ����﷨�ṹ��
- shell�����﷨
	- ϵͳ����:ͨ��set����鿴ϵͳ����,���õ�ϵͳ������ $PWD $SHELL #USER $HOME
	- �Զ������
		- ˫���ţ�����ͨ��$�������������ֵ
		- �����ţ���ֹ������������ֵ��$��Ϊ��ͨ�ַ�
		- ��Ʋ�ţ������滻����ȡ����ִ�к����������Ҳ����$(����)
	- �Ӽ����������ݱ�Ϊ��ֵ:read  [-p  "��ʾ��Ϣ"]  ������
	- read����
		* read -p(��ʾ���)-n(�ַ�����) -t(�ȴ�ʱ��)?
		* read -p "please input your name: " NAME
		* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-300286980bacd687.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- ������ķ���ֵ��������
		* A=`ls -la` �����ţ����������������ѽ�����ظ�����A
		* A=$(ls -la) �ȼ��ڷ�����
	- ȡ������
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-8c2423757062b978.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- �������
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-7506afd3a43fc95f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- �����
	- ��������
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-c5d7141000a2df7d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- ���������
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-7a541b264943ea1e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- ��������
	- test����
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-a0d4e8fdceba2b92.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- �ļ�����
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-28d12b1bf0fdb105.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-0dd6e22d2260ed56.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* eg(����1��ʾ����������,����0��ʾ��������) echo $? �����һ��ָ��������ֵ
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-5294ee208f9f91ef.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- �ļ�Ȩ�޲���:��ʽ [ ������ �ļ���Ŀ¼ ]
	* ���õĲ��Է�����
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-5fad6ec61e100b7f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* eg:
	![image.png](https://upload-images.jianshu.io/upload_images/14498135-1bb655255e9a2df7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- ��ֵ�Ƚ�
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-816d5443fb7d855f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* eg: 
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-1edbff1f821849d8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- �ַ����Ƚ�
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-3e08a0a40bdf1f24.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-97d01f4f4c15bbfb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- ��������
	- if���ṹ
	* ����֧�ṹ
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-5e1d457be126ce1d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* ˫��֧�ṹ
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-6c78f6badeba1391.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* ���֧�ṹ
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-48de0ab91e666ce8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-00eb1b69409ef621.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* eg:�жϷ�����Χ,�ֳ����㼸�����ϸ������ɼ���
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-e43b5608e3605f88.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- case���ṹ
	* �﷨
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-7b80fadf5309e878.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-d2c21c7b13b26116.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* eg:��ʾ�û�����һ���ַ�,�жϸ��ַ�����ĸ���ֻ��������ַ�
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-9aa1a23d165cbd29.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- ѭ�����
	- for���ṹ
	* �﷨
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-cc22a45a58d4413f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-071278bd0b0abed5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240) 
	eg: ��������û�:�û��������users.txt�ļ���,ÿ��һ��
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-31162eea4a82b597.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- for....do.....done ����ֵ����
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-8bd2bce8ce33911e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)	
	-while���Ľṹ
	* �﷨
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-491e13643ab96a3d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* eg1:��������û�
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-9db3995946e30dc6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* eg2:����1��100����֮��
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-05b8472878c4d365.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* eg3:��ӡ�žų˷���
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-c9eed7a007fbb34e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- �ۺϰ���
	- ����Ʒ�۸���Ϸ
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-12923d3226dc8059.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-dbf1fd961d49a736.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- shell�Զ��庯��
	* 1.�����ڵ��ú����ط�֮ǰ����������,shell�ű����������е�,��������������һ����Ԥ����
	* 2.����������ֻ��ͨ��$?ϵͳ�������,������ʾ��:return����,�������,�������һ���������н��,��Ϊ����ֵ.return�����ֵn(0-255)
	* �﷨
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-68831612dca76e3b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### Bash
	- ���
	* Bash�� Bourne Again SHell����GNU�ƻ���һ���������Unix�ϵ�Bourne Shell��ȫ���ݣ�������ǿ�汾��֧�����������롢������ʷ����ݼ�����������ض��򡢹ܵ��������ȹ��ܡ�
#### bash����
	- history ��Bash������historyָ����Բ�ѯ�û��Ĺ�������
	* -c:�����ʷ����
	* -w:�ѻ������ʷ����д����ʷ������ļ� �����λ��Ϊ ~/.bash_history
	- Tab���� ��ȫ����,��������[Tab] ���������ǰ����ĸ��ͷ����������
	- alias
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-114e2df712098ba3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- �ض������
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-657064f07fee4518.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- �ܵ���
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-277e1fe663ef2612.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- ͨ���
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-80af32f5025cda21.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- �����������
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-5edc7cb6f6ccc826.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- �����ȼ�
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-7ef9c6aecf16b03d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- ��ȡ����(cut)
	* �﷨: cut <ѡ��> �ļ�
	* ����ѡ��
	* -d:ָ���ָ���
	* -f:���� -d�ķָ��ַ���һ����Ϣ�ָ��Ϊ����,��-fȡ���ڼ��ε���˼
	* -c:ָ�������ַ���Ӧ����
	* ![image.png](https://upload-images.jianshu.io/upload_images/14498135-85463d693e29c610.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

	
	
	
	
	