# Manage File

In OSS, users can manage files (Objects) in the storage space (Bucket) through a series of interfaces, such as ListObjects, DeleteObject, MoveOb, etc. The name of Object is also called as key or object key.

##List files in the storage space

Acquire object list under the bucket, perform dictionary sorting for the returned results based on key. The previous 1000 data will be returned by default. If there are more data, objectList hasNext() returns true, otherwise returns false.

**List all objects**

List all Objects under Bucket:
```
//您的AccessKey和SecretKey可以登录到京东云存储的控制台，在【Access Key 管理】中查看。  
String accessKey =  "<yourAccessKeyId>";  
String secreteKey = "<yourSecretKey>";       
// endpoint以华北为例，其它region请按实际情况填写  
String endPoint = "s-bj.jcloud.com";  
String bucketName = "<yourBucketName>";  
  
//ClientConfig当前为默认配置，用户可根据需要自行配置，如设置连接超时时间等  
ClientConfig config = new ClientConfig();   
  
//构造JingdongStorageService实例  
Credential credential = new Credential(accessKey, secreteKey);  
JingdongStorageService jss = new JingdongStorageService(credential,config); 
//配置endPoint  
jss.setEndpoint(endPoint);  
          
//创建BucketService实例  
BucketService bucketService = jss.bucket(bucketName);  
//列出bucket下满足条件的文件和文件夹  
ObjectListing objectList = bucketService.listObject();  
//列出指定条件下的object名称  
for (ObjectSummary objectSummary : objectList.getObjectSummaries()) {  
    System.out.println("objectName : "+objectSummary.getKey());  
}  

//JingdongStorageService对象内部维护一组HTTP连接池，在不使用该对象之前需要调用其destroy方法关闭连接池，  
//请注意，一旦调用destroy方法，该对象就不能再次被使用，否则将会抛出异常。  
jss.destroy();
```

**Designate maximum return number**
```
//创建BucketService实例  
BucketService bucketService = jss.bucket(bucketName);  
//指定返回最大条数为10  
bucketService.maxKeys(10);  
//列出bucket下满足条件的文件和文件夹  
ObjectListing objectList = bucketService.listObject();  
//列出指定条件下的object名称  
for (ObjectSummary objectSummary : objectList.getObjectSummaries()) {  
     System.out.println("objectName : "+objectSummary.getKey());  
}
```

**Return Objects with designated prefix(es)**

```
//创建BucketService实例  
BucketService bucketService = jss.bucket(bucketName);  
//指定返回前缀  
bucketService.prefix("file");  
//列出bucket下满足条件的文件和文件夹  
ObjectListing objectList = bucketService.listObject();  
//列出指定条件下的object名称  
for (ObjectSummary objectSummary : objectList.getObjectSummaries()) {  
     System.out.println("objectName : "+objectSummary.getKey());  
}
```

**Return the objects after the designated Object**

```
//创建BucketService实例  
BucketService bucketService = jss.bucket(bucketName);  
//返回"file"后以字典序排序的Object信息，结果中不包含"file"  
bucketService.marker("file");  
//列出bucket下满足条件的文件和文件夹  
ObjectListing objectList = bucketService.listObject();  
//列出指定条件下的object名称  
for (ObjectSummary objectSummary : objectList.getObjectSummaries()) {  
     System.out.println("objectName : "+objectSummary.getKey());  
}
```

**Acquire all Objects by paging**

```
String marker = null;  
ObjectListing objectList = null;  
do {  
     System.out.println(".................page....................");  
      //创建BucketService实例  
     BucketService bucketService = jss.bucket(bucketName);  
     //返回marker后以字典序排序的Object信息，结果中不包含marker  
    bucketService.marker(marker);  
    //指定返回最大条数为5  
    bucketService.maxKeys(5);  
    //列出bucket下满足条件的文件和文件夹  
    objectList = bucketService.listObject();  
    //列出指定条件下的object名称  
    List<ObjectSummary> objectSummaries = objectList.getObjectSummaries();  
    for (ObjectSummary objectSummary : objectSummaries) {  
         System.out.println("objectName : "+objectSummary.getKey());  
    }  
    marker = objectSummaries.get(objectSummaries.size()-1).getKey();  
} while (objectList.isHasNext());
```

**Acquire all objects after the specific Object by paging**

Acquire all objects after the specific Object by paging, with the number of Objects being equal to the value of maxKeys per page.

```
//分页获取"file"后以字典序排序的Object信息，结果中不包含"file"  
String marker = "file";  
ObjectListing objectList = null;  
do {  
    System.out.println(".................page....................");  
    //创建BucketService实例  
    BucketService bucketService = jss.bucket(bucketName);  
    //返回marker后以字典序排序的Object信息，结果中不包含marker  
    bucketService.marker(marker);  
    //指定返回最大条数为5  
    bucketService.maxKeys(5);  
    //列出bucket下满足条件的文件和文件夹  
    objectList = bucketService.listObject();  
    //列出指定条件下的object名称  
    List<ObjectSummary> objectSummaries = objectList.getObjectSummaries();  
    for (ObjectSummary objectSummary : objectSummaries) {  
        System.out.println("objectName : "+objectSummary.getKey());  
    }  
    marker = objectSummaries.get(objectSummaries.size()-1).getKey();  
} while (objectList.isHasNext());
```

