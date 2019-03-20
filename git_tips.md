** To set global config of user and email **
Open the command line.
Set your username:
__git config --global user.name "FIRST_NAME LAST_NAME"__
Set your email address:
__git config --global user.email "MY_NAME@example.com"__

** To set user and email config for a single project **
From the command line, change into the repository directory.
Set your username:
__git config user.name "FIRST_NAME LAST_NAME"__
Set your email address:
__git config user.email "MY_NAME@example.com"__
Verify your configuration by displaying your configuration file:
__cat .git/config__
