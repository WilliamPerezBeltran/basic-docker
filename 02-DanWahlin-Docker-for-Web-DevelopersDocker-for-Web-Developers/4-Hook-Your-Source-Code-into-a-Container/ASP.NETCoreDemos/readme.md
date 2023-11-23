# Using Volumes with ASP.NET Core

This demonstrates how a volume can be used to mount a local directory into an ASP.NET Core container.

**Linux, Mac, and WSL on Windows - $(pwd)**

`docker run -d -p 8080:5063 -v $(pwd):/var/www -w "/var/www" mcr.microsoft.com/dotnet/sdk bash -c "dotnet watch run"`


**PowerShell - ${PWD}**

`docker run -d -p 8080:5063 -v ${PWD}:/var/www -w "/var/www" mcr.microsoft.com/dotnet/sdk bash -c "dotnet watch run"`

NOTE: You'll need to add quotes around `"$(pwd)"` or `"${PWD}"` if you have a space in the working directory path.






================= Command explination ================= 

```bash
docker run -d -p 8080:5063 -v $(pwd):/var/www -w "/var/www" mcr.microsoft.com/dotnet/sdk bash -c "dotnet watch run"
```

Aquí está la desglose del comando:

- `docker run`: Este comando se utiliza para ejecutar un contenedor a partir de una imagen.

- `-d`: Inicia el contenedor en segundo plano (modo detach).

- `-p 8080:5063`: Asocia el puerto 8080 del host con el puerto 5063 del contenedor. Esto significa que si la aplicación dentro del contenedor escucha en el puerto 5063, podrás acceder a ella desde el host a través del puerto 8080.

- `-v $(pwd):/var/www`: Monta el directorio actual (`$(pwd)`) en el host en el directorio `/var/www` dentro del contenedor. Esto se hace para que los cambios en el código fuente en el host se reflejen dentro del contenedor.

- `-w "/var/www"`: Establece el directorio de trabajo dentro del contenedor en `/var/www`.

- `mcr.microsoft.com/dotnet/sdk`: La imagen de Docker utilizada para crear el contenedor. En este caso, es la imagen SDK de .NET de Microsoft.

- `bash -c "dotnet watch run"`: Esto ejecuta un shell (`bash`) dentro del contenedor y ejecuta el comando `dotnet watch run`. La herramienta `dotnet watch` es utilizada comúnmente en el desarrollo de aplicaciones .NET para reiniciar automáticamente la aplicación cuando se detectan cambios en el código fuente.

En resumen, este comando Docker ejecuta un contenedor basado en la imagen SDK de .NET, monta el directorio actual en el contenedor, establece el directorio de trabajo y luego ejecuta `dotnet watch run` para iniciar una aplicación .NET y observar cambios en el código fuente.
================= end-Command explination ================= 








================= Command explination ================= 
Certainly! Here's an explanation of the Docker command you provided:

```bash
docker run -d -p 8080:5063 -v $(pwd):/var/www -w "/var/www" mcr.microsoft.com/dotnet/sdk bash -c "dotnet watch run"
```

Breaking down the command:

- `docker run`: This command is used to run a container based on an image.

- `-d`: Runs the container in the background (detach mode).

- `-p 8080:5063`: Maps port 8080 on the host to port 5063 on the container. This means that if the application inside the container is listening on port 5063, you can access it from the host through port 8080.

- `-v $(pwd):/var/www`: Mounts the current directory (`$(pwd)`) on the host to the `/var/www` directory inside the container. This is done to reflect changes in the source code on the host inside the container.

- `-w "/var/www"`: Sets the working directory inside the container to `/var/www`.

- `mcr.microsoft.com/dotnet/sdk`: The Docker image used to create the container. In this case, it's the .NET SDK image from Microsoft.

- `bash -c "dotnet watch run"`: This runs a shell (`bash`) inside the container and executes the command `dotnet watch run`. The `dotnet watch` tool is commonly used in .NET application development to automatically restart the application when changes in the source code are detected.

In summary, this Docker command runs a container based on the Microsoft .NET SDK image, mounts the current directory into the container, sets the working directory, and then executes `dotnet watch run` to start a .NET application and watch for changes in the source code.
================= end-Command explination ================= 





