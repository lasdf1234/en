# High availability architecture of Virtual Machine

This Tutorial will guide you in building a high availability application solution across Availability Zone by using keepalived tool. In the event of a failure, the failure can be blocked by migrating the Elastic Network Interface from the primary server to the standby server. This Tutorial is applicable primarily to scenarios where the business needs to be deployed with high reliability, especially scenarios where the security policy is strongly associated with the MAC address of the network interface.

## Business scenarios architecture
![High reliability application solution](../../../../image/Networking/Elastic-Network-Interface/eni-003.png)

## Before creation
- Within the same Virtual Private Cloud, create one Virtual Machine in Availability Zone A and Availability Zone B respectively, and set up appropriate Security Group policies.
- Within the same Virtual Private Cloud, select one subnet according to the network plan and create one Elastic Network Interface in such subnet.

## Action Steps
- Step 1: login the console of JD Cloud, and enter list page of Elastic Network Interface, then select the previously created secondary Elastic Network Interface to associate it to the Virtual Machine in Availability Zone A.

- Step 2: Login the Virtual Machine of Availability Zone A and Availability Zone B respectively through SSH, and install and configure keepalived tool and then active the listen mode of unicast VRRP.

- Step 3: Write a keepalive switch function, and call the Elastic Network Interface of JD Cloud Open API, then disassociate the Elastic Network Interface and re-associate it to the standby server. Call the function to configure the standby machine network interface and route in case of failure.

## Follow-up tests
- After the deployment of both the primary and standby servers is completed, shut down the primary server and check whether the Elastic Network Interface has been migrated to the standby server in the console. Access the IP of Elastic Network Interface to see if it can be connected, if so, the switchover is done.
