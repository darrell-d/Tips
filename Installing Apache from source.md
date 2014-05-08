#Installing Apache from source

#####Configuration script
After extracting the compressed source file configure the installation with this command. This is a good base command for things that will be required
`./configure --prefix=/usr/local/apache --enable-so --enable-cgi --enable-info --enable-rewrite --enable-spelling --enable-usertrack --enable-deflate --enable-ssl --enable-mime-magic`

######Key commands
`--prefix=/usr/local/apache`: This is where apache will be installed

`--enable-so`: This tells Apache to build modules 