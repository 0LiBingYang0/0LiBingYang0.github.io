#sed & awk

##sed

��ʽ:sed ѡ�� '����' filename
ѡ��
-n ����ģʽ,�� sed -n 'p' aaa.txt ��������ļ�������
-e ֱ����ָ����ģʽ�Ͻ���sed�����༭
-f ֱ�ӽ�sed�� ����д��һ��������,-f filename �����ִ�� filename�ڵ�sed����
-r sed�Ķ���֧�ֵ��������������ʾ�����﷨.(Ĭ�ϵ��ǻ��������ʾ���﷨)
-i ֱ���޸Ķ�ȡ�ĵ�������,����������Ļ���
����
- a ����,a�ĺ�����Խ��ַ���,��Щ�ַ��������µ�һ�г���(Ŀǰ����һ��) 
	- �ڵ�һ���������:sed '1a asd' 123.txt(1)
	- ![1.png](https://upload-images.jianshu.io/upload_images/14498135-8321ef9f5dc401ba.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- ��ÿһ����������:sed 'a asd' 123.txt(2)
	- ![2.png](https://upload-images.jianshu.io/upload_images/14498135-4ef71c082ef2eb88.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	- ��1-5���������:sed '1,5a asd' 123.txt(3)
	- sed ![3.png](https://upload-images.jianshu.io/upload_images/14498135-dd588882e20ed7d3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- i ����,i�ĺ�����Խ��ַ���,����Щ�ַ��������µ�һ�г���(��ǰ�е���һ��)������÷���-a��ͬ
	- eg:�ڵ�һ���������: sed '1i asd' 123.txt(4)
	- ![4.png](https://upload-images.jianshu.io/upload_images/14498135-f01d0547500120c7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- c ȡ��,c�ĺ�����Խ��ַ���,��Щ�ַ�������ȡ�����м������
	- �滻�����е�����:sed 'c asd' 123.txt
	- ![image.png](https://upload-images.jianshu.io/upload_images/14498135-8666735bdd315c2d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	d ɾ��
	p ��� 1p ��ӡ��һ�� 1,5�Ĵ�ӡ1-5��  5,p �ӵ����д�ӡ����β
	s �滻�������������в���
	w д�� sed 'w Ҫ��д����ļ�(Ŀ���ļ�)' ��ȡ���ݵ��ļ�(Դ�ļ�)ֻҪ��w���ļ�
	�н���д��ͻὫĿ���ļ�֮ǰ������ȫ���ɵ�
	r��ȡ sed '2r Ҫ��ȡ���ļ�' �������ݵ��ļ�(Ŀ���ļ�)
�߼�����
	| �ܵ���,ʹ�ø÷��������������
	{} ������sedִ�ж������,ֻ�Ƕ���֮��Ҫ��";"�ֺŸ���
	&�滻 
	&�൱��ռλ�������� �������� s/��ѯ����/��ѯ��������
	������s/��ѯ����/Ҫ�滻�ɵ������н���ʹ��,ʵ��׷�ӵ�Ч��
	\uת�ɴ�д����������ǵ�&��ʵ�ֽ�ƥ������ת���ɴ�д�Ĳ���
	
	��passwd�ļ��л�ȡusername.userid,groupid����չʾ()���鹦��
	sed 's/\([a-z0-9_-]\+\):x:\([0-9]\+\):\([0-9]\+\):.*$/user: \1/' passwd
	��ô��sed�л�ȡ����õ���������?
	���ȷ��������Ǵ�1��ʼ�Ĳ����ǰ��մ����ҵ�˳���ŵ�
	Ҫ��ȡʹ��\�������������л�ȡ,����\1���Ǹ�ռλ��
	
awk �ж�ȡ
	������ʽ: awk optionsѡ�� 'command' file
	NR �к�
	NF ����
	$1,$n
	-F ���÷ָ��� Ĭ���������ʹ�� " "�ո������еķָ�
	
	awk����չ��ʽ
	awk optionsѡ�� 'BEGIN{} command END{}' file
	