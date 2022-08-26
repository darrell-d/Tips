# MYSQL

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


# BASH
**& vs &&**

&:

If a command is terminated by the control operator &, the shell executes the command in the background in a subshell. The shell does not wait for the command to finish, and the return status is 0. Commands separated by a ; are executed sequentially; the shell waits for each command to terminate in turn. The return status is the exit status of the last command executed.

&&:

Pretty much means AND like you're used to. Runs commands in sequence

alias:
If you want to run the default version of an aliased command use \. EG: `\ls` to run the non aliased version.

# Finding things

`grep -rnw '/path/to/somewhere/' -e 'pattern'`

Usually I want to do this above

`find . -name testfile.txt`

Find a file called testfile.txt in current and sub-directories.

`find /home -name '*.jpg`

Find all `.jpg` files in the `/home` and sub-directories.

`find . -type f -empty`

Find an empty file within the current directory.

`find /home -user exampleuser -mtime 7 -iname ".db"`
Find all `.db` files (ignoring text case) modified in the last 7 days by a user named exampleuser.

# VIM
Forgot to sudo in vim? Say no more, I got you.

`:w !sudo tee %`

#Useful commands
`alternatives`: Set the default version of a commmand. EG:
`alternatives --set python /usr/bin/python3.5`
`alternatives --display python`
This command is system wide

`CTRL-a :sessionname name` -- set screen name after starting a session
`screen -xS name` -- connect to a screen by name
`screen -S name` start screen with a name

# ssh keyfile permissions (Permissions 0644 for 'key' are too open.)
 `chmod 600 discord-bot-key.pem`

