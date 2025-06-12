#TODO: Usar node
FROM node:18.17.1-alpine

#TODO: Crear un volumen /usr/src/app
VOLUME /usr/src/app

# TODO: Copiar al archivo package.json y package-look.json
COPY package*.json ./

# TODO: Ejecutar npm install
RUN npm install

# TODO: Copiar el contenido al contenedor
COPY . .

# TODO: Exponer el puerto 3000
EXPOSE 3000

# TODO: Ejecutar CMD ["node", "index.js"]
CMD ["node", "index.js"]
