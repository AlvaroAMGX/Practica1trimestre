Empezaremos instalando Nginx

```bash
sudo apt install nginx
```
Vamos a habilitar el servicio de Nginx HTTP

```bash
sudo ufw allow 'Nginx HTTP'
```

- Y ya tendremos el servidor activo, pero para poder visualizarlo correctamente, deberemos cambiar el puerto del servidor ya que por defecto viene el 80 y nos dara problemas con apache

```bash
sudo nano /etc/nginx/sites-available/default
```

Vamos a cambiar el número de puerto de estas dos lineas:

```bash
server {
        listen 8080 default_server;
        listen [::]:8080 default_server;
```

![]

Guardamos el archivo y reiniciamos el servicio de nginx
```bash
sudo service nginx restart
```

Y para ver si funciono pondremos localhost:8080 y nos saldra el index por defecto de nginx:
![]