** Acquire all Objects with designated prefix(es)**

Acquire all Objects with designated prefix(es) by paging, with the number of Objects being equal to the value of maxKeys per page.

```
String marker = null;  
ObjectListing objectList = null;  
do {  
    System.out.println(".................page....................");  
    //创建BucketService实例  
    BucketService bucketService = jss.bucket(bucketName);  
    //指定返回前缀的object  
    bucketService.prefix("file");  
    //返回marker后以字典序排序的Object信息，结果中不包含marker  
    bucketService.marker(marker);  
    //指定返回最大条数为5  
    bucketService.maxKeys(5);  
    //列出bucket下满足条件的文件和文件夹  
    objectList = bucketService.listObject();  
    //列出指定条件下的object名称  
    List<ObjectSummary> objectSummaries = objectList.getObjectSummaries();  
    for (ObjectSummary objectSummary : objectSummaries) {  
        System.out.println("objectName : "+objectSummary.getKey());  
    }  
    marker = objectSummaries.get(objectSummaries.size()-1).getKey();  
} while (objectList.isHasNext());
```

## Simulate folder function

You can simulate the folder function by matching the parameters of Delimiter and Prefix. The combinative effects of Delimiter and Prefix are as follows:

If Prefix is set as a folder name, then the files (i.e., all files and subfolders (directory) being recursive under the folder) with the prefix of the name will be listed.

If Delimiter is set as “/”, the return value only list the files and subfolders (directory) under the folder. The sub-file names (directory) under the folder return the part at CommonPrefixes while recursive files and folders under the subfolder will not be displayed.

Notification: if there 4 files in the Bucket: oss.jpg, jingdong/file, jingdong/dir/file1, jingdong/dir/file2, “/” is used as the delimiter of the folders. The following example demonstrates how to simulate folder function.

**List all files in the storage space**

When we need to acquire all files under the storage space, we use the following codes:

```
//创建BucketService实例  
BucketService bucketService = jss.bucket(bucketName);  
//列出bucket下满足条件的文件和文件夹  
ObjectListing objectList = bucketService.listObject();  
//列出指定条件下的object名称  
System.out.println("objectName : ");  
for (ObjectSummary objectSummary : objectList.getObjectSummaries()) {  
    System.out.println(objectSummary.getKey());  
}  
//列出指定条件下的文件夹  
System.out.println("\nCommonPrefixes : ");  
for (String commonPrefixes : objectList.getCommonPrefixes()) {  
    System.out.println(commonPrefixes);  
}
```
Output:

```
objectName :   
jingdong/dir/file1  
jingdong/dir/file2  
jingdong/file  
oss.jpg  
  
CommonPrefixes :
```

**List all files under the directory by recursion**

We can acquire all files under a directory (jingdong/) by setting Prefix parameter:

```
//创建BucketService实例  
BucketService bucketService = jss.bucket(bucketName);  
//获取"jingdong/"下所有的文件  
bucketService.prefix("jingdong/");  
//列出bucket下满足条件的文件和文件夹  
ObjectListing objectList = bucketService.listObject();  
//列出指定条件下的object名称  
System.out.println("objectName : ");  
for (ObjectSummary objectSummary : objectList.getObjectSummaries()) {  
    System.out.println(objectSummary.getKey());  
}  
//列出指定条件下的文件夹  
System.out.println("\nCommonPrefixes : ");  
for (String commonPrefixes : objectList.getCommonPrefixes()) {  
    System.out.println(commonPrefixes);  
}
```

Output:

```
objectName :   
jingdong/dir/file1  
jingdong/dir/file2  
jingdong/file  
  
CommonPrefixes :
```

**List files and sub-directories under the directory**

In the case of combining Prefix and Delimiter, files and sub-directories under the directory (jingdong/) can be listed. It shall be noted that it only takes effect when HasCommonPrefix is true:

```
//创建BucketService实例  
BucketService bucketService = jss.bucket(bucketName);  
//列出"jingdong/"下的文件和子目录,需要注意的是hasCommonPrefix必须为true才生效
bucketService.prefix("jingdong/").delimiter("/").hasCommonPrefix(true);  
//列出bucket下满足条件的文件和文件夹  
ObjectListing objectList = bucketService.listObject();  
//列出指定条件下的object名称  
System.out.println("objectName : ");  
for (ObjectSummary objectSummary : objectList.getObjectSummaries()) {  
     System.out.println(objectSummary.getKey());  
}  
//列出指定条件下的文件夹  
System.out.println("\nCommonPrefixes : ");  
for (String commonPrefixes : objectList.getCommonPrefixes()) {  
    System.out.println(commonPrefixes);  
}
```

Output:

```
objectName :   
jingdong/file  
 
CommonPrefixes :   
jingdong/dir
```

Notification:

* In the returned results, the list of ObjectSummaries lists the files under the directory of jingdong.

* And the list of CommonPrefixs lists all subfolders under the directory of jingdong. It can be seen that two files of jingdong/dir/file1 and jingdong/dir/file2 are not listed for they belong to dir directory under jingdong folder.
