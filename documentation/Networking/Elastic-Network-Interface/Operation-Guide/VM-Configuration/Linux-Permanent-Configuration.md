# Linux system permanent configuration

This Tutorial takes the CentOS 6.8 operating system as an example to explain how to configure the Elastic Network Interface in Virtual Machine (which saves the configuration of the Elastic Network Interface permanently, and Virtual Machine will remain in effect after rebooting).

**Note: the contents in brackets are filled out by the user. **

## Action Steps
Step 1: associate Elastic Network Interface to the target Virtual Machine in the JD Cloud console.

Step 2: remotely log on the target Virtual Machine via SSH.

Step 3: execute the following command to query the name of the attached Elastic Network Interface.

	# ifconfig -a

Step 4: execute the following command to enter the network interface configuration file directory.

	# cd /etc/sysconfig/network-scripts

Step 5: execute the following command to create configuration file of Elastic Network Interface.

	# touch ifcfg-[device name]

Step 6: execute the following command to enable editing for configuration file of Elastic Network Interface.

	# vi ifcfg-[device name]

Step 7: replace and fill in the following contexts in the configuration file of Elastic Network Interface.

	DEVICE=[device name]
	NM_CONTROLLED=yes
	ONBOOT=yes
	IPADDR=[primary ip]
	NETMASK=[netmask]

Step 8: execute the following command to restart the network service so that the configuration can take effect.

	# service network restart

