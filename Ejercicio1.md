# Ejercicio 1
Para instalar el apache usaremos este comando
```bash
sudo apt install apache2
```
Una vez instalado el apache crearemos un directorio en esta ruta (/var/www/),en nuestro caso tendremos que hacer dos centro.intranet y departamentos.centro.intranet: 
```bash
sudo mkdir /var/www/centro.intranet
sudo mkdir /var/www/departamentos.centro.intranet
```
Una vez creado los directorios crearemos un archivo .conf en (/etc/apache2/sites-available/)

Se creara con este comando:
```bash
sudo nano /etc/apache2/sites-available/centro.intranet
sudo nano /etc/apache2/sites-available/departamentos.centro.intranet
```
Dentro de cada uno de los archvivos .conf pondremos esto
- Centro:
```bash
<VirtualHost *:80>
    ServerName centro.intranet
    ServerAlias www.centro.intranet
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/centro.intranet
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```
- Departamentos:
```bash
<VirtualHost *:80>
    ServerName departamentos.centro.intranet
    ServerAlias www.departamentos.centro.intranet
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/departamentos.centro.intranet
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```
Ahora para habilitar los host virtuales pondremos este comando:
```bash
sudo a2ensite departamentos.centro.intranet
sudo a2ensite centro.intranet
```
Ahora si recargamos el apache con este comando:
```bash
sudo systemctl reload apache2
```
Si ponemos un index.html apache nos lo ejecutara automaticamente pero como vamos a mostrar en uno wordpress y en el otro python ya veremos como funciona cuando los instalemos y los introduzcamos.
