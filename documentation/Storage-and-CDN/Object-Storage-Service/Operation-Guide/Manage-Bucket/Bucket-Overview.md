# Space overview

All files in the JD Cloud object storage service must be stored in the storage space (Bucket). Storage space is the unit that you use to manage your stored files, and all objects must belong to a certain storage space. You can set access permissions, anti-theft chain rules, etc. for the storage space; these attributes are applied to all files in the storage space, so you can flexibly create different storage spaces to complete different management functions.

The space inside the same storage space is flat, namely there is no concept of a directory of a file system, and all files directly belong to their corresponding storage spaces. However, you can use folders to group, classify and manage relevant files.

To access and view a storage space, select Object Storage Service->Space Management after logging in to the JD Cloud console; after entering the space management page, click on the storage space to be accessed, and you will enter the overview page of the storage space with the following effects:

![空间概览](https://github.com/jdcloudcom/cn/blob/edit/image/Object-Storage-Service/OSS-026.png)

The description related to the contents shown on this page is as follows:

1. The basic information of each space will include the space name, current access permissions, creation time, intranet access domain name and Internet access domain name;

2. Below the basic information is the utilization within one month before the current date of the storage space, including the storage space capacity, the downlink traffic generated through the Internet access domain name, and the number of http requests.
