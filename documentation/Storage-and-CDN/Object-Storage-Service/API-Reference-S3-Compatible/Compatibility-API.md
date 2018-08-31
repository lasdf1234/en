# Compatible interface

|api supported by cloud storage|api introduction|description|
|-|-|-|
|GET Service(List Bucket)|Get all Buckets under a User|Compatible [GET Service](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTServiceGET.html)|
|PUT Bucket|Create a new Bucket, the permission by default is Private|Compatible [PUT Bucket](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUT.html)|
|HEAD Bucket|Confirm if a Bucket exists and has a right to access <br>? If Bucket exists and has a right to access, return 200 OK. If designated bucket does not exist, return 404 Not Found|Compatible [HEAD Bucket](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketHEAD.html)|
|GET Bucket(List Object)|Get information of Object under Bucket（Compatible Version2）|Compatible [GET Bucket](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/v2-RESTBucketGET.html)|
|DELETE Bucket|Delete the designated Bucket|Compatible [DELETE Bucket](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETE.html)|
|PUT Object|Upload an Object to OSS|Compatible [PUT Object]|(https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectPUT.html)
|GET Object|Get Meta and data of an Object, Can get all data or get part of data by designation using Range|Compatible [GET Object](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectGET.html)|
|HEAD Object|Get Meta of an Object|Compatible [HEAD Object](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectHEAD.html)|
|DELETE Object|Delete an Object|Compatible [DELETE Object](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectDELETE.html)|
|Initiate MultiPart Upload|Initiate MultiPart Upload Task|Compatible [Initiate MultiPart Upload](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadInitiate.html)|
|Upload Part|Upload a Part to OSS|Compatible [Upload Part](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadUploadPart.html)|
|Complete MultiPart Upload|Combine Uploaded MultiPart to an Object|Compatible [Complete MultiPart Upload](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadComplete.html)|
|Abort MultiPart Upload|Abort a MultiPart Upload Task|Compatible [Abort MultiPart Upload](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadAbort.html)|
|List Parts|Get information of part loaded successfully by uploadid|Compatible [List Parts](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadListParts.html)|
|List MultiPart Uploads|Get MultiPart Uploads Tasks under a Bucket|Compatible[List MultiPart Uploads](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadListMPUpload.html)|
|GET Bucket policy|Get policy on assigned Bucket|Compatible [GET Bucket policy](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketGETpolicy.html)|
|PUT Bucket policy|Add or edit policy for assigned Bucket|Compatible [PUT Bucket policy](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUTpolicy.html)|
|DELETE Bucket policy|Delete policy on assigned Bucket|Compatible [DELETE Bucket policy](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEpolicy.html)|
|PUT Bucket acl|Set acl on assigned Bucket|Compatible [PUT Bucket acl](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUTacl.html)|
|GET Bucket acl|Get acl on assigned Bucket|Compatible [GET Bucket acl](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketGETacl.html)|
|PUT Bucket cors|Add CORS statement for assigned Bucket|Compatible [PUT Bucket cors](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUTcors.html)|
|GET Bucket cors|Get CORS statement of assigned Bucket|Compatible [GET Bucket cors](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketGETcors.html)|
|DELETE Bucket cors|Delete CORS statement of assigned Bucket|Compatible [DELETE Bucket cors](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEcors.html)|
|PUT Bucket website|Add static website hosting statement for assigned Bucket (Note: interface compatible, but details of statement have slight difference with S3)|Compatible [PUT Bucket website](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEcors.html)|
|GET Bucket website|Get static website hosting statement for assigned Bucket (Note: interface compatible, but details of statement have slight difference with S3)|Compatible [GET Bucket website](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEcors.html)|
|DELETE Bucket website|Delete static website hosting statement for assigned Bucket (Note: interface compatible, but details of statement have slight difference with S3)|Compatible [DELETE Bucket website](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEcors.html)|
|Put Object Copy|Copy an object already existed on OSS to another object|Unsupported: x-amz-copy-source-if-match, <br>x-amz-copy-source-if-none-match, <br>x-amz-copy-source-if-unmodified-since, <br>x-amz-copy-source-if-modified-since, <br>x-amz-tagging-directive<br>x-amz-storage-class<br>Support STANDARD and REDUCED_REDUNDANCY<br>Reference: [PUT Object - Copy](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectCOPY.html)|
|Upload Part Copy|Upload Part from copying data from an already existed Object. |Unsupported: x-amz-copy-source-if-match, <br>x-amz-copy-source-if-none-match, <br>x-amz-copy-source-if-unmodified-since, <br>x-amz-copy-source-if-modified-since<br>Reference: [Upload Part - Copy](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadUploadPartCopy.html)|
|Delete Multiple Objects|Support the user to delete multiple Objects in the same Bucket through one HTTP request|Unsupported: version<br>Reference: [Delete Multiple Objects](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/multiobjectdeleteapi.html)|
|PUT Bucket Replication|Create, modify cross-region replication configuration|Unsupported: Account, Role, Owner AccessControlTranslation SourceSelectionCriteria<br>Reference: [PUT Bucket Replication](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUTreplication.html)|
|GET Bucket Replication|Return cross-region replication configuration set on Bucket|Reference: [GET Bucket replication](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketGETreplication.html)|
|Delete Bucket Replication|Delete started cross-region replication configuration, target Bucket and object still exist after deletion|Reference: [Delete Bucket replication](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEreplication.html)|
