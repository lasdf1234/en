# Data Transferring from VM Percona to Percona Service 
It mainly explains how to transfer data from the self-built VM Percona to JD Cloud Percona service. The self-built Percona requires operations such as daily maintenance, monitoring and backup, while JD Cloud Percona service spares these operations and only requires user's attention on the use.

## Precautions
* New Percona instance is required to share one ***virtual private cloud*** with the VM.
* Ensure the capacity space of the new Percona instance not smaller than the Percona self-built in VM.

## Operation Steps
1. See specific steps of the Percona service creation in [Create Cloud Database RDS Instance](to be added).
2. Create a database via the console to ensure that the name of the database to be exported from the self-built VM Percona is also created in the Percona service. See specific creation steps in [Create Database](to be added).
3. Create a database account via the console, or use the account that created for the Percona service creation, and then give this account the ***read/write*** authorization for the new database created in step 2. See specific creation steps in [Create Account](to be added).
4. Export the data from the self-built Percona of the VM to the local of the VM and execute the command after completing the creation and initialization of the Percona service.

    ```
    mysqldump -u用户名 -p密码 --single-transaction --set-gtid-purged=OFF -B 数据库名称 > /路径/导出文件名.sql

    参数描述
        用户名：自建数据库的用户名。
        密码：自建数据库的密码。
        数据库名称：填写您需要导出的库名，多个库名通过空格来分隔。
    ```

5. Import the data into the Percona service and execute the command after exporting self-built Percona data from the VM to the local.

    ```
    mysql -u用户名 -p密码 -h 云数据库域名 < /路径/导出文件名.sql

    参数描述
        用户名：第 3 步操作中的用户名。
        密码：第 3 步操作中的用户对应的密码。
        数据库域名：云数据库 Percona 的域名可以在实例的详情页查看。
    ```
    
6. Zero error prompt indicates successful import. You can log in the Percona service to see if the data has been imported.
