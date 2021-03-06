# Create account
Before using database, you need to create account in the block chain data service instance. You can't manage the database account by SQL statement but only by actions on console.

## Precautions
* Database created by starting synchronization service can only set read permission.

## Action Steps
1. Log in [Block chain data service console](https://bds-console.jdcloud.com/block/list). 
2. Select the target instance needs to create account and click the target instance to enter the Details of the instance. 
3. Select  **Account Management** tag to open the Account Management; click  **Create Account** button to modify the parameters in the account popup as below description 
    * Database account and password: we reserved some keyword names for database accounts for your reference [Actions Limit](to be supplemented) and the length and characters of the account and password have some limits which is subject to the console.
    * Authorize database: database authorized by this account
        * Add authorized database, click the database name in the authorizable database list and click the middle button “>”, then the selected database name will be removed from the authorizable database list and added to the end of the authorized database list. **Read Only** permission is selected by default.
        * Remove authorized database, click the database name in the authorized database list and click the middle button “<”, then the selected database name will be removed from the authorized database list and added to the end of the authorizable database list.
        * Modify in batches the permission of authorized database, move the mouse to **Full Read/Write Access** to select an option in the dropdown menu, then the database permission in the authorized database list will all be modified to corresponding options.
    ![Create account](Pic/Create account.png)

4. Click ***OK*** button to create account and return to the account management page.
