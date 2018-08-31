# Simple Download

OSS Java SDK provides rich file download interfaces, users can download files from OSS via the following methods:

* Stream download

* Download to the local file

* Range download

Stream download, download to the local file are called as simple download.

## Stream download

When download large files, you may want to perform stream processing (process a part of content for one time) instead of all contents.
```
//您的AccessKey和SecretKey可以登录到京东云存储的控制台，在【Access Key 管理】中查看。  
String accessKey =  "<yourAccessKeyId>";  
String secreteKey = "<yourSecretKey>";       
// endpoint以华北为例，其它region请按实际情况填写  
String endPoint = "s-bj.jcloud.com";  
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
 
//获取object对象  
StorageObject storageObject = objectService.get();  
// 读Object内容  
System.out.println("Object content:");  
BufferedReader reader = new BufferedReader(new InputStreamReader(storageObject.getInputStream()));  
String tempString = null;  
// 一次读入一行，直到读入null为文件结束  
while ((tempString = reader.readLine()) != null) {  
    System.out.println(tempString);  
}  

reader.close();       
storageObject.close();  
 /JingdongStorageService对象内部维护一组HTTP连接池，在不使用该对象之前需要调用其destroy方法关闭连接池，  
//请注意，一旦调用destroy方法，该对象就不能再次被使用，否则将会抛出异常。  
jss.destroy();
```
Notification:

* Acquired stream must be displayed as close, otherwise it will lead to resource disclosure.

* If 64KB data need to be read from OSS stream, please use the following method to read with multiple times until 64KB data have been read or the file ended:
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

## Download to the Local File

Download the contents of Object to the designated local file(s). If the designated local file do not exist, it will be created.
```
//您的AccessKey和SecretKey可以登录到京东云存储的控制台，在【Access Key 管理】中查看。  
String accessKey =  "<yourAccessKeyId>";  
String secreteKey = "<yourSecretKey>";       
// endpoint以华北为例，其它region请按实际情况填写  
String endPoint = "s-bj.jcloud.com";  
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

//获取object对象  
StorageObject storageObject = objectService.get();  
//将文件下载到本地文件中，如下示例是将指定的object下载到"localFile"中  
storageObject.toFile(new File("<localFile>"));  

 
//JingdongStorageService对象内部维护一组HTTP连接池，在不使用该对象之前需要调用其destroy方法关闭连接池，  
//请注意，一旦调用destroy方法，该对象就不能再次被使用，否则将会抛出异常。  
jss.destroy();
```
