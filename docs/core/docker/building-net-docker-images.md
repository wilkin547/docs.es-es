---
title: Creación de imágenes de Docker de .NET Core
description: Descripción de las imágenes de Docker y .NET Core
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: e48a263334ebb93a5d281032336aeb4073d8467c
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "34827344"
---
# <a name="building-docker-images-for-net-core-applications"></a>Creación de imágenes de Docker para aplicaciones de .NET Core

 Este tutorial se centra en cómo usar .NET Core en Docker. En primer lugar se analizan las distintas imágenes de Docker que ofrece y mantiene Microsoft, además de los casos de uso. Luego se aprende a compilar una aplicación de ASP.NET Core y a aplicarle Docker.

Este tutorial ayuda a:
> [!div class="checklist"]
> * Obtener información sobre las imágenes de Microsoft .NET Core Docker 
> * Obtener una aplicación de ejemplo de ASP.NET Core para aplicarle Docker
> * Ejecutar la aplicación de ejemplo de ASP.NET en local
> * Compilar y ejecutar el ejemplo con contenedores de Docker para Linux
> * Compilar y ejecutar el ejemplo con contenedores de Docker para Windows

## <a name="docker-image-optimizations"></a>Optimizaciones de imágenes de Docker

Al crear imágenes de Docker para desarrolladores, nos centramos en tres escenarios principales:

* Imágenes usadas para desarrollar aplicaciones .NET Core
* Imágenes usadas para crear aplicaciones .NET Core
* Imágenes usadas para ejecutar aplicaciones de .NET Core

¿Por qué tres imágenes?
Al desarrollar, compilar y ejecutar aplicaciones en contenedor, hay prioridades diferentes.

* **Desarrollo:** la prioridad se centra en la iteración rápida de los cambios y en la posibilidad de depurarlos. El tamaño de la imagen no es tan importante; lo que importa es si se pueden hacer cambios en el código y verlos rápidamente.

* **Compilación:** esta imagen contiene todo lo necesario para compilar la aplicación, lo que incluye el compilador y las demás dependencias para optimizar los archivos binarios.  La imagen de compilación se usa para crear los recursos que se colocan en una imagen de producción. La imagen de compilación se usaría para la integración continua, o en un entorno de compilación. Este enfoque permite a un agente de compilación compilar y generar la aplicación (con todas las dependencias necesarias) en una instancia de imagen de compilación. El agente de compilación solo necesita saber cómo ejecutar la imagen de Docker.

* **Producción:** velocidad a la que puede implementar e iniciar la imagen. Esta imagen es pequeña, así que el rendimiento de red desde el Registro de Docker hasta los hosts de Docker está optimizado. El contenido está listo para ejecutar, lo que permite el tiempo más rápido desde la ejecución de Docker hasta el procesamiento de los resultados. En el modelo de Docker no se necesita compilación de código dinámico. El contenido que se coloca en esta imagen estaría limitado a los archivos binarios y al contenido necesario para ejecutar la aplicación.

    Por ejemplo, la salida `dotnet publish` contiene:

    * los archivos binarios compilados
    * archivos .js y .css


La razón para incluir la salida del comando `dotnet publish` en la imagen de producción es mantener su tamaño al mínimo.

Algunas imágenes de .NET Core comparten capas entre diferentes etiquetas, de modo que la descarga de la última etiqueta es un proceso relativamente ligero. Si ya tiene una versión anterior en el equipo, esta arquitectura reduce el espacio en disco necesario.

Cuando varias aplicaciones usan imágenes comunes en el mismo equipo, la memoria se comparte entre las imágenes comunes. Las imágenes deben ser las mismas para poder compartirse.

## <a name="docker-image-variations"></a>Variantes de imagen de Docker

Para lograr los objetivos anteriores, en [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/) se proporcionan variantes de imágenes.

* `microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.1-sdk`): esta imagen contiene el SDK de .NET Core, que incluye .NET Core y las herramientas de línea de comandos (CLI). Esta imagen se asigna al **escenario de desarrollo**. Esta imagen se usa para el desarrollo local, la depuración y las pruebas unitarias. Esta imagen también puede usarse en sus escenarios de **compilación**. Al usar `microsoft/dotnet:sdk` siempre se obtiene la versión más reciente.

> [!TIP]
> Si no está seguro de sus necesidades, se recomienda usar la imagen `microsoft/dotnet:<version>-sdk`. Como imagen "de facto", se ha diseñado para usarse como contenedor desechable (monte el código fuente e inicie el contenedor para iniciar la aplicación) y como imagen base para compilar otras imágenes.

