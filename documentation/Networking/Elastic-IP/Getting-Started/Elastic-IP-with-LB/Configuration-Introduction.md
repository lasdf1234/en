# Configuration Description

This Tutorial will guide you to create a Load Balancer in the Virtual Private Cloud and make the Load Balancer associate Elastic IP to realize the diversion function of Load Balancer during the public network’s access to the Virtual Machine. This Tutorial is applicable to the scenario where a number of Virtual Machines provide outward services and the traffic distribution is required, such as large websites.

## Before Creation

- Make sure you have registered your JD Cloud account and finished real-name verification.

- Make sure you have created an Elastic IP which has not associated resources.

## Action Steps

Step 1: create a Virtual Private Cloud (VPC)

Step 2: create a Load Balancer based on VPC you have created.

Step 3: during the process of creating a Load Balancer, you may choose to allocate an Elastic IP or no Elastic IP. This Tutorial is based on the allocation of no Elastic IP.

Step 4: make the Load Balancer you have created associate Elastic IP in either Load Balancer associating Elastic IP or Elastic IP associating Load Balancer.

## Follow-up Tests

After the Load Balancer associates the Elastic IP, you may test the connectivity of the Elastic IP by using Ping Elastic IP addresses.