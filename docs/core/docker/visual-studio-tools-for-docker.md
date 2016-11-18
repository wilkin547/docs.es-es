---
title: Visual Studio Tools para Docker
description: Uso de Visual Studio Tools para Docker
keywords: .NET, .NET Core, Docker, ASP.NET Core, Visual Studio 2015
author: spboyer
manager: wpickett
ms.date: 09/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 1f3b9a68-4dea-4b60-8cb3-f46164eedbbf
translationtype: Human Translation
ms.sourcegitcommit: 03193513706967a46f74bccdba08a56946dd67df
ms.openlocfilehash: 274402bbd254e97d88771675daf07995983914aa

---

# <a name="visual-studio-tools-for-docker"></a>Visual Studio Tools para Docker 
Desarrollar y depurar la aplicación en un contenedor de Docker puede constituir una batería de tareas para configurar con varias herramientas. [Visual Studio Tools para Docker](https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4) le ayuda a superar los obstáculos y buscar los errores con F5 para depurar la aplicación directamente en un contenedor de Docker hospedado localmente. 

> [!NOTE]
>La versión actual se orienta a los contenedores de Linux Docker, mientras que los de Windows llegarán próximamente.

## <a name="prerequisites"></a>Requisitos previos
- [Microsoft Visual Studio 2015 Update 3](https://www.visualstudio.com/downloads/download-visual-studio-vs)
- [Herramientas de .NET Core 1.0.1 - VS 2015 Preview 2](https://go.microsoft.com/fwlink/?LinkID=827546)
- [Docker para Windows](https://www.docker.com/products/docker#/windows) para ejecutar localmente los contenedores de Docker

## <a name="installation-and-setup"></a>Instalación y configuración
Descargue e instale [Visual Studio Tools para Docker](https://aka.ms/DockerToolsForVS) desde la [Galería de Visual Studio](http://visualstudiogallery.msdn.microsoft.com/) o bien busque en **Extensiones y actualizaciones** en Visual Studio. 

Una configuración necesaria es configurar **[unidades compartidas](https://docs.docker.com/docker-for-windows/#/shared-drives)** en Docker para Windows. La configuración es necesaria para la compatibilidad de asignación y depuración de los volúmenes.

Haga clic con el botón derecho en el icono de Docker en la bandeja del sistema, haga clic en Settings (Configuración) y seleccione Shared Drives (Unidades compartidas).

![Unidades compartidas](./media/visual-studio-tools-for-docker/settings-shared-drives-win.png) 

## <a name="create-an-aspnet-web-application-and-add-docker-support"></a>Creación de una aplicación web ASP.NET y adición de la compatibilidad con Docker

Con Visual Studio, cree una nueva aplicación web de ASP.NET Core. Cuando se carga la aplicación, seleccione **Add Docker Support** (Agregar compatibilidad con Docker) desde el **menú de proyecto** o haga clic en el proyecto desde el Explorador de soluciones y seleccione **Agregar** > **Docker Support** (Compatibilidad con Docker).

Menú de proyecto

![Agregar compatibilidad con Docker del proyecto](./media/visual-studio-tools-for-docker/project-add-docker-support.png)

Menú contextual del proyecto

![Hacer clic con el botón derecho en Agregar compatibilidad con Docker](./media/visual-studio-tools-for-docker/right-click-add-docker-support.png)

También se agrega al proyecto los siguientes archivos:

- **Dockerfile**: el archivo de Docker para las aplicaciones de ASP.NET Core se basa en la imagen [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore). Esta imagen incluye los paquetes NuGet de ASP.NET Core que se hayan precompilado, con lo que se mejora el rendimiento en el inicio. Al compilar aplicaciones de consola de .NET Core, el archivo Dockerfile de origen hará referencia a la última imagen [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet).
- **docker-compose.yml**: archivo de Docker Compose de base utilizado para definir la colección de imágenes que se van a compilar y ejecutar con docker-compose build/run.  
- **docker-compose.dev.debug.yml**: archivo docker-compose adicional para cambios iterativos cuando se establece la configuración en depuración. Visual Studio llamará a -f docker-compose.yml -f docker-compose.dev.debug.yml para combinarlos. Las herramientas de desarrollo de Visual Studio usarán este archivo compuesto.   
- **docker-compose.dev.release.yml**: archivo de Docker Compose adicional para depurar la definición de versión. Montará el volumen del depurador, por lo que no cambia el contenido de la imagen de producción.  

El archivo docker-compose.yml contiene el nombre de la imagen que se crea al ejecutar el proyecto. 

```
version '2'

services:
  hellodockertools:
    image:  user/hellodockertools${TAG}
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "80"

``` 

En este ejemplo, `image: user/hellodockertools${TAG}` genera la imagen `user/hellodockertools:dev` cuando se ejecuta la aplicación en modo **Depuración** y `user/hellodockertools:latest` en modo **Lanzamiento**, respectivamente. 

Querrá cambiar el `user` a su nombre de usuario de Docker Hub si va a insertar la imagen en el registro. Por ejemplo, `spboyer/hellodockertools`, o cambiar la dirección URL del registro privada `privateregistry.domain.com/` dependiendo de la configuración.

### <a name="debugging"></a>Depuración
Seleccione **Docker** en la lista desplegable de depuración en la barra de herramientas y utilice F5 para iniciar la depuración de la aplicación. 

- Se adquiere la imagen de microsoft/aspnetcore (si no está ya en la memoria caché).
- ASPNETCORE_ENVIRONMENT se establece en Desarrollo dentro del contenedor.
- Se EXPONE el PUERTO 80 y se asigna a un puerto dinámicamente asignado para el host local. El puerto viene determinado por el host de docker y se puede consultar con docker ps. 
- La aplicación se copia en el contenedor.
- Se inicia el explorador predeterminado con el depurador asociado al contenedor, utilizando el puerto asignado dinámicamente. 

La imagen de Docker resultante creada es la imagen `dev` de la aplicación con las imágenes `microsoft/aspnetcore` como la imagen base.
Nota: La imagen de desarrollo está vacía de contenido de aplicación ya que las configuraciones de depuración utilizan el montaje del volumen para proporcionar la experiencia iterativa. Para insertar una imagen, use la configuración de lanzamiento.

```console
REPOSITORY                  TAG         IMAGE ID            CREATED         SIZE
spboyer/hellodockertools    dev         0b6e2e44b3df        4 minutes ago   268.9 MB
microsoft/aspnetcore        1.0.1       189ad4312ce7        5 days ago      268.9 MB
```

La aplicación se ejecuta con el contenedor que puede ver mediante la ejecución del comando `docker ps`.

```console
CONTAINER ID        IMAGE                          COMMAND               CREATED             STATUS              PORTS                   NAMES
3f240cf686c9        spboyer/hellodockertools:dev   "tail -f /dev/null"   4 minutes ago       Up 4 minutes        0.0.0.0:32769->80/tcp   hellodockertools_hellodockertools_1
```

### <a name="edit-and-continue"></a>Editar y continuar
Los cambios en los archivos estáticos o archivos de plantilla Razor (.cshtml) se actualizan automáticamente sin necesidad de un paso de compilación. Realice el cambio, guarde y pulse Actualizar en el explorador para ver la actualización.  

Las modificaciones en los archivos de código requieren compilación y un reinicio del Kestrel dentro del contenedor. Después de realizar la modificación, use CTRL + F5 para realizar el proceso e iniciar la aplicación dentro del contenedor. El contenedor de Docker no se vuelve a crear ni se detiene; mediante `docker ps` en la línea de comandos puede ver que el contenedor original todavía se está ejecutando desde hace 10 minutos. 

```console
CONTAINER ID        IMAGE                          COMMAND               CREATED             STATUS              PORTS                   NAMES
3f240cf686c9        spboyer/hellodockertools:dev   "tail -f /dev/null"   10 minutes ago      Up 10 minutes       0.0.0.0:32769->80/tcp   hellodockertools_hellodockertools_1
```

### <a name="publishing-docker-images"></a>Publicación de imágenes de Docker 
Una vez completado el ciclo de desarrollo y depuración de la aplicación, Visual Studio Tools para Docker le ayudará a crear la imagen de producción de la aplicación. Cambie la lista desplegable de depuración a **Lanzamiento** y compile la aplicación. Las herramientas producirán la imagen con la etiqueta `:latest` que puede insertar en el registro privado o en Docker Hub. 

Mediante `docker images` puede ver la lista de imágenes.

```console
REPOSITORY                 TAG                 IMAGE ID            CREATED             SIZE
spboyer/hellodockertools   latest              8184ae38ba91        5 seconds ago       278.4 MB
spboyer/hellodockertools   dev                 0b6e2e44b3df        About an hour ago   268.9 MB
microsoft/aspnetcore       1.0.1               189ad4312ce7        5 days ago          268.9 MB
```

Se puede esperar que la imagen de producción o lanzamiento sea de menor tamaño en comparación a la imagen de **desarrollo**; sin embargo, mediante el uso de la asignación del volumen, el depurador y la aplicación se están ejecutando realmente desde la máquina local y no dentro del contenedor. La **última** imagen ha empaquetado el código de aplicación completo necesario para ejecutar la aplicación en una máquina host, por lo tanto, la diferencia es el tamaño del código de aplicación.



<!--HONumber=Nov16_HO3-->


