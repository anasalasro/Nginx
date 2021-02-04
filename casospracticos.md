# CASOS PRACTICOS  

## 1. Versión de Nginx instalada  

![Versión](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/version.png)  

## 2. Servicios asociados
- Habilitar el servicio  

```systemctl enable nginx```

- Deshabilitar el servicio  

```systemctl disable nginx```

- Iniciar el servicio  

```systemctl start nginx```

- Ver el estado en el que se encuentra  

`systemctl status nginx`

## 3. Ficheros de configuración
En **/etc/nginx** encontraremos los ficheros de configuración
![Ficheros](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/ficherosconf.png)  
  - El fichero principal es: `/etc/nginx/nginx.conf`
  - Los sitios virtuales se guardan en: `/etc/nginx/sites-available`
  - Los LOGS se guardan en: `/var/log/nginx`
