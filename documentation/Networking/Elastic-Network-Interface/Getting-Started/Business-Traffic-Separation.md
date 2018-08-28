# The traffic separation of the Virtual Machine business

This Tutorial is designed to guide you on how to associate multiple Elastic Network Interfaces on the same Virtual Machine. Each Elastic Network Interface hosts the business traffic of the intranet, public network and management network respectively, thus realizing the separation of the business traffic of a single Virtual Machine. This Tutorial is applicable to scenarios where the different security policies are applied to different business needs of the Virtual Machines and network isolation.

## Business scenarios architecture
![业务流量分离场景](../../../../image/Networking/Elastic-Network-Interface/eni-002.png)

## Before creation
- Make a reasonable network plan and create internal subnets, external subnets and management subnets in the same Virtual Private Cloud according to the network plan.
- Apply for one Virtual Machine with appropriate specification. The primary network interface of the Virtual Machine belongs to the internal subnet and is configured with appropriate Security Group policy.
- Apply for 1 Elastic IP

## Action Steps
- Step 1: login the console of JD Cloud, and enter list page of Elastic Network Interface, and click the Create key to create an Elastic Network Interface.

- Step 2: create one Elastic Network Interface in the external subnet and the management subnet respectively

- Step 3: on the list page of Elastic Network Interface, click the resources blinding key respectively to attach the auxiliary Elastic Network Interfaces in the external subnet and the management subnet to the Virtual Machine previously created.

- Step 4: associate the previously applied Elastic IP with the Primary IP of the secondary Elastic Network Interface of the external subnet

- Step 5: login the Virtual Machine through SSH to deploy internal business, external business and management business respectively, and specify different network interface exits according to business type through routing configuration tools.

## Follow-up tests
- Login the Virtual Machine through SSH and access the other Virtual Machines in internal subnet, external subnet and management subnet respectively. The normal access will confirm the successful configuration.