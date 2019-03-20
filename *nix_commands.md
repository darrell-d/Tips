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


#BASH
** & vs && **

&:
If a command is terminated by the control operator &, the shell executes the command in the background in a subshell. The shell does not wait for the command to finish, and the return status is 0. Commands separated by a ; are executed sequentially; the shell waits for each command to terminate in turn. The return status is the exit status of the last command executed.

&&:
Pretty much means AND like you're used to. Runs commands in sequence

