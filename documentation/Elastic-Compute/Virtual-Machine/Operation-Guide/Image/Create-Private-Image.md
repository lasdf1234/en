# Create a Private Image Based on an Instance
You can create a private image from an instance created as required, and use this image to launch more instances with the same operating system, pre-installed software, and related configurations as the original instance.

## Precondition
* To ensure data integrity, only instances in the "Stopped" status are supported for private image.
* You must ensure that the image and cloud disk snapshot quotas are sufficient, because if the instance system disk is a cloud disk or the instance attaches a data disk, it will take up the private image quotas and the cloud disk snapshot quotas.

## Precautions
* If the instance has an auto-attach command configured in /etc/fstab of Linux system, it shall delete the relevant auto-attach command prior to creating the private image, otherwise the instance created from its private image may not start properly.
If the current instance's system disk is a local disk, then the created private image is the local system disk image; If the current instance's system disk is a cloud disk, then the created private image is the cloud system disk image. You can convert a local system disk image to a cloud system disk image by [Image Type Conversion](Convert-Image.md).

## Operation Steps
1. Access [Virtual Machine Console][1] to enter the instance list page. Or access [JD Cloud Console][2] Click navigation bar on the left [Elastic Compute] - [Virtual Machine] - [Instance] to enter the instance list page.
2. Select the instance where you want to create a private image and click [More] - [Create Image].
![](../../../../../image/vm/Operation-Guide-Image-create1.png)
3. In the pop-up window of image creating, supplement the "Name" and "Description" of the private image,    click [OK] to start the creation of the private image.
4. You can back up the system disk when creating image, besides, you can choose a data disk attaches to the backup instance currently. The data disk will be associated with the system disk image in the form of a snapshot and displayed in the "Device Mapping Information" on the private image detail page as the preset configuration of the data disk for subsequent instance creation by using this private image, which makes it easy to quickly deploy the entire machine. If you want to modify the capacity of the data disk, you can adjust it when you create a machine based on that image. Click here for details on the data disk [Device Name Assignment Rules](../Operation-Guide/Cloud-Disk/Assign-Device-Name.md).
5. It takes a long time to make the whole image. In order to avoid the failure, please stop other operations on the machine and the cloud disk during the production process, and ensure that the current instance and the cloud disk snapshot have sufficient quotas.
![](../../../../../image/vm/Operation-Guide-Image-create2.png)
![](../../../../../image/vm/Operation-Guide-Image-create3.png)

6. The submitted private image is created successfully into "Available" status after passing through the two intermediate statuses of "Pending" and "Replicating", then it can be used normally. In the intermediate status, operations of [Share], [Create VM instance], and [Delete] on the image are not allowable.

7. In the process of image creating, any resource's failed creation will cause the image to be in the "Error" status. If the data disk attached by the machine is selected to create the whole machine image, all the snapshots created by the operation will be automatically deleted after operation failed, but the private image could be deleted after your confirmation.
![](../../../../../image/vm/Operation-Guide-Image-create4.png)
 
 ## Related Reference
 
[Image Type Conversion](Convert-Image.md)
 
[Device Name Assignment Rule](../Operation-Guide/Cloud-Disk/Assign-Device-Name.md)


  [1]: https://cns-console
  [2]: https://console.jdcloud.com/
  [3]: ./images/Operation-Guide-Image-create1.png "Operation-Guide-Image-create1.png"
  [4]: ./images/Operation-Guide-Image-create2.png "Operation-Guide-Image-create2.png"
  [5]: ./images/Operation-Guide-Image-create3.png "Operation-Guide-Image-create3.png"
  [6]: ./images/Operation-Guide-Image-create4.png "Operation-Guide-Image-create4.png"