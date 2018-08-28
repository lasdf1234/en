# Virtual Machine hosts multiple businesses

This tutorial will guide you to deploy multiple public network services on the same Virtual Machine and associate an IP address for each business. So that a single Virtual Machine hosts multiple businesses can be realized to reduce the cost. This Tutorial is applicable primarily to scenarios where a single Virtual Machine provides multiple HTTPS businesses and different public IP are required to be used to associate different certificates.

## Business scenarios architecture
![Multi-service bearer scenario](../../../../image/Networking/Elastic-Network-Interface/eni-001.png)

## Before creation
- Apply for a Virtual Machine with appropriate specifications and configure appropriate Security Group policy.
- Apply for the required number of Elastic IP.

## Action Steps
- Step 1: Login the console of JD Cloud, and enter the Instance List page of Virtual Machine, then click the Virtual Machine name to enter the Virtual Machine details.

- Step 2: enter the Virtual Machine details, and click the tag page of Elastic Network Interface to switch to the management page of Elastic Network Interface.

- Step 3: select the Elastic Network Interface that needs to host traffic and enter the IP management page of the Elastic Network Interface.

- Step 4: on the IP management page of the Elastic Network Interface, allocate the same number of Private IP addresses that match the number of businesses.

- Step 5: associate one Elastic IP address for each Private IP address on the IP management page of Elastic Network Interface.

- Step 6: login the Virtual Machine through SSH to deploy related services, and specify different source IP addresses for different business traffics.

## Follow-up tests
- The access to specific business can be achieved by accessing a specific public IP address or its corresponding domain name.
