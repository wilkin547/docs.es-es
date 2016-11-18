---
title: Migrar aplicaciones de ASP.NET MVC a contenedores de Windows
description: "Aprenda a ejecutar una aplicación existente de ASP.NET MVC en un contenedor de Docker de Windows"
keywords: Contenedores de Windows, Docker, ASP.NET MVC
author: BillWagner
manager: wpickett
ms.date: 09/28/2016
ms.topic: article
ms.prod: .net-framework-4.6
ms.technology: dotnet-mvc
ms.devlang: dotnet
ms.assetid: c9f1d52c-b4bd-4b5d-b7f9-8f9ceaf778c4
translationtype: Human Translation
ms.sourcegitcommit: 15c55a87beb64f265a164db918c7721c7690fadf
ms.openlocfilehash: 3e8a8a953cbb3dde6ddf386f8c3b3a1fd4c549f1

---

# <a name="migrating-aspnet-mvc-applications-to-windows-containers"></a>Migrar aplicaciones de ASP.NET MVC a contenedores de Windows

Ejecutar una aplicación existente basada en .NET Framework en un contenedor de Windows requiere la creación de la imagen de Docker que contiene la aplicación e iniciar uno o varios contenedores para ejecutar esa imagen. En este tema, se explican las tareas que debe realizar para tomar una [aplicación ASP.NET MVC](http://www.asp.net/mvc) existente e implementarla en un contenedor de Windows.

Comenzará con una aplicación de ASP.NET MVC existente. Después, compilará los recursos publicados mediante Visual Studio. Usará Docker para crear la imagen que contiene la aplicación y que la ejecuta cuando se inicia. Cuando haya terminado, puede conectar un explorador con el sitio que se ejecuta en un contenedor de Windows y comprobar que se ejecuta la aplicación.

En este artículo, se supone un conocimiento básico de Docker. Puede obtener más información sobre la arquitectura de Docker si lee [Docker Overview (Introducción a Docker)](https://docs.docker.com/engine/understanding-docker/) en el sitio de Docker, si estos conceptos son nuevos para usted.

La aplicación que ejecutará en un contenedor es un sitio web sencillo que responde a preguntas de forma aleatoria. Esta aplicación es una aplicación MVC básica sin compatibilidad de autenticación ni almacenamiento de base de datos, lo que le permite centrarse en mover la capa web a un contenedor. En temas futuros, se le mostrará cómo mover y administrar el almacenamiento persistente en aplicaciones en contenedor.

Al mover la aplicación, se incluyen los siguientes pasos:

1. [Crear una tarea de publicación para crear los recursos de una imagen.](#publish-script)
2. [Crear una imagen de Docker que ejecutará la aplicación.](#build-the-image)
3. [Iniciar un contenedor de Docker que ejecuta la imagen.](#start-a-container)
4. [Comprobar la aplicación mediante el explorador.](#verify-in-the-browser)

La aplicación finalizada se encuentra en el [repositorio dotnet/core-docs en GitHub](https://github.com/dotnet/docs/tree/master/samples/framework/docker/MVCRandomAnswerGenerator).

## <a name="prerequisites"></a>Requisitos previos

Como mínimo, el equipo de desarrollo debe ejecutar la [actualización de aniversario de Windows 10](https://www.microsoft.com/en-us/software-download/windows10/) o [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server). 

Antes de comenzar, tiene que instalar [Docker para Windows](https://docs.docker.com/docker-for-windows/), versión 1.12 Beta 26 o una versión más reciente. La compatibilidad con el contenedor de Windows solo está disponible en el canal Beta en este momento.

> [!IMPORTANT]
> Si usa Windows Server 2016, deberá seguir las instrucciones de [Implementación de host de contenedor - Windows Server](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/deployment/deployment) para poder ejecutar contenedores de Docker.

Después de instalar e iniciar Docker, debe hacer clic con el botón derecho en el icono de bandeja y seleccionar **Cambiar a contenedores de Windows** para poder ejecutar imágenes de Docker basadas en Windows. Este comando tarda algunos segundos en ejecutarse:

![Contenedor de Windows][windows-container]

## <a name="publish-script"></a>Publicar script

El primer paso es reunir en un mismo lugar todos los recursos que necesita cargar en una imagen de Docker. Afortunadamente, puede usar el comando **Publicar** de Visual Studio para crear un perfil de publicación para la aplicación. Este perfil incluirá todos los recursos en un árbol de directorio que copiará en la imagen de destino más adelante en este tutorial.

**Pasos de publicación**

1. Haga clic con el botón derecho en el proyecto web en Visual Studio y seleccione **Publicar**.
2. Haga clic en el **botón Perfil personalizado y después seleccione **Sistema de archivos** como método.
3. Elija el directorio. Por convención, el ejemplo descargado usa `bin/PublishOutput`.

![Conexión de publicación][publish-connection]

Después, abra la sección **Opciones de publicación de archivos** de la pestaña **Configuración**. Seleccione **Precompilar durante la publicación**. Esta optimización significa que compilará vistas en el contenedor de Docker, está copiando las vistas precompiladas.

![Configuración de publicación][publish-settings]

Haga clic en **Publicar** y Visual Studio copiará todos los recursos necesarios en la carpeta de destino. 

## <a name="build-the-image"></a>Compilar la imagen

Defina la imagen de Docker en un Dockerfile que contenga instrucciones para la imagen base, cualquier componente adicional, la aplicación que quiere ejecutar y otra imagen de configuración.  El Dockerfile es la entrada al comando `docker build`, que crea la imagen.

Creará una imagen basada en la imagen `microsft/aspnet` que se encuentra en [Docker Hub](https://hub.docker.com/r/microsoft/aspnet/).
La imagen base, `microsoft/aspnet`, es una imagen de Windows Server. Además de Windows Server Core, tiene IIS y ASP.NET 4.6.2 instalados y habilitados. Al ejecutar esta imagen en un contenedor, iniciará de forma automática IIS y los sitios web instalados estarán activos.

El Dockerfile que crea la imagen tiene el siguiente aspecto:

```
# The `FROM` instruction specifies the base image. You are
# extending the `microsoft/aspnet` image.

FROM microsoft/aspnet

# Next, this Dockerfile creates a directory for your application
RUN mkdir C:\randomanswers

# configure the new site in IIS.
RUN powershell -NoProfile -Command \
    Import-module IISAdministration; \
    New-IISSite -Name "ASPNET" -PhysicalPath C:\randomanswers -BindingInformation "*:8000:"

# This instruction tells the container to listen on port 8000. 
EXPOSE 8000

# The final instruction copies the site you published earlier into the container.
ADD containerImage/ /randomanswers
```

No hay ningún comando `ENTRYPOINT` en este Dockerfile. No se necesita ninguno.
La imagen base garantiza que IIS se inicie cuando se inicia el contenedor. 

Después, debe ejecutar un comando de compilación de Docker para crear la imagen que ejecutará la aplicación de ASP.NET. Para ello, abra una ventana de PowerShell y escriba el siguiente comando en el directorio de la solución:

```
docker build -t mvcrandomanswers .
```

Este comando seguirá las instrucciones del Dockerfile para compilar la nueva imagen. Esto puede incluir la extracción de la imagen base de [Docker Hub](http://hub.docker.com) y después agregará la aplicación a esa imagen.

Una vez que el comando finaliza, puede ejecutar el comando `docker images` para ver información sobre la nueva imagen:

```
REPOSITORY                    TAG                 IMAGE ID            CREATED             SIZE
mvcrandomanswers              latest              86838648aab6        2 minutes ago       8.104 GB
```

El IDENTIFICADOR DE LA IMAGEN será diferente en su equipo. Ahora, ejecutará la aplicación.

## <a name="start-a-container"></a>Iniciar un contenedor

Para iniciar un contenedor, ejecute el siguiente comando `docker run`:

```
docker run -d -p 8000:8000 --name randomanswers mvcrandomanswers
```

El argumento `-d` indica a Docker que inicie la imagen en modo desasociado. Esto significa que la imagen de Docker se ejecuta desconectada del shell actual.

El argumento `-p 8000:8000` indica a Docker cómo asignar los puertos de entrada. En este ejemplo, se usa el puerto 8000 en el host y en el contenedor.

El argumento `--name randomanswers` da un nombre al contenedor en ejecución. Puede usar este nombre en lugar del identificador del contenedor en la mayoría de los comandos.

El argumento `mvcrandomanswers` es el nombre de la imagen que se iniciará.

## <a name="verify-in-the-browser"></a>Comprobar en el explorador

> [!NOTE]
> Con la versión actual, no puede usar `http://localhost` para explorar el sitio. Esto se debe a un comportamiento conocido en WinNAT y se resolverá en el futuro. Hasta que se solucione, debe usar la dirección IP del contenedor.

Una vez iniciado el contenedor, necesitará encontrar su dirección IP para poder conectarse al contenedor en ejecución desde un explorador:

```
docker inspect -f "{{ .NetworkSettings.Networks.nat.IPAddress }}" randomanswers
172.31.194.61
```

Puede conectarse al contenedor en ejecución mediante la dirección IPv4 y el puerto configurado (8000), `http://172.31.194.61:8000` en el ejemplo mostrado. Escriba esa dirección URL en el explorador y debería ver el sitio en ejecución.

> [!NOTE]
> Algún software de proxy o VPN puede impedir que explore su sitio.
> Puede deshabilitarlo de forma temporal para asegurarse de que el contenedor funciona.

El directorio de ejemplo en GitHub contiene un [script de PowerShell](https://github.com/dotnet/docs/tree/master/samples/framework/docker/MVCRandomAnswerGenerator/run.ps1) que ejecuta estos comandos. Abra una ventana de PowerShell, cambie el directorio por el directorio de la solución y escriba:

```
./run.ps1
```

Crea la imagen, muestra la lista de imágenes del equipo, inicia un contenedor y muestra la dirección IP de ese contenedor. 

Cuando haya terminado y quiera detener el contenedor, envíe un comando `docker
stop`:

```
docker stop randomanswers
```

Para quitar el contenedor, envíe un comando `docker rm`:

```
docker rm randomanswers
```

## <a name="summary"></a>Resumen

En este tema, ha visto los pasos para mover y ejecutar una aplicación de ASP.NET MVC existente en un contenedor de Windows Server. Ejecutar una aplicación existente no requiere ningún cambio en la aplicación. Debe ejecutar las tareas para publicar la aplicación, crear una imagen de Docker e iniciar esa imagen en un nuevo contenedor. Aprovechar los contenedores de Windows Server es la forma más sencilla de migrar las aplicaciones existentes a este entorno.

[windows-container]: media/aspnetmvc/SwitchContainer.png "Cambiar al contenedor de Windows"
[publish-connection]: media/aspnetmvc/PublishConnection.png "Publicar en el sistema de archivos"
[publish-settings]: media/aspnetmvc/PublishSettings.png "Configuración de publicación"



<!--HONumber=Nov16_HO3-->


