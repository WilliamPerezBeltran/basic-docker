# Using Volumes with Node.js

This demonstrates how a volume can be used to mount a local directory into a Node.js container.

**Linux, Mac, and WSL on Windows - $(pwd)**

`docker run -d -p 8080:3000 -v $(pwd):/var/www -w "/var/www" node:alpine sh -c "npm install && npm start"`

**PowerShell - ${PWD}**

`docker run -d -p 8080:3000 -v ${PWD}:/var/www -w "/var/www" node:alpine sh -c "npm install && npm start"`

NOTE: You'll need to add quotes around `"$(pwd)"` or `"${PWD}"` if you have a space in the working directory path.



======================================= command explanation =======================================

explicacion de este comando: `docker run -d -p 8080:3000 -v $(pwd):/var/www -w "/var/www" node:alpine sh -c "npm install && npm start"`


Este comando de Docker se utiliza para ejecutar un contenedor basado en la imagen `node:alpine` en segundo plano (`-d`). Aquí hay una explicación de los argumentos y opciones utilizados en este comando:

- `docker run`: Inicia un nuevo contenedor a partir de una imagen.

- `-d`: Ejecuta el contenedor en segundo plano (modo detach).

- `-p 8080:3000`: Asocia el puerto 8080 del host con el puerto 3000 del contenedor. Esto significa que si la aplicación dentro del contenedor escucha en el puerto 3000, podrás acceder a ella desde el host a través del puerto 8080.

- `-v ${PWD}:/var/www`: Monta el directorio actual (`${PWD}`) en el host en el directorio `/var/www` dentro del contenedor. Esto se hace para que los cambios en el código fuente en el host se reflejen dentro del contenedor.

- `-w "/var/www"`: Establece el directorio de trabajo dentro del contenedor en `/var/www`.

- `node:alpine`: La imagen de Docker utilizada para crear el contenedor. En este caso, es la imagen de Node.js basada en Alpine Linux.

- `sh -c "npm install && npm start"`: Esto ejecuta un shell (`sh`) dentro del contenedor y ejecuta los comandos `npm install && npm start`. En este contexto, `npm install` instalará las dependencias del proyecto, y `npm start` iniciará la aplicación.

En resumen, este comando construye y ejecuta un contenedor de Node.js que probablemente sea utilizado para ejecutar una aplicación Node.js. La aplicación se encuentra en el directorio `/var/www` dentro del contenedor, y el código fuente se monta desde el host en ese directorio para facilitar el desarrollo local.
======================================= finish-command explanation =======================================