# Kasud
> apt-get install php5-common libapache2-mod-php5 php5-cli # php installeerimine
> apt-get install mysql-server php5-mysql # mysql installeerimine
> apt-get install phpmyadmin # installeerib phpmyadmin graafilise keskkonna

# praktikum 4
> openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/apache-selfsigned.key -out /etc/ssl/certs/apache-selfsigned.crt
> nano /etc/apache2/conf-available/ssl-params.conf # kopeerisin sellesse faili sisu
> cp /etc/apache2/sites-available/default-ssl.conf /etc/apache2/sites-available/default-ssl.conf.bak
# default-ssl.conf failis muutsin ServerName oma ip'ks, mis on 172.23.13.46
# 000-default.conf failis lisasin Redirect "/" "https://172.23.13.46/"

# kasutatud käsud
> a2enmod ssl
> a2enmod headers
> a2ensite default-ssl
> a2enconf ssl-params # pidin ssl-params.conf faili ära kustutama hiljem
> apache2ctl configtest
> systemctl restart apache2


