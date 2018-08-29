# Restore Backup Files to the Self-built Percona Service 
You can restore the backup data of the Percona service to the self-built database.

## Precautions
* The self-built database version shall be consistent with the source database version of backup files.
* The backup unzipping software can only be used in Linux.
* System software of unzipping tools relies on openssl, gzip, tee and python, with version >= 2.7.
* The current system has already been installed with percona xtrabackup >= 2.4; If not, please refer to [Official Manual](https://www.percona.com/doc/percona-xtrabackup/2.4/index.html).

## Operation Instructions
1. See the requirements for installation environment in precautions.
2. Download the backup unzipping tool, [Click to Download](https://jddb-common-public.oss.cn-north-1.jcloudcs.com/percona_backup_extract_tool.tar.gz) and unzip. The tool name is `percona_backup_exztract.py`, and the using instances are as follows.
    
    ```
    # 查看帮助手册
    ./percona_backup_extract.py -h
     
     # 解压云数据库 Percona 实例的备份数据
     ./percona_backup_extract.py  -v 5.7 -f ./backup.xbstream.gz.enc
    ```
3. Download backup files.

    ```
    wget -c '<数据备份下载地址>' -O <自定义备份文件名>.xbstream.gz.enc

    -c：启动断点续传
    -O：将下载的结果保存为指定的文件，注意文件的后者必须是 .xbstream.gz.enc
    ```

4. Unzip the backup data, and the unzipped files will be saved in tmp_snapshot, a sub-directory of the current directory, assuming that the current directory is $HOME.

    ```
    ./percona_backup_extract.py -v 5.7 -f <自定义备份文件名>.xbstream.gz.enc
    
    -v 参数可以不指定，默认：5.7，具体 -v 后面可以跟什么变量可以通过 -h 查看帮助手册得知。
    ```

5. Restore the unzipped backup files.

    ```
    innobackupex --defaults-file=$HOME/tmp_snapshot/backup-my.cnf --apply-log $HOME/tmp_snapshot
    ``` 
    ***innobackupex completed OK!*** indicates successful execution, and you can continue to the next step.

6. Modify the configuration file, backup-my.cnf.

    ```
    # The MySQL server
    [mysqld]
    innodb_checksum_algorithm=innodb
    #innodb_log_checksum_algorithm=strict_crc32
    innodb_data_file_path=ibdata1:512M;ibdata2:512M:autoextend
    innodb_log_files_in_group=3
    innodb_log_file_size=536870912
    #innodb_fast_checksum=false
    #innodb_page_size=16384
    #innodb_log_block_size=512
    innodb_undo_directory=.
    innodb_undo_tablespaces=0
    #redo_log_version=1
    ```

7. Modify the file owner and confirm that files are owned by the MySQL user.

    ```
    chown -R mysql:mysql $HOME/tmp_snapshot
    ```

8. Start the Percona process.

    ```
    mysqld --defaults-file=$HOME/tmp_snapshot/backup-my.cnf --user=mysql --datadir=$HOME/tmp_snapshot --socket=$HOME/tmp_snapshot/mysql.sock &
    ```

9. Login the MySQL service.

    ```
    mysql -uroot -p --socket=$HOME/tmp_snapshot/mysql.sock
    ```

* Click "Enter" directly due to the default blank password.
