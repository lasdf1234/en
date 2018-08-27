# Configuration Description

This Tutorial will guide you to create a Virtual Machine in the Virtual Private Cloud and make the Virtual Machine associate Elastic IP to realize the Virtual Machine’s access to the public network. This Tutorial is applicable to the scenario where the Virtual Machine provides outward services, such as building websites, BBS and personal blogs.

## Before Creation

- Make sure you have registered your JD Cloud account and finished real-name verification.

- Make sure you have created an Elastic IP which has not associated resources.

## Action Steps

Step 1: create a Virtual Private Cloud (VPC)

Step 2: create a virtual machine based on VPC you have created.

Step 3: during the creation of a Virtual Machine instance, you may choose to allocate an Elastic IP or no Elastic IP. This Tutorial is based on the allocation of no Elastic IP.

Step 4: make the Virtual Machine you have created associate Elastic IP in either Virtual Machine associating Elastic IP or Elastic IP associating Virtual Machine.

## Follow-up Tests

After the Virtual Machine associates the Elastic IP, you may test the connectivity of the Elastic IP by using Ping Elastic IP addresses.