# Getting SSL Certificate with certbot

## Getting the certificates
* Use sudo as necessary

        `apt-install certbot`

        `certbot certonly --webroot`

* Follow terms, enter domain

* When asked for web root enter apache (or other webserver) root on server machine. For example for apache : `var/www/html`

* Find certs at path (/etc/letsencrypt/live/<domain>)

## Installing to apache
* Assuming `apache2` and `apache2-dev`

* Ensure mod_ssl is intalled and enabled

        `a2enmod ssl`

* Find the <VirtualHost*:443> statement or create it

* See vHost config:

        <VirtualHost *:443>
            ServerName rewards.slucards.com
            Alias /static /code/static/
            DocumentRoot /code/slucards
            <Directory /code/static/>
                Require all granted
            </Directory>

            <Directory /code/slucards>
                <Files wsgi.py>
                    Require all granted
                </Files>
            </Directory>


            WSGIScriptAlias / /code/slucards/wsgi.py
            # WSGIPythonPath /code
            WSGIScriptReloading On

            ErrorLog ${APACHE_LOG_DIR}/error.log
            CustomLog ${APACHE_LOG_DIR}/access.log combined

            SSLEngine on
            SSLCertificateFile "/code/letsencrypt/live/rewards.slucards.com/fullchain.pem"
            SSLCertificateKeyFile "/code/letsencrypt/live/rewards.slucards.com/privkey.pem"

        </VirtualHost>
