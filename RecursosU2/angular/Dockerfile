# Usar la imagen base de nginx
FROM nginx:stable-alpine

# Crear volumen en /tmp 
VOLUME /tmp

# Eliminar contenido anterior del directorio HTML
RUN rm -rf /usr/share/nginx/html/*

# Copiar archivos de configuración de nginx
COPY nginx.conf /etc/nginx/nginx.conf
COPY mime.types /etc/nginx/mime.types

# Copiar el directorio del frontend Angular ya compilado
COPY sistema-ventas-front /usr/share/nginx/html/

#Exponer el puerto 80
EXPOSE 80

# Ejecutar el contenedor y mantenerlo corriendo
CMD ["nginx", "-g", "daemon off;"]
