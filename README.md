# deployServer
Veremos el procedimiento para subir nuestros progresos de un proyecto symfony a un servidor Ubuntu 16.04 vacío.

# Pasos a seguir dentro del servidor

```
apt-get update
apt-get install tasksel
tasksel
```
*(instala LAMP)*
```
cd /var/www/
git clone "repo" (Clonamos el repo)
chmod 755 -R "repo" (permisos para la cache de symfony)
sudo nano /etc/apache2/sites-available/000-default.conf (Cambiamos la ruta para que coja otra y no la html por defecto)
sudo service apache2 restart (reiniciamos apache)
configuraciones varias para personalizar ~/.bashrc y ~/.gitconfig

sudo apt-get install php libapache2-mod-php php-mcrypt php-mysql (instalamos php para apache)
composer
sudo php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
sudo php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
sudo php composer-setup.php
sudo php -r "unlink('composer-setup.php');"
sudo mv composer.phar /usr/local/bin/composer
sudo composer update (Acabamos finalizando con un update)

Incrementar a 1GB la CPU
sudo apt-get install zip unzip php7.0-zip
composer update
```
