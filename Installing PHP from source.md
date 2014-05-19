#Installing PHP from source

###Pre-requisites:
libxml : `apt-get install libxml2-dev`

###Installation
1. Download the source files: `wget http://downloads.php.net/tyrael/php-5.6.0beta3.tar.gz`
2. Extract source files : `tar -zxvf php-5.6.0beta3.tar.gz`
3. Configure the install: `./configure --with-pear=/usr/share/php --with-bz2 --with-curl --with-gd --enable-calendar --enable-mbstring --enable-bcmath --enable-sockets --with-regex=php --with-zlib --with-regex=php --with-zlib --with-mysql --with-mysqli --with-apxs2=/usr/local/apache/bin/apxs`
4. Make `make`
5. Make install `make install`

######Key commands
`--with-apxs2=/usr/local/apache/bin/apxs`: This enables PHP to create libphp5.so. This mod is required so that Apache can rung PHP files. 

###Congfiguration with Apache

Next PHP needs to be configured with Apache.

1. Navigate to `/usr/local/apache/conf` (or wherever your local Apache install is)
2. Open httpd.conf with your preferred editor. For example `vi httpd.conf` or `gedit httpd.conf`
3. Set the `Directory Index` to `index.php index.html` This makes `index.php` the default file loaded, then if `index.php` is missing `index.html` is loaded
4. Add `AddType application/x-httpd-php .php`
5. Ensure the libphp5.so module is loaded: `LoadModule php5_module        modules/libphp5.so`
6. Set the Handler for PHP files:

    `<FilesMatch \.php$>`

    `SetHandler application/x-httpd-php`
    
    `</FilesMatch>` 
    
7. Restart Apache