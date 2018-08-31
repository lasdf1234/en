# Use URL signature to grant access privilege

JD Cloud storage provides a kind of authentication method based on Query String, i.e., by perform Presigned action, generate a URL with authentication information for the Objects and send it to third party users to implement public access. When generating URL, you can designate URL expired time so as to restrict users from accessing with long time.

Generated URL accesses with the method of GET by default, thus, users can directly access relevant contents via a browser, the codes are as follows:
```
// endpoint以华北为例，其它region请按实际情况填写  
String endpoint = "s-bj.jcloud.com";  
//您的AccessKey和SecretKey可以登录到京东云存储的控制台，在【Access Key 管理】中查看。  
String accessKey = "<your accessKey>";  
String secretKey = "<your secretKey>";  
String bucketName = "<your bucketName>";  
String key = “<you objectKey>”;  
       
// 创建JingdongStorageService实例  
Credential credential = new Credential(accessKey, secreteKey);  
//默认配置文件。如用户需要个别配置，则自行配置。例:config.setMaxConnections(20);  
ClientConfig config = new ClientConfig();  
JingdongStorageService jss= new JingdongStorageService (credential, config);  
//设置Endpoint  
jss.setEndpoint(endpoint);  
      
//生成URL，可以通过浏览器直接访问，过期时间是1小时  
URI signatureUrl = jss.bucket(bucketName).object(key)
                   .generatePresignedUrl(3600);  
// 打印URL  
System.out.println(signatureUrl.toString());  
// 关闭jss  
jss.destroy();
```
