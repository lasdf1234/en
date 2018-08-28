# Associate Elastic Network Interface

JD Cloud supports that attach an independently created secondary Elastic Network Interface to any Virtual Machine with the same Virtual Private Cloud attribute.

## Action Steps

Step 1: log in to the console of JD Cloud and enter the Console Navigation Page.

Step 2: select network - Virtual Private Cloud - Elastic Network Interface at the navigation bar on the left side of the console to enter the Elastic Network Interface list page.

Step 3: if the Elastic Network Interface is unassociated on the Elastic Network Interface list page, the associated resource key is displayed.

Step 4: click the resource association key to enter the Elastic Network Interface association resource popup.

	Description
	Currently, Elastic Network Interface can be associated with VM resource. On the Elastic Network Interface Details, the shortcut operation menu at the upper right corner is also provided with the Associate Resource key, and the function is consistent with the key on the List page.

Step 5: select the subnet where the Elastic Network Interface needs to be associated to the Virtual Machine at the resource association popup and select the Virtual Machine that needs to be associated in the Virtual Machine list.

	Description
	Currently, Elastic Network Interface can only be associated with Virtual Machine with the same Virtual Private Cloud attribute. The number of Elastic Network Interface that can be associated to each Virtual Machine is restricted by the Instance Type of the Virtual Machine. When the quota of Elastic Network Interface of the Virtual Machine reaches the upper limit, an error will occur if the Elastic Network Interface association operation is performed.

Step 6: click the OK in the resource association popup to complete the Elastic Network Interface association operation.

Step 7: return to the Elastic Network Interface list page. Since it takes 3 to 5 seconds for associating the Elastic Network Interface with the Virtual Machine to take effect, refresh the Elastic Network Interface list page after completing the association operation for 3 to 5 seconds to view the association status of the Elastic Network Interface.

## Relevant references

- [Use Limitations](../../Introduction/Restrictions.md)
