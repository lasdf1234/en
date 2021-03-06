# Simple Upload

Stream upload and local file upload are called as simple upload. Stream upload use InputStream as the data source of Objects; file upload use local file as the data source of Objects.

## Stream Upload
```
//您的AccessKey和SecretKey可以登录到京东云存储的控制台，在【Access Key 管理】中查看。  
String accessKey =  "<yourAccessKeyId>";  
String secreteKey = "<yourSecretKey>";       
// endpoint以华北为例，其它region请按实际情况填写  
String endPoint = "s-bj.jcloud.com";  
File file = new File("<localFile>");   
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
//使用低冗余存储，则使用该句代码  
//objectService.getBuilder().getHeaders().put(JssHeaders.X_JSS_STORAGE_CLASS, StorageClass.ReducedRedundancy.toString());  
  
//获取输入流  
InputStream inputStream = new FileInputStream(file);  
//获取流长度  
long contentLength = file.length();  
//设置上传文件Content-type为"text/html"。函数返回上传数据的Etag,目前Etag的值为上传数据的MD5  
String md5 = objectService.entity(contentLength,inputStream).contentType("text/html").put();  
//若对上传文件进行加密，则使用该句代码  
//String md5 = objectService.entity(contentLength,inputStream).contentType("text/html").put(true);  
System.out.println(md5);  
  
//JingdongStorageService对象内部维护一组HTTP连接池，在不使用该对象之前需要调用其destroy方法关闭连接池，  
//请注意，一旦调用destroy方法，该对象就不能再次被使用，否则将会抛出异常。  
jss.destroy();
```

## Local File Upload
```
//您的AccessKey和SecretKey可以登录到京东云存储的控制台，在【Access Key 管理】中查看。  
String accessKey =  "<yourAccessKeyId>";  
String secreteKey = "<yourSecretKey>";       
// endpoint以华北为例，其它region请按实际情况填写  
String endPoint = "s-bj.jcloud.com";  
File file = new File("<localFile>");   
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
//使用低冗余存储，则使用该句代码  
//objectService.getBuilder().getHeaders().put(JssHeaders.X_JSS_STORAGE_CLASS, StorageClass.ReducedRedundancy.toString());  
 
//设置上传文件Content-type为"text/html"。函数返回上传数据的Etag,目前Etag的值为上传数据的MD5  
String md5 = objectService.entity(file).contentType("text/html").put();  
//若对上传文件进行加密，则使用该句代码  
//String md5 = objectService.entity(file).contentType("text/html").put(true);  
System.out.println(md5);  
 
//JingdongStorageService对象内部维护一组HTTP连接池，在不使用该对象之前需要调用其destroy方法关闭连接池，  
//请注意，一旦调用destroy方法，该对象就不能再次被使用，否则将会抛出异常。  
jss.destroy();
```
