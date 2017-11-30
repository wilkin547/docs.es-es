---
title: "Creación de imágenes de Docker de .NET Core"
description: "Descripción de las imágenes de Docker y .NET Core"
keywords: .NET, .NET Core, Docker
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
ms.openlocfilehash: 3ec2d5a58b46e332de41b618f1c3fac663b29bee
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2017
---
# <a name="building-docker-images-for-net-core-applications"></a>Creación de imágenes de Docker para aplicaciones de .NET Core

 En este tutorial se centra en cómo usar .NET Core en Docker. En primer lugar, exploramos las distintas imágenes de Docker ofrece y mantenido por Microsoft y casos de uso. A continuación, se Aprenda a crear y dockerize una aplicación de ASP.NET Core.

En el transcurso de este tutorial, aprenderá:
> [!div class="checklist"]
> * Obtenga información acerca de las imágenes de Docker de núcleo de Microsoft .NET 
> * Obtener un núcleo de ASP.NET de la aplicación de ejemplo para Dockerize
> * Ejecutar la aplicación de ejemplo ASP.NET localmente
> * Compilar y ejecutar el ejemplo con Docker para contenedores de Linux
> * Compilar y ejecutar el ejemplo con contenedores de Docker para Windows

## <a name="docker-image-optimizations"></a>Optimizaciones de imágenes de Docker

Al crear imágenes de Docker para desarrolladores, nos centramos en tres escenarios principales:

* Imágenes usadas para desarrollar aplicaciones .NET Core
* Imágenes usadas para crear aplicaciones .NET Core
* Imágenes usadas para ejecutar aplicaciones de .NET Core

¿Por qué tres imágenes?
Al desarrollar, compilar y ejecutar aplicaciones en contenedores, se tengan diferentes prioridades.

* **Desarrollo:** los enfoques de prioridad en iteración rápidamente cambios y la capacidad para depurar los cambios. El tamaño de la imagen no es tan importante, en su lugar puede hacer cambios en el código y verlas rápidamente?

* **La compilación:** esta imagen contiene todo lo necesario para compilar la aplicación, que incluye el compilador y las otras dependencias al optimizar los archivos binarios.  Usar la imagen de compilación para crear los activos que se colocan en una imagen de producción. La imagen de la compilación se usaría para la integración continua, o en un entorno de compilación. Este enfoque permite a un agente de compilación compilar y generar la aplicación (con todas las dependencias necesarias) en una instancia de la imagen de compilación. El agente de compilación solo necesita saber cómo ejecutar la imagen de Docker.

* **Producción:** rapidez puede implementar e iniciar la imagen? Esta imagen es pequeña, por lo que se optimiza el rendimiento de la red desde el registro de Docker para los hosts de Docker. El contenido está listo para ejecutar, lo que permite el tiempo más rápido desde la ejecución de Docker hasta el procesamiento de los resultados. Compilación de código dinámico no se necesita en el modelo de Docker. El contenido que se coloca en esta imagen estaría limitado a los archivos binarios y al contenido necesario para ejecutar la aplicación.

    Por ejemplo, el `dotnet publish` salida contiene:

    * los archivos binarios compilados
    * archivos .js y .css


La razón para incluir el `dotnet publish` resultado del comando en la imagen de producción es mantener su ' tamaño al mínimo.

Algunas imágenes de .NET Core compartan capas entre diferentes etiquetas para descargar la última etiqueta es un proceso relativamente ligero. Si ya tiene una versión anterior en su equipo, esta arquitectura reduce el espacio en disco necesario.

Cuando varias aplicaciones usan imágenes comunes en el mismo equipo, la memoria se comparte entre las imágenes comunes. Las imágenes deben ser las mismas que se pueden compartir.

## <a name="docker-image-variations"></a>Variantes de imagen de Docker

