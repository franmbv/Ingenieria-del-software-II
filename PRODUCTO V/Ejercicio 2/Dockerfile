# 1. Imagen base oficial e inmutable de Node.js basada en Alpine Linux
FROM node:18-alpine

# 2. Definir el directorio de trabajo dentro del sistema de archivos aislado del contenedor
WORKDIR /usr/src/app

# 3. Copiar únicamente los manifiestos de dependencias para aprovechar la memoria caché de capas (BuildKit)
COPY package*.json ./

# 4. Instalar las dependencias de forma determinista e inmutable para entorno de producción
RUN npm ci --only=production

# 5. Copiar el resto del código fuente del proyecto (incluyendo server.js)
COPY . .

# 6. Documentar y declarar el puerto de escucha en el que opera la aplicación
EXPOSE 8080

# 7. Comando de ejecución por defecto al iniciar el contenedor
CMD ["node", "server.js"]