# Configuration Description

This Tutorial will guide you to create a container in the Virtual Private Cloud and make the container associate Elastic IP to realize the container’s access to the public network. This Tutorial is applicable to the scenario where the container provides outward services.

## Before Creation

- Make sure you have registered your JD Cloud account and finished real-name verification.

- Make sure you have created an Elastic IP which has not associated resources.

## Action Steps

Step 1: create a Virtual Private Cloud (VPC)

Step 2: create a container instance based on VPC you have created.

Step 3: during the process of creating a container instance, you may choose to allocate an Elastic IP or no Elastic IP. This Tutorial is based on the allocation of no Elastic IP.

Step 4: make the container instance you have created associate Elastic IP in either container instance associating Elastic IP or Elastic IP associating container instance.

## Follow-up Tests

After the container instance associates the Elastic IP, you may test the connectivity of the Elastic IP by using Ping Elastic IP addresses.