Para lograr los objetivos anteriores, proporcionamos variantes de imagen en [ `microsoft/dotnet` ](https://hub.docker.com/r/microsoft/dotnet/).

* `microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) Esta imagen contiene el núcleo de .NET SDK, que incluye el núcleo de .NET y herramientas de línea de comandos (CLI). Esta imagen se asigna al **escenario de desarrollo**. Usar esta imagen para el desarrollo local, depuración y pruebas unitarias. Esta imagen también puede usarse en sus escenarios de **compilación**. Usar `microsoft/dotnet:sdk` siempre obtendrá la versión más reciente.

> [!TIP]
> Si no está seguro acerca de sus necesidades, desea utilizar la `microsoft/dotnet:<version>-sdk` imagen. Como la imagen "de facto", se ha diseñado para utilizarse como throw contenedor alejada (montar el código fuente e iniciar el contenedor para iniciar la aplicación) y como la imagen base para generar otras imágenes de.

* `microsoft/dotnet:<version>-runtime`: Esta imagen contiene el núcleo de .NET (en tiempo de ejecución y bibliotecas) y está optimizada para ejecutar aplicaciones de .NET Core **producción**.

## <a name="alternative-images"></a>Imágenes nativas

Además de los escenarios optimizados de desarrollo, compilación y producción, proporcionamos imágenes adicionales:

* `microsoft/dotnet:<version>-runtime-deps`: La **en tiempo de ejecución depós** imagen contiene el sistema operativo con todas las dependencias nativo necesarios .NET Core. Esta imagen es para [aplicaciones independientes](https://docs.microsoft.com/dotnet/core/deploying/index).

Versiones más recientes de cada variante:

* `microsoft/dotnet`o `microsoft/dotnet:latest` (alias para la imagen SDK)
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a>Ejemplos para explorar

* [Este ejemplo de ASP.NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) muestra un patrón de prácticas recomendado para la creación de imágenes de Docker para ASP.NET Core aplicaciones de producción. El ejemplo funciona con contenedores de Linux y Windows.

* Este ejemplo de .NET Core Docker muestra un patrón de prácticas recomendado para [crear imágenes de Docker para las aplicaciones de .NET Core para entornos de producción.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)

## <a name="your-first-aspnet-core-docker-app"></a>La primera aplicación de ASP.NET Core Docker

Para este tutorial, permite usar una aplicación de ejemplo de ASP.NET Core Docker para la aplicación que deseamos dockerize. Esta aplicación de ejemplo de ASP.NET Core Docker muestra un patrón de prácticas recomendado para la creación de imágenes de Docker para ASP.NET Core aplicaciones de producción. El ejemplo funciona con contenedores de Linux y Windows.

El ejemplo Dockerfile crea una imagen de Docker de aplicación de ASP.NET Core basada fuera de la imagen de base de Docker en tiempo de ejecución de ASP.NET Core.

Usa el [varias fases de Docker generar la característica](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) para:

* Genere el ejemplo en un contenedor en función de la **mayor** imagen base de Docker de compilación de ASP.NET Core 
* copia el resultado de compilación final en una imagen de Docker basada en la **menor** imagen base de tiempo de ejecución de ASP.NET Core Docker

> [!Note]
> La imagen de la compilación contiene las herramientas necesarias para crear aplicaciones, mientras que la imagen en tiempo de ejecución no.

### <a name="prerequisites"></a>Requisitos previos

Para compilar y ejecutar, instale los siguientes elementos:

#### <a name="net-core-20-sdk"></a>.NET core SDK 2.0

* Instalar [.NET Core SDK 2.0](https://www.microsoft.com/net/core).

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

#### <a name="installing-git-for-sample-repository"></a>Instalación de Git para el repositorio de ejemplo

* Instalar [git](https://git-scm.com/download) si desea clonar el repositorio.

### <a name="getting-the-sample-application"></a>Obtiene la aplicación de ejemplo

Es la manera más fácil de obtener el ejemplo mediante la clonación de la [repositorio de ejemplos](https://github.com/dotnet/dotnet-docker-samples) con git, mediante las siguientes instrucciones: 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

También puede descargar el repositorio (es pequeño) como un archivo zip del repositorio de ejemplos de .NET Core Docker.

### <a name="run-the-aspnet-app-locally"></a>Ejecutar la aplicación ASP.NET localmente

Como punto de referencia, antes de que meter la aplicación en un contenedor, ejecútela localmente.

Puede compilar y ejecutar la aplicación localmente con el SDK de .NET Core 2.0 utilizando los comandos siguientes (las instrucciones presupone la raíz del repositorio):

```console
cd aspnetapp
dotnet run
```

Tras iniciar la aplicación, visite **http://localhost: 5000** en el explorador web.

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a>Compilar y ejecutar el ejemplo con Docker para contenedores de Linux

Puede compilar y ejecutar el ejemplo en Docker con contenedores de Linux utilizando los comandos siguientes (las instrucciones presupone la raíz del repositorio):

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!Note] El `docker run` '-p' argumento asignaciones de puerto 5000 en el equipo local al puerto 80 del contenedor (la forma de asignación de puerto es `host:container`). Para obtener más información, consulte el [docker ejecutar](https://docs.docker.com/engine/reference/commandline/exec/) referencia en los parámetros de línea de comandos.

Tras iniciar la aplicación, visite **http://localhost: 5000** en el explorador web.

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a>Compilar y ejecutar el ejemplo con contenedores de Docker para Windows

Puede compilar y ejecutar el ejemplo en Docker con contenedores de Windows mediante los comandos siguientes (las instrucciones presupone la raíz del repositorio):

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> Debe ir a la **dirección IP del contenedor** (en lugar de http://localhost) en el explorador directamente al utilizar los contenedores de Windows. Puede obtener la dirección IP del contenedor con los pasos siguientes:

* Abra el símbolo del otro.
* Ejecute `docker ps` para ver los contenedores en ejecución. El contenedor "aspnetcore_sample" debería existir.
* Ejecute `docker exec aspnetcore_sample ipconfig`.
* Copie la dirección IP del contenedor y pegue en el explorador (por ejemplo, 172.29.245.43).

> [!Note]
> Ejecución de docker es compatible con contenedores de identificación con nombre o hash. En nuestro ejemplo, se utiliza el nombre (aspnetcore_sample).

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

> [!Note]
> Ejecución de docker ejecuta un comando nuevo en un contenedor en ejecución. Para obtener más información, consulte el [referencia de docker exec](https://docs.docker.com/engine/reference/commandline/exec/) en parámetros de línea de comandos.

Puede generar una aplicación que está lista para implementarse en producción localmente mediante el [publicar dotnet](../tools/dotnet-publish.md) comando.

```console
dotnet publish -c release -o published
```

> [!Note]
> El argumento de versión - c compila la aplicación en modo de lanzamiento (el valor predeterminado es el modo de depuración). Para obtener más información, consulte el [referencia de run dotnet](../tools/dotnet-run.md) en parámetros de línea de comandos.

Puede ejecutar la aplicación en **Windows** mediante el siguiente comando.

```console
dotnet published\aspnetapp.dll
```

Puede ejecutar la aplicación en **Linux** o **macOS** mediante el siguiente comando.

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a>Imágenes de docker que se utilizan en este ejemplo

Las siguientes imágenes de Docker se usan en este ejemplo

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

¡Enhorabuena! simplemente deberá:
> [!div class="checklist"]
> * Aprender acerca de las imágenes de Docker de núcleo de Microsoft .NET
> * Tiene un núcleo de ASP.NET de aplicación de ejemplo para Dockerize
> * Se ejecutó la aplicación de ejemplo ASP.NET localmente
> * Compila y se ejecutó el ejemplo con Docker para contenedores de Linux
> * Compila y se ejecutó el ejemplo con contenedores de Docker para Windows


**Pasos siguientes**

Aquí le mostramos algunos procedimientos que puede realizar:

* [Trabajar con herramientas de Docker de Visual Studio](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Implementación de imágenes de Docker desde el registro de contenedor de Azure a las instancias de contenedor de Azure](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [Depuración con el código de Visual Studio](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [Obtener las manos con Visual Studio para Mac, contenedores y el código sin servidor en la nube](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [Introducción a Docker y Visual Studio para Mac laboratorio](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

> [!Note]
> Si no tiene una suscripción de Azure, [Regístrese hoy](https://azure.microsoft.com/free/?b=16.48) para una cuenta gratuita de 30 días y get 200 dólares en créditos de Azure para probar cualquier combinación de los servicios de Azure.
