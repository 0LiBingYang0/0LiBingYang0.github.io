1.Linux����ϵͳ�ṹ
�û�
Ӧ�ò�
Shell��    ����дShell����
�ں˲� 	   ΪӲ����������
Ӳ��

home�ļ����Ǵ����ͨ�û��ĵ��ļ���
d rwx    r-x      r-x  �ֳ����β鿴 d�����ļ���
  root  �û���    �û�

bin Ŀ¼�·ſ�ִ���ļ�
etc �ŵ��ǻ����ļ�
usr װ������ŵ�Ŀ¼
home ÿ����һ���û��ͻ���home�ļ������洴����Ӧ���ļ���
hostname �鿴������
hostname s �޸��û���Ϊsһ�����޸�������ָ�
su ����ͨ�û��л���root
exit ��root�л�����ͨ�û�

vi /etc/hostname �����޸�������
vi �༭�ļ� �����ļ��� i ���б༭  
�˳�ʱ esc + : + q(�˳�������)/q!(ǿ���˳�������)/wq(���沢�˳�)


ping���� ����������ͨ�� ��ʽ  ping+ip��˿ں�

ifconfig �鿴���л����ӿڵ���Ϣ
yum install net-tools /y   ��װ������ص�����  /y  ������ѡ�����Զ�ִ��y

service firewalld status �鿴����ǽ״̬
systemctl stop firewalld ��ʱ�رշ���ǽ
systemctl disable firewalld  ��ֹ������������ǽ

Linux�ı��� #��ͷ�Ĵ���ע��

Linux�����ͨ�������ʽ
������ [ѡ��] [����]
ѡ��:���ڵ�������ľ��幦��
��������������Ķ������ļ���Ŀ¼����

pwd:�鿴��ǰ����Ŀ¼��ȫ·��
cd:�л�����Ŀ¼  ��ʽ:cd [Ŀ¼λ��]
ls -R:�ݹ��ѯ
ls -a:�鿴�����ļ����������ļ�
ls -A:�鿴���������ļ���������ļ�

mkdir:�����ļ���
mkdir -p:ͬʱ��������ļ���

du:ͳ��Ŀ¼���ļ�ռ�ÿռ�����
du -s:ͳ��ÿ��������ռ�ռ��С
touch:�����ļ�
> :�ļ��� �����ļ���touch������ͬ
echo:���ļ�����д����


cp:�����ļ���Ŀ¼  ��ʽ  cp [ѡ��] Դ�ļ���Ŀ¼ Ŀ���ļ���Ŀ¼
-r:��������Ŀ¼��
-p:����Դ�ļ������Բ���
-f:ǿ�Ƹ���ͬ���ļ���Ŀ¼
-i:��Ҫ����ʱ������

rm:�Ƴ�  ���� rm -rf ֱ��ɾ��

mv:�ƶ� ԭ·���൱�ڸ����� 