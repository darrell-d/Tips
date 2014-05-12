#Installing PHP from source

#####Configuration script
After extracting the compressed source file configure the installation with this command. This is a good base command for things that will be required
`  ./configure --with-pear=/usr/share/php --with-bz2 --with-curl --with-gd --enable-calendar --enable-mbstring --enable-bcmath --enable-sockets --with-libxml-dir=/usr  --with-regex=php --with-zlib --with-regex=php --with-zlib --with-mysql --with-mysqli --with-apxs2=/usr/local/apache/bin/apxs`


######Key commands
`--with-apxs2=/usr/local/apache/bin/apxs`: This enables PHP to create libphp5.so. This mod is required so that Apache can rung PHP files. 