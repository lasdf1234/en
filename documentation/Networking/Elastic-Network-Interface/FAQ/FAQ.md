# FAQ

** Q: What resources can be associated to Elastic Network Interface? **

A: Currently, Elastic Network Interface can be associated with VM resource. The Virtual Private Cloud attribute of the Elastic Network Interface must be consistent with that of VM.

** Q: Is there an Availability Zone limit for the Elastic Network Interface? **

A: The Elastic Network Interface has a region-level attribute. When it is not associated, it is not restricted to Availability Zone and can be associated to any VM that meets the Virtual Private Cloud restriction. After the Elastic Network Interface is associated, the attribute of the Availability Zone is consistent with that of the VM.

** Q: Can the migration across the Availability Zone be adopted to Elastic Network Interface? **

A: Elastic Network Interface can be migrated between Virtual Machines in different Availability Zones within the same region.

**Q: Can the primary network interface be elastically plugged on a VM? **

A: The life cycle of the primary network interface of the Virtual Machine shall be consistent with that of the Virtual Machine instance, and the elastic plugging is not allowed.
   
**Q: Can the Primary IP of the Elastic Network Interface be released? **

A: The Primary IP of the Elastic Network Interface (including the primary network interface and the secondary network interface) cannot be released, and each Elastic Network Interface is only provided with one Primary IP.

** Q: How to display the associating information when the Elastic Network Interface associated by Elastic IP is in a free state (not associated to the Virtual Machine)? **

A: The ID and name of the associated network interface can be displayed on the list of Elastic IP. If the Elastic Network Interface is unassociated and the Elastic IP is associated to the Elastic Network Interface, the state of Elastic IP is displayed as associated with the associated network displayed. However, the Instance Type Family and the instance name are displayed as blank.