* `microsoft/dotnet:<version>-runtime`: esta imagen contiene .NET Core (runtime y bibliotecas) y está optimizada para ejecutar aplicaciones de .NET Core en **producción**.

## <a name="alternative-images"></a>Imágenes nativas

Además de los escenarios optimizados de desarrollo, compilación y producción, proporcionamos imágenes adicionales:

* `microsoft/dotnet:<version>-runtime-deps`: la imagen de **dependencias en tiempo de ejecución** contiene el sistema operativo con todas las dependencias nativas que necesita .NET Core. Esta imagen es para [aplicaciones autocontenidas](../deploying/index.md).

Versiones más recientes de cada variante:

* `microsoft/dotnet` o `microsoft/dotnet:latest` (alias para la imagen del SDK)
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a>Ejemplos para examinar

* [En este ejemplo de Docker de ASP.NET Core](https://github.com/dotnet/dotnet-docker/tree/master/samples/aspnetapp) se muestra un patrón de prácticas recomendadas para compilar imágenes de Docker para aplicaciones de ASP.NET Core para entornos de producción. El ejemplo funciona con contenedores de Linux y Windows.

* En este ejemplo de Docker de .NET Core se muestra un patrón de prácticas recomendadas para [compilar imágenes de Docker para aplicaciones de .NET Core para entornos de producción.](https://github.com/dotnet/dotnet-docker/tree/master/samples/dotnetapp)

## <a name="your-first-aspnet-core-docker-app"></a>Primera aplicación de ASP.NET Core Docker

En este tutorial se usa una aplicación de ejemplo de ASP.NET Core Docker para la aplicación a la que se va a aplicar Docker. En esta aplicación de ejemplo de ASP.NET Core Docker se muestra un patrón de procedimientos recomendados para compilar imágenes de Docker para aplicaciones de ASP.NET Core para producción. El ejemplo funciona con contenedores de Linux y Windows.

El Dockerfile de ejemplo crea una imagen de Docker de aplicación de ASP.NET Core basada en la imagen base de Docker de runtime de ASP.NET Core.

Usa la [característica de compilación de varias fases de Docker](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) para:

* compilar el ejemplo en un contenedor en función de la **mayor** imagen base de Docker de compilación de ASP.NET Core 
* copiar el resultado de la compilación final en una imagen de Docker en función de la **menor** imagen base de Docker de runtime de ASP.NET Core

> [!NOTE]
> La imagen de compilación contiene las herramientas necesarias para compilar aplicaciones, mientras que la imagen de runtime no.

### <a name="prerequisites"></a>Requisitos previos

Para compilar y ejecutar, instale los siguientes elementos:

#### <a name="net-core-21-sdk"></a>SDK de .NET Core 2.1

* Instale el [SDK de .NET Core 2.1](https://www.microsoft.com/net/core).

* Instale el editor de código que prefiera si aún no lo ha hecho.

> [!TIP]
> ¿Es necesario instalar un editor de código? Pruebe [Visual Studio](https://visualstudio.com/downloads).

#### <a name="installing-docker-client"></a>Instalación del cliente Docker

Instale la versión [Docker 18.03](https://docs.docker.com/release-notes/docker-ce/) o posterior del cliente Docker.

El cliente Docker se puede instalar en:

* Distribuciones de Linux

   * [CentOS](https://www.docker.com/docker-centos-distribution)

   * [Debian](https://www.docker.com/docker-debian)

   * [Fedora](https://www.docker.com/docker-fedora)

   * [Ubuntu](https://www.docker.com/docker-ubuntu)

* [macOS](https://docs.docker.com/docker-for-mac/)

* [Windows](https://docs.docker.com/docker-for-windows/).

#### <a name="installing-git-for-sample-repository"></a>Instalación de Git para el repositorio de ejemplo

* Instale [git](https://git-scm.com/download) si quiere clonar el repositorio.

### <a name="getting-the-sample-application"></a>Obtención de la aplicación de ejemplo

La manera más sencilla de obtener el ejemplo es clonar el [repositorio de .NET Core Docker](https://github.com/dotnet/dotnet-docker) con git, mediante las siguientes instrucciones: 

```console
git clone https://github.com/dotnet/dotnet-docker
```

También puede descargar el repositorio (es pequeño) como un archivo zip desde el repositorio de .NET Core Docker.

### <a name="run-the-aspnet-app-locally"></a>Ejecutar la aplicación de ASP.NET en local

Como punto de referencia, antes de que meter la aplicación en un contenedor, ejecútela localmente.

Puede compilar y ejecutar la aplicación en local con el SDK de .NET Core 2.1 mediante los comandos siguientes (las instrucciones presuponen la raíz del repositorio):

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located
cd aspnetapp // project scope

dotnet run
```

Una vez iniciada la aplicación, visite **http://localhost:5000** en el explorador web.

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a>Compilar y ejecutar el ejemplo con contenedores de Docker para Linux

Puede compilar y ejecutar el ejemplo en Docker con contenedores de Linux mediante los comandos siguientes (las instrucciones presuponen la raíz del repositorio):

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located

docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!NOTE]
> El argumento `docker run` "-p" asigna el puerto 5000 del equipo local al puerto 80 del contenedor (el formato de asignación de puerto es `host:container`). Para más información, vea la referencia [docker run](https://docs.docker.com/engine/reference/commandline/exec/) en los parámetros de línea de comandos.

Una vez iniciada la aplicación, visite **http://localhost:5000** en el explorador web.

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a>Compilar y ejecutar el ejemplo con contenedores de Docker para Windows

Puede compilar y ejecutar el ejemplo en Docker con contenedores de Windows mediante los comandos siguientes (las instrucciones presuponen la raíz del repositorio):

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located

docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> Si usa contenedores de Windows, debe ir a la **dirección IP del contenedor** (en lugar de http://localhost)) en el explorador directamente. Puede obtener la dirección IP del contenedor con los pasos siguientes:

* Abra otro símbolo del sistema.
* Ejecute `docker ps` para ver los contenedores en ejecución. El contenedor "aspnetcore_sample" debería estar ahí.
* Ejecute `docker exec aspnetcore_sample ipconfig`.
* Copie la dirección IP del contenedor y péguela en el explorador (por ejemplo, 172.29.245.43).

> [!NOTE]
> La ejecución de Docker admite la identificación de contenedores con nombre o hash. En el ejemplo se usa el nombre (aspnetcore_sample).

Vea el siguiente ejemplo de cómo obtener la dirección IP de un contenedor de Windows en ejecución.

```console
docker exec aspnetcore_sample ipconfig

Windows IP Configuration

Ethernet adapter Ethernet:

   Connection-specific DNS Suffix  . : contoso.com
   Link-local IPv6 Address . . . . . : fe80::1967:6598:124:cfa3%4
   IPv4 Address. . . . . . . . . . . : 172.29.245.43
   Subnet Mask . . . . . . . . . . . : 255.255.240.0
   Default Gateway . . . . . . . . . : 172.29.240.1
```

> [!NOTE]
> La ejecución de Docker ejecuta un comando nuevo en un contenedor en ejecución. Para más información, vea la referencia [docker exec](https://docs.docker.com/engine/reference/commandline/exec/) en los parámetros de línea de comandos.

Puede crear una aplicación lista para implementarse en producción localmente mediante el comando [dotnet publish](../tools/dotnet-publish.md).

```console
dotnet publish -c Release -o published
```

> [!NOTE]
> El argumento de versión -c compila la aplicación en modo de versión (el valor predeterminado es el modo de depuración). Para más información, vea la referencia [dotnet run](../tools/dotnet-run.md) en los parámetros de línea de comandos.

Puede ejecutar la aplicación en **Windows** mediante el siguiente comando.

```console
dotnet published\aspnetapp.dll
```

Puede ejecutar la aplicación en **Linux** o **macOS** mediante el siguiente comando.

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a>Imágenes de Docker usadas en este ejemplo

En el dockerfile de este ejemplo se usan las siguientes imágenes de Docker.

* `microsoft/dotnet:2.1-sdk`
* `microsoft/dotnet:2.1-aspnetcore-runtime`

¡Enhorabuena! Acaba de:
> [!div class="checklist"]
> * Obtener información sobre las imágenes de Microsoft .NET Core Docker
> * Obtener una aplicación de ejemplo de ASP.NET Core para aplicarle Docker
> * Ejecutar la aplicación de ejemplo de ASP.NET en local
> * Compilar y ejecutar el ejemplo con contenedores de Docker para Linux
> * Compilar y ejecutar el ejemplo con contenedores de Docker para Windows


**Pasos siguientes**

Estos son algunos de los pasos que puede realizar a continuación:

* [Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker) (Trabajo con Visual Studio Docker Tools)
* [Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Implementación de imágenes de Docker desde Azure Container Registry a Azure Container Instances)
* [Depuración con Visual Studio Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments) (Información práctica sobre Visual Studio para Mac, contenedores y código sin servidor en la nube)
* [Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started) (Introducción a Docker y Visual Studio para Mac Lab)

> [!NOTE]
> Si no tiene una suscripción de Azure, [regístrese hoy](https://azure.microsoft.com/free/?b=16.48) para obtener una cuenta gratuita durante 30 días y obtenga 200 dólares en créditos de Azure para probar cualquier combinación de servicios de Azure.
