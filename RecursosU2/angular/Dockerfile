# Usar la imagen base de nginx
FROM nginx:stable-alpine

# Crear volumen en /tmp (corrección: no /temp como decía el enunciado)
VOLUME /tmp

# Eliminar contenido anterior del directorio HTML
RUN rm -rf /usr/share/nginx/html/*

# Copiar archivos de configuración de nginx
COPY nginx.conf /etc/nginx/nginx.conf
COPY mime.types /etc/nginx/mime.types

# Copiar el directorio del frontend Angular ya compilado
COPY sistema-ventas-front/ /usr/share/nginx/html/

# Exponer puerto 80
EXPOSE 80

# Comando para mantener nginx en ejecución en primer plano
CMD [ "nginx", "-g", "daemon off;" ]
