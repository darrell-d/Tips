#MYSQL

**Make a database backup dump**

`!#> mysqldump -u root -p[root_password] [database_name] > dumpfilename.sql`

**Backup multiple databases**

`!#> mysqldump -u root -p[passwprd] --databases [database1] [database2] ... > dumpfile.sql`
 
**Backup all databases**

`!#> mysqldump -u root -p[passwprd] --all-databases > dumpfile.sql`
 
 
**Restore a database**

    mysql> create database [database];
  
    Query OK, 1 row affected (0.02 sec)

    !#> mysql -u root -p[password] [database] < dumpfile.sql

    !#> mysql -u root -p[root_password] [database_name] < dumpfilename.sql
