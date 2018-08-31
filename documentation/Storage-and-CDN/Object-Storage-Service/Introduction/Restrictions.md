# Limitation description

Use limit of JD Cloud object storage service is as below:

|Limit item|Description|
|-|-|
|Storage space|1. A same user can create a maximum of 20 storage spaces in each region. <br>2. Once successfully created, the name and region of the storage space cannot be modified. <br>3. Name of storage space is globally unique. <br>4. You need to delete all file resources and image styles in this storage space before deleting the storage space. <br>5. Naming length of storage space must be between 3-63 characters and the name can only be composed of lowercase letters, numbers, and line-through (-) and can only start and end with lowercase letters or numbers. <br>6. Console currently will not support bucket to associate with customized domain name by default. If this function is required, you need to separately apply for open ticket. |
|Upload file|1. Size of files uploaded through console cannot exceed 1GB <br>2. When uploaded by way of ordinary upload or multipart upload, size of a single file or multipart cannot exceed 5GB. <br>3. If a file size exceeding 5GB is uploaded, the mode of multipart upload must be used; the maximum allowable uploading size is 48.8TB. <br>4. File with a same name is supported to be uploaded, but it will replace the original file.
|Delete file|1. Files are unrecoverable if deleted. <br>2. If arrearage is not made up within 60 days after the service is suspended due to insufficient balance, all files will be automatically deleted. <br>3. Deletion in batches is not supported currently.
|Access key Management|1. User will not automatically create Access Key when turning on Object Storage Service. <br>2. It needs to be manually created in the AccessKey Management of Personal Center; a maximum of 5 Access Keys can be created.
