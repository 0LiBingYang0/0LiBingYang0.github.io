
## hdfs ��������(1)

#### ����

* hdfs��Ⱥ��NameNode��Secondary NameNode����DataNode
  * NameNode����Ԫ���ݣ�DataNode�������ݿ�
* �������ƣ�dataNode �ᶨ�ڻ㱨���������nameNode���𱣳�DataNode�������ļ���������;
            ��dataNode�������⣬nameNode���blockת�Ƶ���һ����
* �ͻ��˿�����hdfs�ڲ����ƣ�ͨ��namenode�������

#### д��������

*  �ͻ��˽����ݽ���block�ֿ�
*  ȷ��ͨ�ţ����ͨ�ŵ�dataNode
*  ����ͨ��ͨ�����������block����Ӧ��dataNode
*  �ɽ���block��dataNode����������dataNode���ݸ���

  ![image.png](https://upload-images.jianshu.io/upload_images/14466577-3f5593035b3e5898.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
   
  ![image.png](https://upload-images.jianshu.io/upload_images/14466577-0c19e90d2d3955dc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


#### ����������   

* �ͻ��˽�·������nameNode,��nameNode��ȡblockԭ��Ϣ����Ҫ��block���λ�ã�����
* �ͻ���ͨ��������Ϣ���Ҷ�ӦdataNode����ȡ�ļ�block
* �ڿͻ��˱��ؽ������ݺϲ�����������ļ�

  ![image.png](https://upload-images.jianshu.io/upload_images/14466577-13e524724582ce14.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  
  ![image.png](https://upload-images.jianshu.io/upload_images/14466577-9af53e8601bbe8f2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### nameNode��������

* ְ�𣺸���ͻ���������Ӧ��Ԫ���ݹ���
* �洢��ʽ
  * Ԫ����meta data���ڴ��У��ڴ���namenode��
  * �����ļ�fsimage:namenode����Ŀ¼��
  * ���ݲ�����־�ļ�edits:�����ν�metadata��fsimage
  
#### Ԫ���ݵ�checkpoint

* һ��ʱ�䣬Secondary NameNode��nameNode�ϻ��۵�����edits��һ�����µ�fsimage���ص����أ�
  �����ص��ڴ����merge��������̳�Ϊcheckpoint��
  
  ![image.png](https://upload-images.jianshu.io/upload_images/14466577-ab4aa48f2f4d9a8b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
   
  ![image.png](https://upload-images.jianshu.io/upload_images/14466577-e7c2e77aa2c81251.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 
#### namenode·��/current/Ŀ¼���ļ�
* VERSION��java�����ļ���
* seen_txid��edits�ļ��������
* format��ͬʱҲ������fsimage��edits�ļ��������Ӧ��md5У���ļ���

#### Secondary nameNode
* fsimage ������NameNode����ʱ�������ļ�ϵͳ�Ŀ��գ�
* edit logs ������NameNode�����󣬶��ļ�ϵͳ�ĸĶ����У�
* Secondary NameNode ���ǰ�����������������ݷŵ��ڴ��У��ֽм��ڵ㣬����nameNode�ı��ݣ�
* nameNode��Secondary nameNode�����ڵ㣩�����洢Ŀ¼��ȫ��ͬ��
* ��namenode�����˳���Ҫ���»ָ�ʱ�����Դ�secondary namenode�Ĺ���Ŀ¼�н�fsimage������namenode�Ĺ���Ŀ¼���Իָ�namenode��Ԫ����
* [���](https://www.xuebuyuan.com/3196294.html)








