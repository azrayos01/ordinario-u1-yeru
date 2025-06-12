# Usar imagen base de Node.js
FROM node:18.17.1-alpine

# Crear directorio de trabajo
WORKDIR /usr/src/app

# Copiar archivos de dependencias .json
COPY package*.json ./

# Instalar dependencias con el npm install
RUN npm install

# Copiar todo el código dentro del contenedor
COPY . .

# Exponer puerto 3000
EXPOSE 3000

# Comando para iniciar la aplicación
CMD ["node", "index.js"]