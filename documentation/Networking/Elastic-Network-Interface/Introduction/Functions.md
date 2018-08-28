# Product Function

## Multiple network interfaces and multiple IPs

## Multiple network interface
Based on the Instance Type of the Virtual Machine, a single Virtual Machine can only be associated with 8 Elastic Network Interfaces, which belongs to the different subnets of the same Virtual Private Cloud.

## Multiple Private IPs
Based on the Instance Type of the Virtual Machine, each Elastic Network Interface of a Virtual Machine can only be allocated with 21 Private IP addresses, and all Private IP addresses on the same Elastic Network Interface belong to the same subnet.

### Multiple public IPs
Each internal network IP address allocated to one Elastic Network Interface can be associated with one Elastic IP address.

## Network interface migration

### Region level network interface

Elastic Network Interface with region-level attributes are accepted, which breaks through the limitation of available areas of traditional Elastic Network Interface. The Elastic Network Interface can be migrated elastically between Virtual Machines in different Availability Zones within the Virtual Private Cloud.

### Flexible migration

The Elastic Network Interface can be migrated flexibly between Virtual Machines in the Virtual Private Cloud to which it belongs. When the Elastic Network Interface is migrated, the allocated Private IP address, Elastic IP address, and Security Group are retained.

## Business security
 
### Independent security policy
Network interface level security policy control is accepted. The Elastic Network Interface can be associated to 5 Security Groups at most to achieve accurate control of business traffic.

### Business traffic separation
The Virtual Machine can be attached with multiple Elastic Network Interfaces, and the traffic of specific business can be hosted by specific Elastic Network Interface. Different Security Group policies are adopted to different Elastic Network Interfaces, which can realize the accurate separation of business traffic and security policies.

## Routing control

### Subnet routing
The Virtual Machine can be attached with Elastic Network Interfaces belonging to different subnets, and each subnet can be independently set with identity and access management policies and routing forwarding policies, thus realizing the safe isolation of user business from the network.

### Machine routing
Fine routing policies can be set up inside the Virtual Machine, and specific types of traffic can be forwarded by specific Elastic Network Interfaces or specific IP addresses.



