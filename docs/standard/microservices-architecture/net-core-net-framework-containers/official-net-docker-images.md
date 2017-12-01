---
title: "Imágenes de Docker .NET oficiales"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Imágenes de Docker .NET oficiales"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 6f14bd0cf55a552f3881d755ebe7389f000975d8
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="official-net-docker-images"></a>Imágenes de Docker .NET oficiales

Las imágenes de Docker oficial de .NET son imágenes de Docker creado y optimizado por Microsoft. Están disponibles públicamente en los repositorios de Microsoft en [Docker Hub](https://hub.docker.com/u/microsoft/). Cada repositorio puede contener varias imágenes, dependiendo de las versiones de .NET y las versiones (Linux Debian, Alpine Linux, Windows Nano Server, Windows Server Core, etcetera) y el sistema operativo.

La visión de Microsoft para los repositorios de .NET es tener repositorios granular y tiene el foco, donde un repositorio representa un escenario específico o carga de trabajo. Por ejemplo, el [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) imágenes se deben usar cuando mediante ASP.NET Core en Docker, porque esas imágenes de ASP.NET Core proporcionan optimizaciones adicionales contenedores por lo que puede iniciar más rápido.

Por otro lado, las imágenes de .NET Core (microsoft/dotnet) están diseñadas para las aplicaciones de consola basadas en .NET Core. Por ejemplo, procesos por lotes, los trabajos Web de Azure y otros escenarios de consola deben utilizar .NET Core. Las imágenes no incluyen la pila de ASP.NET Core, lo que produce una imagen de contenedor más pequeña.

Mayoría repositorios de imagen proporcionan amplia etiquetado para ayudarle a seleccionar no solo una versión de un marco concreto, sino también para elegir un sistema operativo (distribución de Linux o versión de Windows).

Para obtener más información acerca de las imágenes de Docker .NET oficiales proporcionadas por Microsoft, consulte el [resumen .NET Docker Images](https://aka.ms/dotnetdockerimages).

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a>.NET core y Docker optimizaciones de imagen para el desarrollo y producción

Al compilar imágenes de Docker para los desarrolladores, Microsoft se centra en los siguientes escenarios principales:

-   Imágenes que se utilizan para *desarrollar* y compilar aplicaciones de .NET Core.

-   Imágenes que se utilizan para *ejecutar* aplicaciones .NET Core.

¿Por qué varias imágenes? Al desarrollar, compilar y ejecutar aplicaciones en contenedores, normalmente tengan diferentes prioridades. Al proporcionar diferentes imágenes para estas tareas independientes, Microsoft le ayuda a optimizar los procesos de desarrollo, crear e implementar aplicaciones independientes.

### <a name="during-development-and-build"></a>Durante el desarrollo y compilación

Durante el desarrollo, lo que es importante es la velocidad puede recorrer en iteración cambios y la capacidad para depurar los cambios. El tamaño de la imagen no es tan importante como la capacidad de realizar cambios en el código y ver rápidamente los cambios. Algunas herramientas y "contenedores de agente de compilación", utilice el desarrollo de la imagen de ASP.NET Core (microsoft/aspnetcore-build) durante el desarrollo y proceso de compilación. Cuando se crea dentro de un contenedor de Docker, los aspectos importantes son los elementos necesarios para compilar la aplicación. Esto incluye el compilador y las otras dependencias de .NET, además de las dependencias de desarrollo web como npm, Gulp y Bower.

¿Por qué es importante este tipo de imagen de compilación? No implemente esta imagen para producción. En su lugar, es una imagen que se utiliza para compilar el contenido que se coloca en una imagen de producción. Esta imagen se usaría en su entorno de integración continua (CI) o el entorno de compilación. Por ejemplo, en lugar de instalar manualmente las dependencias de aplicación directamente en un agente de compilación de host (una máquina virtual, por ejemplo), el agente de compilación crearía una instancia de una imagen de compilación de .NET Core con todas las dependencias necesarias para compilar la aplicación. El agente de compilación solo necesita saber cómo ejecutar la imagen de Docker. Esto simplifica el entorno de integración continua y resulta mucho más predecible.

### <a name="in-production"></a>En producción

¿Qué es importante en producción es ¿con qué rapidez puede implementar e iniciar los contenedores que se basa en una imagen de .NET Core de producción. Por lo tanto, la imagen sólo en tiempo de ejecución se basa en [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) es pequeño, por lo que puede desplazarse rápidamente a través de la red desde el registro de Docker para los hosts de Docker. El contenido está listo para ejecutarse, lo que permite el menor tiempo de inicio del contenedor al procesamiento de los resultados. En el modelo de Docker, no es necesario para la compilación de C\# código, como cuando se ejecute dotnet compilación o dotnet publicar cuando usa el contenedor de compilación.

En esta imagen optimizada coloque sólo los archivos binarios y otro contenido necesarios para ejecutar la aplicación. Por ejemplo, publicar el contenido creado con dotnet contiene solo los archivos binarios de .NET compilados, imágenes, .js y archivos .css. Con el tiempo, verá las imágenes que contienen paquetes anterior a la compilación JIT.

Aunque hay varias versiones de las imágenes de .NET Core y ASP.NET Core, todos ellos comparten una o varias capas, incluido el nivel de base. Por lo tanto, la cantidad de espacio en disco necesario para almacenar una imagen es pequeña; compone únicamente de las diferencias entre la imagen personalizada y su imagen de la base. El resultado es que es rápido extraer la imagen desde el registro.

Al explorar los repositorios de imagen de .NET en Docker Hub, encontrará varias versiones de imagen clasificada o marcadas con etiquetas. Estas etiquetas ayudan a decidir cuál utilizar, según la versión que necesita, como los de la tabla siguiente:

-   Microsoft /**aspnetcore:2.0**

        ASP.NET Core, with runtime only and ASP.NET Core optimizations, on Linux and Windows (multi-arch)

-   Microsoft /**aspnetcore-compilación: 2.0**

        ASP.NET Core, with SDKs included, on Linux and Windows (multi-arch)


>[!div class="step-by-step"]
[Anterior] (net-contenedor-os-targets.md) [siguiente] (.. /Architect-microservice-Container-Applications/Index.MD)
