---
title: "Obtenga información acerca de los aspectos básicos de Docker con .NET Core"
description: "Un Docker y el Tutorial básico de .NET Core"
keywords: . NET, .NET core, Docker, Tutorial
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.custom: mvc
manager: wpickett
ms.openlocfilehash: 5935f67d7e4ca9c9e8768373e2bcaa9febccfdc5
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2017
---
# <a name="learn-docker-basics-with-net-core"></a>Obtenga información acerca de los aspectos básicos de Docker con .NET Core

Este tutorial enseña el contenedor compilar e implementar tareas para una aplicación de .NET Core de Docker. En el transcurso de este tutorial, aprenderá:

> [!div class="checklist"]
> * Cómo crear un archivo Dockerfile
> * Cómo crear una aplicación de .NET Core.
> * Cómo implementar la aplicación en un contenedor de Docker.

El [plataforma Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) utiliza la [motor de Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) para generar y empaquetar aplicaciones como rápidamente [imágenes de Docker](https://docs.docker.com/glossary/?term=image). Estas imágenes se escriben el [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) formato para implementar y ejecutar un [superpuesto contenedor](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).

## <a name="net-core-easiest-way-to-get-started"></a>.NET core: De manera más fácil para empezar a trabajar

Antes de crear la imagen de Docker, se necesita una aplicación que incluya. Puede crearla en Linux, Mac OS o Windows. La forma más rápida y sencilla de hacerlo es usar .NET Core.

Si no está familiarizado con el conjunto de herramientas de la CLI de .NET Core, vea la [información general del SDK de .NET Core](../tools/index.md).

Puede crear contenedores de Windows y Linux con [arch múltiples según etiquetas](https://github.com/dotnet/announcements/issues/14).

## <a name="your-first-net-core-docker-app"></a>La primera aplicación de .NET Core Docker

### <a name="prerequisites"></a>Requisitos previos

Para completar este tutorial:

#### <a name="net-core-20-sdk"></a>.NET core SDK 2.0

* Instalar [.NET Core SDK 2.0](https://www.microsoft.com/net/core).

Vea [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 2.x, fuera de las versiones de sistema operativo compatibles y los vínculos de directiva de ciclo de vida.

* Instale al editor de código favoritos, si no lo ha hecho ya.

> [!TIP]
> ¿Es necesario instalar a un editor de código? Intente [Visual Studio](https://visualstudio.com/downloads)!

#### <a name="installing-docker-client"></a>Instalación de cliente de Docker

Instalar [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) u otra posterior del cliente.

El cliente se puede instalar en:

* Distribuciones de Linux

   * [CentOS](https://www.docker.com/docker-centos-distribution)

   * [Debian](https://www.docker.com/docker-debian)

   * [Fedora](https://www.docker.com/docker-fedora)

   * [Ubuntu](https://www.docker.com/docker-ubuntu)

* [macOS](https://docs.docker.com/docker-for-mac/)

* [Windows](https://docs.docker.com/docker-for-windows/).

### <a name="create-a-net-core-20-console-app-for-dockerization"></a>Crear una aplicación de consola .NET Core 2.0 para Dockerization

Abra un símbolo del sistema y cree una carpeta denominada *Hello*. Navegue hasta la carpeta que creó y escriba los siguientes comandos:

```console
dotnet new console
dotnet run
```

Veamos un tutorial rápido:

1. `$ dotnet new console`

   [`dotnet new`](../tools/dotnet-new.md) crea un archivo de proyecto `Hello.csproj` actualizado con las dependencias necesarias para compilar una aplicación de consola.  Además, se crea un archivo `Program.cs`, un archivo básico que contiene el punto de entrada para la aplicación.
   
   `Hello.csproj`:

   El archivo de proyecto especifica todo lo que es necesario para restaurar las dependencias y compilar el programa.

   * La etiqueta `OutputType` especifica que estamos creando un archivo ejecutable, es decir, una aplicación de consola.
   * La etiqueta `TargetFramework` especifica la implementación .NET a la que nos dirigimos. En un escenario más avanzado, puede especificar varios marcos de trabajo de destino y la compilación en los marcos de trabajo especificados en una sola operación. En este tutorial, se compila para .NET Core 2.0.

   `Program.cs`:

   Inicia el programa por `using System`. Esta instrucción significa, "poner todo el `System` espacio de nombres en el ámbito de este archivo." El espacio de nombres `System` incluye construcciones básicas, como `string` o tipos numéricos.

   Después, definimos un espacio de nombres denominado `Hello`. Puede cambiar el espacio de nombres para el que desee. Se define una clase denominada `Program` dentro del espacio de nombres, con un método `Main` que toma una matriz de cadenas como argumento. Esta matriz contiene la lista de argumentos que se ha pasado cuando se llama al programa compilado. En nuestro ejemplo, el programa escribe sólo "¡Hello World!" en la consola.

2. `$ dotnet restore`

   En .NET Core 2.x, **dotnet nueva** se ejecuta la [ `dotnet restore` ](../tools/dotnet-restore.md) comando. **Restauración de dotnet** restaura el árbol de dependencias con un [NuGet](https://www.nuget.org/)llamada (Administrador de paquetes. NET).
   NuGet lleva a cabo las siguientes tareas:
   * analiza la *Hello.csproj* archivo 
   * descarga el archivo de dependencias (o grabs desde la caché del equipo)
   * Escribe el *obj/project.assets.json* archivo

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   El *project.assets.json* archivo es un conjunto completo del gráfico de dependencias de NuGet, resoluciones de enlace y otros metadatos de la aplicación. Esto requiere el archivo se usa con otras herramientas, como [ `dotnet build` ](../tools/dotnet-build.md) y [ `dotnet run` ](../tools/dotnet-run.md), para que procese correctamente el código fuente.
   
3. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md)llamadas [ `dotnet build` ](../tools/dotnet-build.md) para confirmar una compilación correcta y, a continuación, llama `dotnet <assembly.dll>` para ejecutar la aplicación.
   
    ```console
    $ dotnet run
    
    Hello World!
    ```

    Para escenarios avanzados, consulte [implementación de aplicaciones de .NET Core](../deploying/index.md) para obtener más información.

## <a name="dockerize-the-net-core-application"></a>Dockerize la aplicación de .NET Core

La aplicación de consola de Hello .NET Core correctamente se ejecuta localmente. Ahora vamos a dar un paso más y compilar y ejecutar la aplicación en Docker.

### <a name="your-first-dockerfile"></a>El primer Dockerfile

¡Abra el editor de texto y Comencemos! Todavía estamos trabajando desde el directorio de Hello en que creamos la aplicación.

Agregue las siguientes instrucciones de Docker para cualquier Linux o [contenedores de Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) en un archivo nuevo. Cuando termine, puede guardarlo en la raíz del directorio Hello como **Dockerfile**, sin extensión (puede que necesite establecer el tipo de archivo `All types (*.*)` o algo similar).

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

El Dockerfile contiene las instrucciones de compilación de Docker que se ejecutan secuencialmente.

Debe ser la primera instrucción [ **FROM**](https://docs.docker.com/engine/reference/builder/#from). Esta instrucción Inicializa una nueva fase de compilación y establece la imagen Base para las instrucciones restantes. Las etiquetas arch varios contenedores de Windows o Linux de extracción según la Docker para Windows [el modo de contenedor](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers). La imagen Base para nuestro ejemplo es la 2.0 sdk desde el repositorio de microsoft/dotnet

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
```

El [ **WORKDIR** ](https://docs.docker.com/engine/reference/builder/#workdir) instrucción establece el directorio de trabajo para cualquier ejecución, CMD, ENTRYPOINT, copiar y agregar Dockerfile restantes instrucciones. Si el directorio no existe, se crea. En este caso, WORKDIR se establece en el directorio de aplicación.

```Dockerfile
WORKDIR /app
```

El [ **copia** ](https://docs.docker.com/engine/reference/builder/#copy) instrucción copia nuevos archivos o directorios de la ruta de acceso de origen y los agrega al sistema de archivos del contenedor de destino. Con esta instrucción, que estamos copiando el archivo de proyecto de C# para el contenedor.

```Dockerfile
COPY *.csproj ./
```

El [ **ejecutar** ](https://docs.docker.com/engine/reference/builder/#run) instrucción ejecuta los comandos en una nueva capa encima de la imagen actual y confirmar los resultados. La imagen resultante confirmada se usa para el siguiente paso en el Dockerfile. Se está ejecutando **dotnet restauración** para obtener las dependencias necesarias del archivo de proyecto de C#. 

```Dockerfile
RUN dotnet restore
```

Esto **copia** instrucción copia el resto de los archivos en el contenedor en nuevos [capas](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).

```Dockerfile
COPY . ./
```

Estamos publicando la aplicación con esta **ejecutar** instrucción. El [ **publicar dotnet** ](../tools/dotnet-publish.md) comando compila la aplicación, lee a través de sus dependencias especificados en el archivo de proyecto y publica el conjunto resultante de archivos en un directorio. Nuestra aplicación se publica con un **versión** configuración y se escribe en el directorio predeterminado.

```Dockerfile
RUN dotnet publish -c Release -o out
```

El [ **ENTRYPOINT** ](https://docs.docker.com/engine/reference/builder/#entrypoint) instrucción permite al contenedor para que se ejecute como un ejecutable.

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

Ahora ya tiene un archivo Dockerfile que:

* copia la aplicación a la imagen
* dependencias de la aplicación a la imagen
* compila la aplicación para que se ejecute como un ejecutable

### <a name="build-and-run-the-hello-net-core-20-app"></a>Compilar y ejecutar la aplicación Hello .NET Core 2.0

#### <a name="essential-docker-commands"></a>Comandos de Docker esenciales

Estos comandos de Docker son esenciales:

* [compilación de docker](https://docs.docker.com/engine/reference/commandline/build/)
* [ejecución de docker](https://docs.docker.com/engine/reference/commandline/run/)
* [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
* [detención de docker](https://docs.docker.com/engine/reference/commandline/stop/)
* [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
* [rmi docker](https://docs.docker.com/engine/reference/commandline/rmi/)
* [imagen de docker](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a>Compilar y ejecutar

Escribió el dockerfile; Ahora Docker compila una aplicación y, a continuación, ejecuta el contenedor.

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

La salida de la `docker build` comando debe ser similar a la siguiente salida de consola:

```console
Sending build context to Docker daemon   72.7kB
Step 1/7 : FROM microsoft/dotnet:2.0-sdk
 ---> d84f64b126a6
Step 2/7 : WORKDIR /app
 ---> Using cache
 ---> 9af1fbdc7972
Step 3/7 : COPY *.csproj ./
 ---> Using cache
 ---> 86c8c332d4b3
Step 4/7 : RUN dotnet restore
 ---> Using cache
 ---> 86fcd7dd0ea4
Step 5/7 : COPY . ./
 ---> Using cache
 ---> 6faf0a53607f
Step 6/7 : RUN dotnet publish -c Release -o out
 ---> Using cache
 ---> f972328318c8
Step 7/7 : ENTRYPOINT dotnet out/Hello.dll
 ---> Using cache
 ---> 53c337887e18
Successfully built 53c337887e18
Successfully tagged dotnetapp-dev:latest
```

Como puede ver en el resultado, el motor de Docker usan el Dockerfile para crear el contenedor.

La salida de la `docker run` comando debe ser similar a la siguiente salida de consola:

```console
Hello World!
```

¡Enhorabuena! simplemente deberá:
> [!div class="checklist"]
> * Crea una aplicación de .NET Core local
> * Crea un archivo Dockerfile para crear el primer contenedor
> * Compila y se ejecutó la aplicación Dockerized



## <a name="next-steps"></a>Pasos siguientes

Aquí le mostramos algunos procedimientos que puede realizar:

* [Introducción a .NET Docker imágenes vídeo](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [Visual Studio, Docker & instancias de contenedor de Azure mejor juntos.](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)
* [Docker para tutoriales rápidos de Azure](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [Implementar la aplicación en Docker de Azure](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> Si no tiene una suscripción de Azure, [Regístrese hoy](https://azure.microsoft.com/free/?b=16.48) para una cuenta gratuita de 30 días y get 200 dólares en créditos de Azure para probar cualquier combinación de los servicios de Azure.

## <a name="docker-images-used-in-this-sample"></a>Imágenes de docker que se utilizan en este ejemplo

Las siguientes imágenes de Docker se usan en este ejemplo

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a>Recursos relacionados

* [Ejemplos de .NET core Docker](https://github.com/dotnet/dotnet-docker-samples/README.md)
* [Dockerfile en contenedores de Windows](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [Ejemplos de .NET framework Docker](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [Núcleo de ASP.NET en DockerHub](https://hub.docker.com/r/microsoft/aspnetcore/)
* [Dockerize una aplicación de .NET Core - Tutorial de Docker](https://docs.docker.com/engine/examples/dotnetcore/)
* [Trabajar con herramientas de Docker de Visual Studio](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Implementación de imágenes de Docker desde el registro de contenedor de Azure a las instancias de contenedor de Azure](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)