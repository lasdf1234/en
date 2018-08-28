# Usage Restrictions

Before using the Elastic Network Interface, please acknowledge the following usage restrictions of the Elastic Network Interface.

## Region quota
Each JD Cloud account supports the creation of 100 secondary network interfaces per region. Some resources will take up the quota of Elastic Network Interface when they are created, such as Kubernates Service.

## Private IPs
Each Elastic Network Interface can be allocated with 1 Primary IP address and 20 secondary IP addresses, and such limit cannot be modified.

#### Security Group
Each Elastic Network Interface can be associated with 1 to 5 Security Groups, and such limit cannot be modified.

## Availability Zone
Elastic Network Interface can be associated to Virtual Machine with the same Virtual Private Cloud attribute and are not limited by the Availability Zone.

## Elastic IP
Elastic IP with secondary network interface associated with “Availability Zone A” attribute is not supported.

## Miscellaneous
The Elastic Network Interface list page only displays secondary network interface operation. Please enter the details of the Virtual Machine for operations related to the primary network interface.

## The quota of Virtual Machine network interface

| Configuration of Virtual Machine	| Number of Elastic Network Interface	|
| :- | :- |
|CPU: 1 core -2 cores 	|2	|
|CPU: 4-8 cores	|4	|
|CPU: more than 8 cores	|8	|

