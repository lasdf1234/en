# Range Download

If the OSS file is relatively large and only one part of the data is required, it can use range download to download data of designated scope. If the designated range is 0 - 1000, then it will return the data from 0 to 1,000 bytes, including the 1,000 th, 1001 bytes data in total, i.e., [0,1000]. If the designated range is 1000 -, the nit will return the data without the first 1000 bytes and download the rest part:
```
//您的AccessKey和SecretKey可以登录到对象存储的控制台，在【Access Key 管理】中查看。  
String accessKey =  "<yourAccessKeyId>";  
String secreteKey = "<yourSecretKey>";       
//endpoint以华北-北京为例，其它region请按实际情况填写  
String endPoint = "oss.cn-north-1.jcloudcs.com";  
String bucketName = "<yourBucketName>";  
String objectName = "<yourObjectName>";    
//ClientConfig当前为默认配置，用户可根据需要自行配置，如设置连接超时时间等  
ClientConfig config = new ClientConfig();  
  
//构造JingdongStorageService实例  
Credential credential = new Credential(accessKey, secreteKey);  
JingdongStorageService jss = new JingdongStorageService(credential,config); 
//配置endPoint  
jss.setEndpoint(endPoint);    
   
//创建objectService实例  
ObjectService objectService = jss.bucket(bucketName).object(objectName);  
//获取object，其中数据返回第0到第1000个字节的数据，包括第1000个，共1001字节的数据  
StorageObject storageObject = objectService.range(0, 1000).get();  
//获取object,其中返回数据跳过前1000个字节，其余部分下载到本地文件” localFile”中  
//StorageObject storageObject = objectService.range(1000).get();  
//将文件下载到本地文件中，如下示例是将指定的object下载到"localFile"中  
storageObject.toFile(new File("<localFile>"));    
 
//JingdongStorageService对象内部维护一组HTTP连接池，在不使用该对象之前需要调用其destroy方法关闭连接池，  
//请注意，一旦调用destroy方法，该对象就不能再次被使用，否则将会抛出异常。  
jss.destroy();
```
Notification: if 64KB data need to be read from OSS stream, please use the following method to read with multiple times until 64KB data have been read or the file ended:
```
byte[] buf = new byte[1024];  
InputStream in = storageObject.getInputStream();  
for (int n = 0; n != -1; ) {  
    n = in.read(buf, 0, buf.length);  
}  
in.close();
```
Not in the following form:
```
byte[] buf = new byte[64 * 1024];  
InputStream in = storageObject.getInputStream();  
in.read(buf, 0, buf.length);  
in.close();
```
The reason is stream reading may not read all the data by a single time, see InputStream.read for detailed description.
