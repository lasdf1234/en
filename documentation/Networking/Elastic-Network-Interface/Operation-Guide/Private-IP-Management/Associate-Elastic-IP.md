# Associate EIP

Each Private IP (including Primary IP and secondary IP) allocated by Elastic Network Interface of JD Cloud (including primary network interface and secondary network interface) can be connected with one Elastic IP.

## Action Steps
Step 1: log in to the console of JD Cloud and enter the Console Navigation Page.

Step 2: select network - Virtual Private Cloud - Elastic Network Interface at the navigation bar on the left side of the console to enter the Elastic Network Interface list page.

Step 3: locate the Elastic Network Interface that needs to be associated with Private IP, and click the ID of the Elastic Network Interface to enter the details of Elastic Network Interface.

Step 4: select the Private IP management tag and enter the Private IP management page.

Step 5: locate the Private IP that needs to be associated to the public network IP, and if the Private IP is not associated to the public network IP, the key of Associate EIP will be displayed.

Step 6: click the Associate EIP key to enter the Associate EIP popup.

	Description
	Currently, only the primary network interface of Virtual Machine of Availability Zone A can be associated with Elastic IP with the attribute of Availability Zone A. Elastic IP with the attribute of full Availability Zone can be adopted for Virtual Machine of Availability Zone B or any secondary network interface.

Step 7: in the Associate EIP popup, select Elastic IP to be associated.

Step 8: click OK to complete the association of Elastic IP and return to the Private IP management page to view the association of Elastic IP.

## Relevant references

- [use limitations](../../Introduction/Restrictions.md)
