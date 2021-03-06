# Installation

## Environment preparation

Applicable to revision JDK 6 or above.

## Installation method

**Import JAR package into Eclipse project:**

Take revision 1.0.3 as an example, with the following steps:

1. Download Java SDK [Java SDK](http://downloads.oss.cn-north-1.jcloudcs.com/jfs-jcloud-sdk-java-1.0.3-SNAPSHOT.jar)

2. Unzip the SDK.

3. Copy the file jfs-jcloud-sdk-java-<versionId>.jar in the unzipped folder and all files in the lib folder of the demo project into your project.

4. Select your project in the Eclipse, right click and select Properties > Java Build Path > Add JARs.

5. Select all JAR files you copied in step 3.

You can use OSS Java SDK in the Eclipse project through the above steps.


## Example project

OSS Java SDK provides an example project that you can run on your local device. You can also develop your applications based on the example project.

* Example project:[jfs-jdcloud-sdk-java-demo.zip](http://downloads.oss.cn-north-1.jcloudcs.com/jfs-jcloud-sdk-java-demo.zip)

* Rich example programs are provided in the example project for the convenience of user reference or direct use

The example includes the following contents:

|Example file|Example contents|
|-|-|
|JcloudOSSDemo|Demonstrate quick start example for cloud storage use|
|InitOSSSample|Demonstrate the method of OSS initialization|
|ObjectSample|Demonstrate the basic object relevant actions, such as upload, download, delete, etc.|
|PutObjectSample|Demonstrate the usage of simple file upload|
|GetObjectsample|Demonstrate the usage of downloading files|
|DeleteObjectSample|Demonstrate the usage of deleting files|
|MoveObjectSample|Demonstrate the usage of moving files|
|ListObjectSample|Demonstrate the usage of listing files|
|PresignedUrlSample|Demonstrate the usage of creating pre-signed URI|
|BucketSample|Demonstrate the usage of configuring storage space, including basic actions (create, delete, display all storage space of the account) of the storage space, relevant actions of anti-theft chain, etc.|
|MultipartUploadSample|Demonstrate the usage of multipart upload of large files|
