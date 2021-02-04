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
  
## 4. Modificar página web por defecto  

Mediante la ruta ` vi /var/www/html/index.nginx-debian.html` modificamos la web por defecto para que nos aparezcala nuestra.  

![web](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/web1modificada.png)  

## 5. Virtual hosting  

  - Crearemos dos sitios virtuales los cuales se llamaran web1 y web2  
  
![Ficheros](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/creardirectoriosweb1y2.png)  

  - Creamos los archivos de configuración de ambas 
  
![Ficheros](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/creararchivoconfweb1y2.png) 

  - Y los configuramos  
  
    - **web1**  
![web1](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/configuracionweb1.png)  

    - **web2**  
    
![web2](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/configuracionweb2.png)  

  - Comprobamos que sea correcta  
  
![web2](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/comprobarconf.png)  

  - Reiniciamos con `systemctl restart nginx.service`  
  
- Para finalizar configuramos los DNS locales para poder entrar  

    - Máquina interna  
    
    ![web2](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/etchosts2.png)  
    
    - Máquina externa  
    
    ![web2](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/etchosts.png)  
    
- Comprobamos que podemos acceder  

![web2](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/comprobacionesweb1y2.png)  

## 6. Autentificación, autorización y control de acceso  

  1. Modificamos la configuración de los sitios virtuales y la añadimos la red para que puedan acceder solo ese ragndo de IP  
  
    - web1  
    
  ![web2](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/acessored2y3.png)  
  
    - web2  
    
  ![web2](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/acessored3web2.png)  
  
  - Reiniciamos con `systemctl restart nginx.service`  
  
  - Comprobamos  
  
     - Máquina interna tiene acceso a ambas  
    
    ![web2](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/maquinainternaweb1y2.png)  
    
    - Máquina externa solo tiene acceso a la web1  
    
    ![web2](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/maquinaexternasinweb2.png)  
    
  2. Creamos un directorio privado  
  
  ![web2](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/directorioprivado.png)  
  
   - Añadimos los usuarios que pueden acceder a ese directorio  
    
   ![web2](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/creamosusuarios.png)  

   - Cambiamos la configuiración de web1 para habilitar la autentifición  
    
   ![web2](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/configurarweb1autentificacion.png)  
    
   - Comprobamos  
   
   ![web2](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/autentificacionweb1.png)  
    
   ![web2](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/autentificacionusuario.png)  
    
   - Cambiamos la configuiración de web1 para habilitar la autentifición de la red externa pero de la interna no  
    
   ![web2](https://github.com/anasalasro/Nginx/blob/main/tareaNginx/configurarweb1autentificacion.png)  
    
    

