---
title: 'Inclusión de una aplicación en un contenedor con Docker: .NET Core'
description: Este tutorial enseña cómo crear una aplicación básica de .NET Core e incluirla en un contenedor con Docker.
ms.date: 10/11/2018
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 8f08936142b0cc44baf268f100e228f68920b69d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126373"
---
# <a name="how-to-containerize-a-net-core-application"></a>Cómo incluir una aplicación de .NET Core en un contenedor

Este tutorial trata sobre las tareas de compilación e implementación de un contenedor de Docker para una aplicación .NET Core. La [plataforma Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) usa el [motor de Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) para compilar y empaquetar aplicaciones rápidamente como [imágenes de Docker](https://docs.docker.com/glossary/?term=image). Estas imágenes se escriben en el formato [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) para implementarse y ejecutarse en un [contenedor superpuesto](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).

Este tutorial ayuda a:

> [!div class="checklist"]
> * Crear un Dockerfile
> * Crear una aplicación .NET Core
> * Implementar la aplicación en un contenedor de Docker

## <a name="net-core-easiest-way-to-get-started"></a>.NET Core: la manera más sencilla de empezar a trabajar

Antes de crear la imagen de Docker, necesita una aplicación que incluir en un contenedor. Puede crearla en Linux, MacOS o Windows. La forma más rápida y sencilla de hacerlo es usar .NET Core.

Si no está familiarizado con el conjunto de herramientas de la CLI de .NET Core, vea la [información general del SDK de .NET Core](../tools/index.md).

Puede compilar contenedores de Windows y Linux con [etiquetas de varias arquitecturas](https://github.com/dotnet/announcements/issues/14).

## <a name="your-first-net-core-docker-app"></a>La primera aplicación de .NET Core Docker

### <a name="prerequisites"></a>Requisitos previos

Para realizar este tutorial:

#### <a name="net-core-sdk"></a>SDK de .NET Core

* Instale el [SDK de .NET Core 2.1](https://www.microsoft.com/net/download) o versiones posteriores.

Vea [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) (.NET Core 2.1: versiones de SO compatibles) para obtener una lista completa de los sistemas operativos compatibles con .NET Core 2.1, las versiones sin soporte del sistema operativo y los vínculos a la directiva de ciclo de vida.

* Instale el editor de código que prefiera si aún no lo ha hecho.

> [!TIP]
> ¿Es necesario instalar un editor de código? Pruebe [Visual Studio Code](https://code.visualstudio.com/download).

#### <a name="installing-docker-client"></a>Instalación del cliente Docker

Instale la versión [Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) o posterior del cliente Docker.

El cliente Docker se puede instalar en:

* Distribuciones de Linux

   * [CentOS](https://docs.docker.com/install/linux/docker-ce/centos/)

   * [Debian](https://docs.docker.com/install/linux/docker-ce/debian/)

   * [Fedora](https://docs.docker.com/install/linux/docker-ce/fedora/)

   * [Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

* [macOS](https://docs.docker.com/docker-for-mac/install/)

* [Windows](https://docs.docker.com/docker-for-windows/install/).

### <a name="create-a-net-core-21-console-app-for-dockerization"></a>Creación de una aplicación de consola de .NET Core 2.1 para incluirla en Docker

Abra un símbolo del sistema y cree una carpeta denominada *Hello*. Vaya a la carpeta que ha creado y escriba los siguientes comandos:

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
   * La etiqueta `TargetFramework` especifica la implementación .NET a la que nos dirigimos. En un escenario avanzado, puede especificar varios marcos de destino y compilar en los especificados en una sola operación. En este tutorial se compila para .NET Core 2.1.

   `Program.cs`:

   `using System` inicia el programa. Esta instrucción significa "llevar cada cosa del espacio de nombres `System` al ámbito de este archivo". El espacio de nombres `System` incluye construcciones básicas, como `string` o tipos numéricos.

   Después, definimos un espacio de nombres denominado `Hello`. Puede cambiar el espacio de nombres por lo que quiera. Se define una clase denominada `Program` dentro del espacio de nombres, con un método `Main` que toma una matriz de cadenas como argumento. Esta matriz contiene la lista de argumentos que se ha pasado cuando se llama al programa compilado. En el ejemplo, el programa solo escribe "¡Hello World!" en la consola.

   **dotnet new** ejecuta el comando [`dotnet restore`](../tools/dotnet-restore.md). **Dotnet restore** restaura el árbol de dependencias con una llamada a [NuGet](https://www.nuget.org/) (administrador de paquetes de .NET).
   NuGet realiza las tareas siguientes:
   * Analiza el archivo *Hello.csproj*.
   * Descarga las dependencias del archivo (o las obtiene de la caché de la máquina).
   * Escribe el archivo *obj/project.assets.json*.

   El archivo *project.assets.json* es un conjunto completo del gráfico de dependencias de NuGet, las resoluciones de enlaces y otros metadatos de la aplicación. Este archivo obligatorio se usa con otras herramientas, como [`dotnet build`](../tools/dotnet-build.md) y [`dotnet run`](../tools/dotnet-run.md), para procesar correctamente el código fuente.

2. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md) llama a [`dotnet build`](../tools/dotnet-build.md) para confirmar una compilación correcta y luego llama a `dotnet <assembly.dll>` para ejecutar la aplicación.

    ```console
    $ dotnet run

    Hello World!
    ```

    En escenarios avanzados, vea [Implementación de aplicaciones .NET Core](../deploying/index.md) para obtener detalles.

## <a name="dockerize-the-net-core-application"></a>Aplicar Docker a la aplicación .NET Core

La aplicación de consola Hello de .NET Core se ejecuta correctamente en local. El siguiente paso es compilar y ejecutar la aplicación en Docker.

### <a name="your-first-dockerfile"></a>El primer Dockerfile

Abra el editor de texto para empezar. Todavía no está trabajando desde el directorio Hello en que se ha compilado la aplicación.

Agregue las siguientes instrucciones de Docker para cada [contenedor de Windows o Linux](https://docs.microsoft.com/virtualization/windowscontainers/about/) a un archivo nuevo. Cuando termine, guárdelo en la raíz del directorio Hello como **Dockerfile**, sin extensión (puede que necesite establecer el tipo de archivo en `All types (*.*)` o similar).

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
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

La primera instrucción debe ser [**FROM**](https://docs.docker.com/engine/reference/builder/#from). Esta instrucción inicializa una nueva fase de compilación y establece la imagen base para las instrucciones restantes. Las etiquetas de varias arquitecturas extraen contenedores de Windows o Linux según [el modo de contenedor](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers) de Docker para Windows. La imagen base del ejemplo es la imagen 2.1-sdk del repositorio microsoft/dotnet.

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
```

La instrucción [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) establece el directorio de trabajo de cualquier instrucción RUN, CMD, ENTRYPOINT, COPY y ADD Dockerfile. Si el directorio no existe, se crea. En este caso, WORKDIR se establece en el directorio de la aplicación.

```Dockerfile
WORKDIR /app
```

La instrucción [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) copia nuevos archivos o directorios de la ruta de acceso de origen y los agrega al sistema de archivos del contenedor de destino. Con esta instrucción, se copia el archivo de proyecto de C# en el contenedor.

```Dockerfile
COPY *.csproj ./
```

La instrucción [**RUN**](https://docs.docker.com/engine/reference/builder/#run) ejecuta los comandos en una nueva capa sobre la imagen actual y confirma los resultados. La imagen resultante confirmada se usa para el siguiente paso en el Dockerfile. Se está ejecutando **dotnet restore** para obtener las dependencias necesarias del archivo de proyecto de C#. 

```Dockerfile
RUN dotnet restore
```

Esta instrucción **COPY** copia el resto de los archivos en el contenedor en nuevas [capas](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).

```Dockerfile
COPY . ./
```

Se está publicando la aplicación con esta instrucción **RUN**. El comando [**dotnet publish**](../tools/dotnet-publish.md) compila la aplicación, lee sus dependencias especificadas en el archivo de proyecto y publica el conjunto resultante de archivos en un directorio. La aplicación se publica con una configuración de **versión** y se escribe en el directorio predeterminado.

```Dockerfile
RUN dotnet publish -c Release -o out
```

La instrucción [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) permite al contenedor ejecutarse como un archivo ejecutable.

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

Ya tiene un Dockerfile que:

* copia la aplicación en la imagen
* copia las dependencias de la aplicación en la imagen
* compila la aplicación para que se ejecute como un archivo ejecutable

### <a name="build-and-run-the-hello-net-core-app"></a>Compilación y ejecución de la aplicación Hello de .NET Core

#### <a name="essential-docker-commands"></a>Comandos de Docker esenciales

Estos comandos de Docker son esenciales:

* [docker build](https://docs.docker.com/engine/reference/commandline/build/)
* [docker run](https://docs.docker.com/engine/reference/commandline/run/)
* [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
* [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
* [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
* [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
* [docker image](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a>Compilar y ejecutar

Ha escrito el Dockerfile; ahora Docker compila la aplicación y luego ejecuta el contenedor.

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

La salida del comando `docker build` debe ser similar a la siguiente salida de consola:

```console
Sending build context to Docker daemon   173.1kB
Step 1/7 : FROM microsoft/dotnet:2.1-sdk
 ---> 288f8c45f7c2
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
Successfully built 46db075bd98d
Successfully tagged dotnetapp-dev:latest
```

Como puede ver en la salida, el motor de Docker ha usado el Dockerfile para compilar el contenedor.

La salida del comando `docker run` debe ser similar a la siguiente salida de consola:

```console
Hello World!
```

¡Enhorabuena! Acaba de:
> [!div class="checklist"]
> * Crear una aplicación .NET Core local
> * Crear un Dockerfile para compilar el primer contenedor
> * Compilar y ejecutar la aplicación a la que se ha aplicado Docker

## <a name="next-steps"></a>Pasos siguientes

Estos son algunos de los pasos que puede realizar a continuación:

* [Introducción a vídeo e imágenes de .NET Docker](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [Instancias de Visual Studio, Docker y Azure Container juntas](https://medium.com/@AliMazaheri/visual-studio-docker-azure-container-instances-better-together-bf8c2f0419ae)
* [Docker para tutoriales rápidos de Azure](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [Implementar la aplicación en Docker para Azure](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> Si no tiene una suscripción de Azure, [regístrese hoy](https://azure.microsoft.com/free/?b=16.48) para obtener una cuenta gratuita durante 30 días y obtenga 200 dólares en créditos de Azure para probar cualquier combinación de servicios de Azure.

## <a name="docker-images-used-in-this-sample"></a>Imágenes de Docker usadas en este ejemplo

En este ejemplo se usan las siguientes imágenes de Docker

* [`microsoft/dotnet:2.1-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a>Recursos relacionados

* [Ejemplos de .NET Core Docker](https://github.com/dotnet/dotnet-docker/tree/master/samples)
* [Dockerfile en contenedores de Windows](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [Ejemplos de .NET Framework Docker](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [ASP.NET Core en DockerHub](https://hub.docker.com/r/microsoft/aspnetcore/)
* [Aplicar Docker a una aplicación .NET Core: Tutorial de Docker](https://docs.docker.com/engine/examples/dotnetcore/)
* [Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker) (Trabajo con Visual Studio Docker Tools)
* [Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Implementación de imágenes de Docker desde Azure Container Registry a Azure Container Instances)