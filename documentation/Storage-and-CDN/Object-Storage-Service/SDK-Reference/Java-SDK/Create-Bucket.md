# Create Bucket

You can use JingdongStorageService.createBucket to create Bucket. The following codes demonstrate the method of creating a Bucket:
```
// endpoint以华北为例，其它region请按实际情况填写  
String endpoint = "s-bj.jcloud.com";  
//您的AccessKey和SecretKey可以登录到京东云存储的控制台，在【Access Key 管理】中查看。  
String accessKey = "<yourAccessKey>";  
String SecretKey = "<yourSecretKey>";  
   
// 创建JingdongStorageService实例  
Credential credential = new Credential(accessKey, secreteKey);  
//默认配置文件。如用户需要个别配置，则自行配置。例:config.setMaxConnections(20);  
ClientConfig config = new ClientConfig();  
JingdongStorageService jss= new JingdongStorageService (credential, config);  
//设置Endpoint  
jss.setEndpoint(endpoint);  
       
// 创建bucket  
String bucketName = "<your-bucket-name>";  
jss.createBucket(bucketName);  
//关闭jss  
jss.destroy();
```
Notification:

* See naming specification in “Basic Concepts” for the naming specification of Bucket.

* The name of Bucket is global unique, so you need to ensure the names of the Buckets are not duplicated with that of others.

* The permissions of the bucket created by the above codes is private read/write (default permissions).
