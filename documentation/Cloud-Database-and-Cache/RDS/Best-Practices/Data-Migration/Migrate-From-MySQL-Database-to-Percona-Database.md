# Data Transferring from MySQL Service to Percona Service
It mainly explains how to transfer data from JD Cloud MySQL service to JD Cloud Percona service. The Percona service provides some more-advanced functions and characteristics than the MySQL service does, and see the detailed comparison between Percona and MySQL in [Official Manual of Percuna](https://www.percona.com/software/mysql-database/percona-server/feature-comparison).

## Precautions
* Use the VM as the transmission medium if to import the data from the MySQL service to the Percona service.
* Create an instance of the Percona service, and the VM is required to share one virtual private cloud with the Percona service.
* Ensure the capacity space of the new instance of the Percona service not smaller than the MySQL service.

## Operation Steps
1. See specific steps of VM creation in [Create VM Instance](https://www.jdcloud.com/help/detail/303/isCatalog/1). Pay attention to following matters when creating VM instances.
    * Make sure that the VM shares one ***virtual private cloud*** with the MySQL service.
    * Make sure that ***Network ACL*** of the subnet where the VM exists, is allowed to access the MySQL service.
2. Start exporting the data from the MySQL service to the VM and execute the command after VM instance creation in completed.

    ```
    mysqldump -u用户名 -p密码 --single-transaction  --set-gtid-purged=OFF -B 数据库名称 > /路径/导出文件名.sql

    参数描述
        用户名：云数据库 MySQL 的用户名。
        密码：云数据库 MySQL 的密码。
        数据库名称：填写您需要导出的库名，多个库名通过空格来分隔。
    ```

3. Create the Percona service after exporting data from the MySQL service to the VM.
4. See specific steps of the Percona service creation in [Create Cloud Database RDS Instance](to be added).
5. Create a database via the console to ensure that the name of the database to be exported from the MySQL service is also created in the Percona service. See specific creation steps in [Create Database](to be added).
6. Create a database account via the console, or use the account that created for the Percona service creation, and then give this account the read-write authorization for the new database created in step 2. See specific creation steps in [Create Account](to be added).
7. Start importing the data from the VM to the Percona service and execute the command after completing the creation and initialization of the Percona service.

    ```
    mysql -u用户名 -p密码 -h 云数据库域名 < /云主机路径/导出文件名.sql

    参数描述
        用户名：第 6 步操作中的用户名。
        密码：第 6 步操作中的用户对应的密码。
        数据库域名：云数据库 Percona 的域名可以在实例的详情页查看。
    ```

8. Zero error prompt indicates successful import. You can log in the Percona service to see if the data has been imported.
