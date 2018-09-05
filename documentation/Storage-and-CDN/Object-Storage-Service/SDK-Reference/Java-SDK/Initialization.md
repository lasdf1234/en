# Initialization

JingdongStorageService (JSS) is the core class of JD Cloud object storage service OSS, it provides a series of interfaces interacting with OSS for the callers, used for OSS resources such as manage, operate buckets and objects, etc. Use Java SDK to initiate OSS request, you need to use your AccessKey and SecretKey to initiate a JingdongStorageService instance and modify the default configuration items of ClientConfig according to the requirements.

## Determine Endpoint

Please read the part of “[basic concepts](http://www.jdcloud.com/help/detail/1177/isCateLog/1)-access domain name” to understand the concepts relevant to Endpoint.

## Configure key

A pair of valid Access Keys (including Access KeyId and Access KeySecretID) to perform signature verification for accessing JD Cloud OSS. They can be acquired through the following steps:

* [register JD Cloud accounts](https://uc.jdcloud.com/reg?returnUrl=http%3A%2F%2Fwww.jdcloud.com%2Findex)

* [Apply for AccessKey](https://uc.jdcloud.com/accesskey/index)

After acquiring the AccessKeyId and secretAccessKeyId, you can perform initialization as per the following steps.

## Create Jingdong Storage Service

Use domain name to create JingdongStorageService, with the relevant codes being as follows:
```
 //访问京东云的accessKey  
String accessKey = "<yourAccessKeyId>";  
String secreteKey = "<yoursecretKeyId>";    
//endpoint以华北-北京为例  
String endpoint = "oss.cn-north-1.jcloudcs.com";  
 
//创建JingdongStorageService实例  
JingdongStorageService jss=new JingdongStorageService(accessKey,secreteKey);
jss.setEndpoint(endpoint);  
  
//使用云存储  
  
//销毁JingdongStorageService实例  
jss.destroy();
```
Notification:

1. Your project may contain several or only one JingdongStorageService;

2. JingdongStorageService may be used concurrently;

3. JingdongStorageService.destroy cannot be used any more later.

## Configure JingdongStorageService

If you need to modify some default configurations of JingdongStorageService, please pass the ClientConfig instance when constructing JingdongStorageService. ClientConfig is a configuration class, which can be used to configure broker, connecting time-out, maximum connections and other parameters. The parameters can be set by ClientConfig are shown as in the following table:

|Parameters|Description|Methods|
|MaxConnections|Maximum HTTP connections allowing to open. Default is 1024|ClientConfiguration.setMaxConnections|
|SocketTimeout|The time-out period for transmitting data by socket layer (unit: millisecond). Default is 50000 millisecond|ClientConfiguration.setSocketTimeout|
|ConnectionTimeout|The time-out period for setting connection (unit: millisecond). Default is 50000 millisecond|ClientConfiguration.setConnectionTimeout|
|MaxErrorRetry|Maximum number of retries after request failure. Default is 3|ClientConfiguration.setMaxErrorRetry|

## Use ClientConfiguration to set JingdongStorageService

Parameter codes are shown as below:
```
//访问京东云的accessKey  
String accessKey =  "<yourAccessKeyId>";  
String secreteKey = "<yourSecretKey>";   
//endpoint以华北-北京为例  
String endpoint = "oss.cn-north-1.jcloudcs.com";  
 
//创建ClientConfig实例  
ClientConfig clientConfig=new ClientConfig();  
//设置最大连接数，默认为128  
clientConfig.setMaxConnections(300);  
//设置请求超时时间，默认是50s  
clientConfig.setSocketTimeout(15000);  
//设置失败请求重试次数，默认是3次  
clientConfig.setMaxErrorRetry(6);  

//创建JingdongStorageService实例  
JingdongStorageService jss=new JingdongStorageService(accessKey,secreteKey);
jss.setEndpoint(endpoint);  
 
//使用对象存储
  
//销毁JingdongStorageService实例  
jss.destroy();
```
