# python-apache-virtualhost
Python and Apache - Virtual Host configuration

Python 3
Apache 2

```
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    ServerName example.com
    AddHandler cgi-script .cgi .py
    DocumentRoot /var/www/example.com/
</VirtualHost>

<IfModule mod_ssl.c>
    <VirtualHost *:443>
    ServerAdmin webmaster@localhost
    ServerName example.com
    AddHandler cgi-script .cgi .py
    DocumentRoot /var/www/example.com/
    SSLEngine on
    SSLCertificateFile /etc/ssl/certs/example.com.pem
    SSLCertificateKeyFile /etc/ssl/private/example.com.key
    </VirtualHost>
</IfModule>

<Directory /var/www/example.com/>
        Options +ExecCGI
        DirectoryIndex index.py
        AllowOverride All
        Order allow,deny
        Allow from all
</Directory>
```
