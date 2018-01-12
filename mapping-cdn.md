  Para acelerar la carga de los archivos PDF de open journal estoy pensando en servirlos a través de un CDN para ello es necesario rescribir la url del link para ser descargado de una ubicación diferente.

* [Primer opcion usar .htaccess para el rewrite en un subdominio](https://stackoverflow.com/questions/3510061/using-htaccess-to-serve-static-files-via-a-subdomain)
* [Usar un segundo subdomain en el mismo servidor]
* Usar CDN para todo el sitio
* Usar Cache solo para los PDF
* [Usar NGINX rewrite para servir los nuevos archivos](http://nginx.org/en/docs/http/ngx_http_rewrite_module.html#rewrite)

Para la redireccion en nginx se puede utilizar
```
location ~ ^/pdf/(.*)\.(jpg|jpeg|test)$ {
rewrite ^/pdf/(.*)\.(jpg|jpeg|test)$ /pdf/image.php?id=$1 break;
}
```
En apache usar un .htaccess requiere usar

* [Servir contenido desde una dominio cookieless](http://www.ravelrumba.com/blog/static-cookieless-domain/)
