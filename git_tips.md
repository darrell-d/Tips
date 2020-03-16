**To set global config of user and email**

Open the command line.

Set your username:

*git config --global user.name "FIRST_NAME LAST_NAME"*

Set your email address:

  *git config --global user.email "MY_NAME@example.com"*

**To set user and email config for a single project**

From the command line, change into the repository directory.

Set your username:

*git config user.name "FIRST_NAME LAST_NAME"*

Set your email address:

*git config user.email "MY_NAME@example.com"*

Verify your configuration by displaying your configuration file:

*cat .git/config*

## Save credentials on server
`git config --global credential.helper store` followed by `git pull`
