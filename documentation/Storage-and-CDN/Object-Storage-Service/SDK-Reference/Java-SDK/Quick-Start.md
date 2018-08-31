# Quick Start

Please confirm the OSS basic concepts that you are already familiar with, such as Bucket, Object, Endpoint, AccessKeyId , AccessKeySecret, etc.

In this section, you will see how to quickly use Java SDK to complete normal actions, such as create storage space, upload files, download files, etc.

##Initiate JingdongStorageService

Before sending any a HTTP request to the cloud storage, a JingdongStorageService instance must be created first:
```
//访问京东云的accessKey  
String accessKey = "<yourAccessKeyId>";  
String secreteKey = "<yoursecretKeyId>";    
//endpoint以华北为例  
String endpoint = "s-bj.jcloud.com";  
 
//创建JingdongStorageService实例  
JingdongStorageService jss= new JingdongStorageService(accessKey,secreteKey);  
jss.setEndpoint(endpoint);  
 
//使用云存储  
  
//销毁JingdongStorageService实例  
jss.destroy();
```
Notification: see “Initialization” for more initialization contents of OSSClient.

## Create Bucket

Storage space (Bucket) is OSS global naming space, (being equivalent to the container of data), which can store several files (Objects). The following codes demonstrate how to create a Bucket:
```
// 创建bucket  
String bucketName = "<your-bucket-name>";  
jss.createBucket(bucketName);
```
Notification:

See the naming specification in “Basic Concepts” for that of the Bucket.

See “Manage Bucket” for more information of creating Bucket.

## Upload Object

The following codes demonstrate how to upload files (objects) to OSS:
```
File file = new File("D:/test");
String bucketName =  "<your-bucket-name>";
String objectName =  "<your-object-name>";
ObjectService objectService = jss.bucket(bucketName).object(objectName);
//获取输入流  
InputStream inputStream = new FileInputStream(file);  
//获取流长度  
long contentLength = file.length();  
//设置上传文件Content-type为"text/html"。函数返回上传数据的Etag  
String md5 = objectService.entity(contentLength,inputStream).contentType("text/html").put();
```
Notification:

Java SDK upload Object to OSS via InputStream.

See “Upload File” for more information of uploading Object.

## Download Object

The following codes demonstrate how to acquire the text contents of Object:
```
String bucketName =  "<your-bucket-name>";
String objectName =  "<your-object-name>";

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
```
Notification: see “Download File” for more information of downloading Object.

## List Object

When a series of upload Object actions have been completed, it may need to view which Objects are contained under the Bucket. The following codes demonstrate how to list the Objects under the Bucket:
```
//创建BucketService实例  
BucketService bucketService = jss.bucket(bucketName);  
//列出bucket下满足条件的文件和文件夹  
ObjectListing objectList = bucketService.listObject();  
//列出指定条件下的object名称  
for (ObjectSummary objectSummary : objectList.getObjectSummaries()) {  
     System.out.println("objectName : "+objectSummary.getKey());  
 }
```

## Delete Object

The following code demonstrates how to delete the designated Objects:
```
String bucketName =  "<your-bucket-name>";
String objectName =  "<your-object-name>";
 
//创建objectService实例    
ObjectService objectService = jss.bucket(bucketName).object(objectName);    
//删除object    
ObjectService.delete();
```
