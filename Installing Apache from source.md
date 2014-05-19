#Installing Apache from source

###Pre-requisites:
Make : `apt-get install make`

APR: `apt-get install libapr1-dev libaprutil1-dev`. Apr is needed for the error `checking for APR... no
configure: error: APR not found.  Please read the documentation.`

###Installation
1. Download the source files: `wget http://www.bizdirusa.com/mirrors/apache//httpd/httpd-2.4.9.tar.gz`
2. Extract source files : `tar -zxvf httpd-2.4.9.tar.gz`
3. Configure the install: `./configure --prefix=/usr/local/apache --enable-so --enable-cgi --enable-info --enable-rewrite --enable-spelling --enable-usertrack --enable-deflate --enable-ssl --enable-mime-magic`
4. Make `make`
5. Make install `make install`
6. Start Apache. Navigate to `/usr/local/apache/bin` and run `./apachectl start`

You should now have a functioning Apache server

######Key commands from configuration script
`--prefix=/usr/local/apache`: This is where apache will be installed

`--enable-so`: This tells Apache to build `so` modules modules.

####Tip
You can alias the apachectl command so you can start it from anywhere.

1. Navigate to your home directory : `cd ~`
2. Edit the `.bash_aliases` file: `vi .bash_aliases`
3. Make the alias `alias apache="/usr/local/apache/bin/apachectl"`
4. Depending on your environment you may need to alias the sudo command as well so it works with your newly created alias for Apache. Add this line before step 3: `alias su5. do="sudo "`
5. Logout of your terminal and log back in, you can now access apache via `apache <start> <restart> <stop> <status>`
