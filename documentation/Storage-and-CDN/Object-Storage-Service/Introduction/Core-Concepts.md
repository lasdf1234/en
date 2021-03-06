# Core concept

|English|Chinese|Description|
| - | - | - |
|Bucket|Storage space|Bucket is the fundamental organization unit of data in object storage service and all data must be a Bucket. The name of Bucket is globally unique. If you create a Bucket of a certain name, then other users cannot create a Bucket with the same name|
|Object|Object or file|Object is the fundamental entity in JD Object Storage Service. In this help documentation, Object, Object and File represent the same meaning which is composed of Key, Data and Metadata|
|Endpoint|OSS access domain name|JD Cloud Object Storage Service allocates an Internet access domain name and an intranet access domain name for each Bucket by default|
|Region|Region or data center|Data center where storage cluster locates, currently there are three data centers, i.e. North China, South China and East China|
|Accesskey|Joint name of AccessKeyId and AccessKeySecret|AccessKeyId and AccessKeySecret are the identity for user to access JD object storage service. Users can log in user center to create AccessKeyId and AccessKeySecret after applying for and turning on use qualification for JD Cloud products|
|Put Object|Simple upload|User can upload a single Object by way of Put Object in APIs, which is applicable to the scenario where uploading can be done upon any HTTP request interaction, e.g. small file uploading|
|Multipart Upload|Multipart upload|Besides PUT Object, OSS provides another uploading mode --- Multipart Upload. If the user cannot determine the size of uploading file or the uploading file is large and requires breakpoint upload, use Multipart Upload uploading mode|
|Get Object|Simple download|Used to obtain an Object|
|Object Meta|File metadata, used to describe file information, e.g. length, type, etc.|A group of Key-Value combination, consisting of System-Defined Metadata and User-Defined Metadata|
|Data|File data|Any type of data uploaded by user, such as text, multimedia, binary|
|Key|File name|Unique name identifier of Object, e.g. test.jpg|
|Bucket Policy|Storage space or file permission|Access permission control of storage space|
