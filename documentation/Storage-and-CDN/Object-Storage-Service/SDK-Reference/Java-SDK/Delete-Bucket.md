# Delete Bucket

You can use JingdongStorageService.deleteBucket to delete Bucket. The following codes demonstrate the method of deleting a Bucket:
```
// endpoint以华北-北京为例，其它region请按实际情况填写  
String endpoint = "oss.cn-north-1.jcloudcs.com";  
//您的AccessKey和SecretKey可以登录到对象存储的控制台，在【Access Key 管理】中查看。  
String accessKey = "<yourAccessKey>";  
String SecretKey = "<yourSecretKey>";  
      
// 创建JingdongStorageService实例  
Credential credential = new Credential(accessKey, secreteKey);  
//默认配置文件。如用户需要个别配置，则自行配置。例:config.setMaxConnections(20);  
ClientConfig config = new ClientConfig();  
JingdongStorageService jss= new JingdongStorageService (credential, config);  
//设置Endpoint  
jss.setEndpoint(endpoint);  
      
// 删除bucket  
jss.deleteBucket("<bucketName>");  
// 关闭jss  
jss.destroy();
```
Notification:

* If the Bucket is not empty (i.e., there are files or multipart upload fragments in the Bucket), then the Bucket cannot be deleted;

* All the files in the Bucket must be deleted before the Bucket can be successfully deleted.

* The Identity and Access Management permission must be deleted before the Bucket can be successfully deleted
