# Data Transferring from VM MySQL to MySQL Service
It mainly explains how to transfer data from the self-built VM MySQL to JD Cloud MySQL service. The self-built MySQL requires operations such as daily maintenance, monitoring and backup, while JD Cloud MySQL service spares these operations and only requires user's attention on the use.

## Precautions
* New MySQL instance is required to share one ***virtual private cloud*** with the VM.
* Ensure the capacity space of the new MySQL instance not smaller than the MySQL self-built in VM.

## Operation Steps
1. See specific steps of the MySQL service creation in [Create Cloud MySQL Database Instance](to be added).
2. Create a database via the console to ensure that the name of the database to be exported from the self-built VM MySQL is also created in the MySQL service. See specific creation steps in [Create Database](to be added).
3. Create a database account via the console, or use the account that created for the MySQL service creation, and then give this account the ***read/write*** authorization for the new database created in step 2. See specific creation steps in [Create Account](to be added).
4. Export the data from the self-built VM MySQL to the VM local and execute the command after completing the creation and initialization of the MySQL service.

    ```
    mysqldump -u User name -p Password --single-transaction --set-gtid-purged=OFF -B Database name > /Path/Outputted file name.sql

    Parameter description
        User name: User name of self-built database.
        Password: Password of self-built database.
        Database name: Fill in database names to be outputted and separate several database names with spaces
    ```

5. Import the data into the MySQL service and execute the command after exporting self-built MySQL data from the VM to the local.

    ```
    mysql -u User name -p Password -h Cloud database domain < /Path/Outputted file name.sql

    Parameter description
        User name: User name in actions of step 3
        Password: Corresponding password of the user in actions of step 3
        Database domain: Please view domain of MySQL service in the Details page of instance.
    ```
    
6. Zero error prompt indicates successful import. You can log in the MySQL service to see if the data have been imported.
