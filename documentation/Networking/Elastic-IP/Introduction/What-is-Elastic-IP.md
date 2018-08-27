# Product Overview

Elastic IP is Public IP that may be independently applied for, and supports dynamically associating and disassociating Virtual Machine, container, Load Balancer, and NFV Instance. The mail function of Elastic IP is to block instance fault, that is, through manual configuration the Elastic IP may drift to a redundant instance in case of fault so as to achieve rapid response.

Currently, JD Cloud uses the industry-leading high-availability technology of the dual-active vRouter (Virtual Router). Compared with the traditional high-availability mode of the active and standby vRouter, the technology may provide link redundancy and high availability in scenarios such as high concurrent connections, large traffic load, and traffic bursts. With this technology, the maximum bandwidth of JD Cloud Elastic IP may reach 150% of the bandwidth actually purchased by a user, providing guarantee for the user’s business.

Based on the traffic sharing model of the dual-active vRouter, the maximum bandwidth of the Elastic IP is generally 150% of the bandwidth actually purchased by a user. In a rare special case, such as single access to FTP files, the maximum bandwidth of Elastic IP is around 75% of the bandwidth actually purchased by a user.

The Elastic IP mainly has the following characteristics:

* Complete elasticity: the Public IPs provided by JD Cloud are all Elastic IPs. Whether you purchase Elastic IP separately or together with other resources of the Virtual Machine, you may modify the association between Elastic IP and cloud resource.

* Supporting the association of multiple resources: Elastic IP supports associating, Virtual Machine, container, Load Balancer, and NFV instance, providing access to public network for cloud resources.

* Supporting multiple billing types: Elastic IP supports three types of billing, i.e. monthly package, pay by configuration, and pay by consumption. Users may choose appropriate billing type as required for their business.

* Flexible adjustment of bandwidth: Elastic IP supports the adjustment of bandwidth, and users may modify bandwidth based on the requirement for change in business and traffic. The modification will be effective immediately.

## Common Operation

- Elastic IP Management
	- [Create Elastic IP](../Operation-Guide/Elastic-IP-Management/Create-Elastic-IP.md)
	- [Delete Elastic IP](../Operation-Guide/Elastic-IP-Management/Delete-Elastic-IP.md)
	- [Associate Elastic IP](../Operation-Guide/Elastic-IP-Management/Associate-Elastic-IP.md)
	- [Disassociate Elastic IP](../Operation-Guide/Elastic-IP-Management/Disassociate-Elastic-IP.md)
	- [Modify Elastic IP bandwidth](../Operation-Guide/Elastic-IP-Management/Modify-Elastic-IP.md)
- View Elastic IP resource information
	- [View Elastic IP resource information](../Operation-Guide/View-Elastic-IP-Detail/View-Elastic-IP-Detail.md)
- View Elastic IP monitoring information
	- [View Elastic IP monitoring information](../Operation-Guide/View-Elastic-IP-Monitoring/View-Elastic-IP-Monitoring.md)
- View Elastic IP billing information
	- [View Elastic IP billing information](../Operation-Guide/View-Elastic-IP-Billing/View-Elastic-IP-Billing.md)
- Export Elastic IP List
	- [Export Elastic IP List](../Operation-Guide/Export-Elastic-IP-List/Export-Elastic-IP-List.md)

## Billing
The Elastic IP supports three billing types, i.e. monthly package, pay by configuration, and pay by consumption. For details, refer to: [Billing Instructions](../Pricing/Billing-Overview.md)
