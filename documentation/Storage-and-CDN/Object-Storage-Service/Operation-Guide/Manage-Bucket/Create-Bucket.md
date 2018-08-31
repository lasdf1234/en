# Create storage space

Once the JD Cloud object storage service is provided, you need to create a storage space to save files. The storage space creating steps are as follows:

1. Log in the JD Cloud console, select Object Storage Service -> Space Management to log in the space management page and click the Create a new space:

![新建空间](https://github.com/jdcloudcom/cn/blob/edit/image/Object-Storage-Service/OSS-027.png)

2. Click the new space creation and the following popup will be shown,

![新建空间弹窗](https://github.com/jdcloudcom/cn/blob/edit/image/Object-Storage-Service/OSS-028.png)

3. The storage space can be created by choosing and switching different regions. At present, JD Cloud only supports four regions, including cn-north-1, cn-south-1, cn-east-1 and cn-east-2. The resource intranets of different regions can't be connected to each other, and the regions can't be changed after being created. If you need to access the object storage service via the virtual machine intranet, please select the region as the same as that of your virtual machine.

4. In the space name text box, the naming of storage space must conform to naming specification (relevant notifications after ? of the text box). The selected storage space name must be globally universe among all current storage space names of the JD Cloud object storage service. The storage space name can’t be changed after being created.

5. JD Cloud's storage space supports four access permissions, “public read and private write”, “private read/write”, “public read/write” and “customized permissions” respectively

 * Public read and private write: Only the creator of the storage space can carry out the write action to files in the storage space, anyone (including anonymous access) can carry out the read operation to files in the storage space.

 * Private read/write: Only the creator of the storage space can carry out the write and read actions to files in the storage space, and others can’t access files in the storage space.

 * Public read/write: Anyone (including anonymous access) can carry out write and read actions to files in the storage space.

 * Customized permissions: The permissions of GetObject, PutObject, DeleteObject, ListObjects, DeleteBucket for the assigned users can be set, the resources that the permissions can access can be assigned, and the IP addresses and Referer white list with the permissions can be assigned.

6. Click “OK” button to finish creation of storage space.

