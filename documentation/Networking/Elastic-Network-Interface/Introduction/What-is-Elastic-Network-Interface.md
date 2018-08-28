# Product overview

Elastic Network Interface is a virtual network interface, making Elastic Network Interface can be associated on the Virtual Machine to connect the Virtual Machine to different networks. The Elastic Network Interface is applicable in building application scenarios such as business traffic separation, multiply businesses hosting and network high availability. The JD Cloud Elastic Network Interface is an Elastic Network Interface with region-level, which can be associated to any Availability Zone Virtual Machine in the Virtual Private Cloud. Each Virtual Machine can be associated with multiple Elastic Network Interfaces, and the associated number depends on the Instance Type of Virtual Machine.

The Elastic Network Interface mainly has the following characteristics:

* Multiple network interfaces and multiple IPs: based on the Instance Type of Virtual Machine, each Virtual Machine of JD Cloud can be associated with multiple Elastic Network Interfaces, and each Elastic Network Interface can be allocated with multiple Private IP addresses. At the same time, each Private IP address can be connected with one Elastic IP address.

* Elastic plugging: The JD Cloud Elastic Network Interface is an Elastic Network Interface with region-level, which can be associated to any Availability Zone Virtual Machine in the Virtual Private Cloud. In the case of failure, the Elastic Network Interface can be disassociated from the failed Virtual Machine and migrated to another standby Virtual Machine.

* Business security: each Virtual Machine of JD Cloud can be attached with multiple under the subnet, and the traffic of specific business can be hosted by specific Elastic Network Interface. Different Elastic Network Interfaces can be independently associated with different Security Groups, which applied to different Security Group policies, thus improving the security of the business traffic.

* Routing control: each Virtual Machine of JD Cloud can be attached with Elastic Network Interface with different subnets in the same Virtual Private Cloud, and each subnet can be set with identity and access management policies and routing forwarding policies respectively. By matching the internal routing configuration tools of Virtual Machines, accurate control of network traffic can be realized.

## Common operation

- Management of Elastic Network Interface
	- [Create Elastic Network Interface](../Operation-Guide/Elastic-Network-Interface-Management/Create-Elastic-Network-Interface.md)
	- [Delete Elastic Network Interface](../Operation-Guide/Elastic-Network-Interface-Management/Delete-Elastic-Network-Interface.md)
	- [Associate Elastic Network Interface](../Operation-Guide/Elastic-Network-Interface-Management/Associate-Elastic-Network-Interface.md)
	- [Disassociate Elastic Network Interface](../Operation-Guide/Elastic-Network-Interface-Management/Disassociate-Elastic-Network-Interface.md)
	- [Enable to delete on instance termination](../Operation-Guide/Elastic-Network-Interface-Management/Enable-Delete-with-VM.md)
	- [Cancel deleting on instance termination](../Operation-Guide/Elastic-Network-Interface-Management/Disable-Delete-with-VM.md)
- Management of Private IP
	- [Allocate Private IP](../Operation-Guide/Private-IP-Management/Allocate-Secondary-IP.md)
	- [Release Private IP](../Operation-Guide/Private-IP-Management/Unassign-Secondary-IP.md)
	- [Associate public network IP](../Operation-Guide/Private-IP-Management/Associate-Elastic-IP.md)
	- [Disassociate public network IP](../Operation-Guide/Private-IP-Management/Disassociate-Elastic-IP.md)
- Management of Security Group
	- [Add Security Group](../Operation-Guide/Security-Group-Management/Associate-Security-Group.md)
	- [Remove Security Group](../Operation-Guide/Security-Group-Management/Disassociate-Security-Group.md)
- Virtual Machine configuration
	- [Linux system temporary configuration](../Operation-Guide/VM-Configuration/Linux-Temporary-Configuration.md)
	- [Linux system permanent configuration](../Operation-Guide/VM-Configuration/Linux-Temporary-Configuration.md)

## Billing
The Elastic Network Interface service is free, and the Elastic IP associated with the Elastic Network Interface is charged independently. For details, refer to: [Billing Instructions](../Pricing/Billing-Overview.md)
