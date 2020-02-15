# Instalar Magento en Ubuntu

1- Actualizamos el Sistema
``` 
apt-get update
```

2- Instalamos Apache 2.4 y configuramos su modo rewrite
``` 
apt-get -y install apache2
a2enmod rewrite
service apache2 restart
```

3- Mysql
``` 
curl -OL https://dev.mysql.com/get/mysql-apt-config_0.8.12-1_all.deb
sudo dpkg -i mysql-apt-config*
sudo apt update
sudo apt install mysql-server -y
``` 

4 - Configurando MYSQL
``` 
mysql_secure_installation
n
y
y
y
``` 

5 - Configuramos el límite de memoria de Apache
``` 
nano /etc/php/7.0/apache2/php.ini
memory_limit = 512M
``` 

6 - Revsiamos la version de Apache
``` 
apache2 -v
``` 

7 - Creamos la bd en mysql
``` 
mysql -h localhost -u root  -p
CREATE DATABASE magento;
CREATE USER 'magento' IDENTIFIED BY 'A%123Negocios';
GRANT ALL PRIVILEGES ON magento.* TO 'magento';
quit
``` 
