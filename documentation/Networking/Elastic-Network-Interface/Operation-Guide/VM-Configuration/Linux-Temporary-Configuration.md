# Linux system temporary configuration

This Tutorial takes the CentOS 6.8 operating system as an example to explain how to configure the Elastic Network Interface in Virtual Machine (which does not save the configuration of the Elastic Network Interface permanently, and will become invalid after rebooting).

**Note: the contents in brackets are filled out by the user. **

## Action Steps
Step 1: associate Elastic Network Interface to the target Virtual Machine in the JD Cloud console.

Step 2: remotely log on the target Virtual Machine via SSH.

Step 3: execute the following command to query the name of the attached Elastic Network Interface.

	# ifconfig -a

Step 4: execute the following command to enable Elastic Network Interface.

	# ifconfig [device name] up

Step 5: execute the following command to configure the Primary IP of Elastic Network Interface.

	# ifconfig [device name] [primary ip] netmask [netmask] broadcast [broadcast ip]

Step 6: execute the following command to configure the secondary IP of Elastic Network Interface.

	# ifconfig [device name]:[secondary ip sequence number] [secondary ip] netmask [netmask] broadcast [broadcast ip]


