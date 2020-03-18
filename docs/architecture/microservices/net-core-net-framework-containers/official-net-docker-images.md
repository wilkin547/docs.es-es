---
title: Imágenes oficiales de Docker de .NET
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Imágenes de Docker de .NET oficiales
ms.date: 01/30/2020
ms.openlocfilehash: 50a50587b35f811859841c4e049f40cb99479372
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77501879"
---
# <a name="official-net-docker-images"></a>Imágenes oficiales de Docker de .NET

Las imágenes oficiales de Docker de .NET son imágenes de Docker que Microsoft ha creado y optimizado. Están disponibles públicamente en los repositorios de Microsoft en [Docker Hub](https://hub.docker.com/u/microsoft/). Cada repositorio puede contener varias imágenes, según las versiones de .NET y según el sistema operativo y las versiones (Linux Debian, Linux Alpine, Windows Nano Server, Windows Server Core, etcétera).

Desde .NET Core 2.1, todas las imágenes de .NET Core, incluidas las de ASP.NET Core, están disponibles en Docker Hub, en el repositorio de imágenes de .NET Core: <https://hub.docker.com/_/microsoft-dotnet-core/>.

Desde mayo de 2018, las imágenes de Microsoft [se distribuyen en Microsoft Container Registry](https://azure.microsoft.com/blog/microsoft-syndicates-container-catalog/). El catálogo oficial todavía está disponible, pero únicamente en Docker Hub, y allí encontrará la dirección actualizada para extraer la imagen.

La mayoría de los repositorios de imágenes ofrece un etiquetado exhaustivo con el que es más fácil elegir no solo la versión de un marco concreto, sino también un sistema operativo (distribución de Linux o versión de Windows).

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a>Optimizaciones de imágenes de .NET Core y Docker para desarrollo y para producción

Al compilar imágenes de Docker para desarrolladores, Microsoft se centró en los siguientes escenarios principales:

- Imágenes que se usan para *desarrollar* y compilar aplicaciones de .NET Core.

- Imágenes que se usan para *ejecutar* aplicaciones de .NET Core.

¿Por qué varias imágenes? Al desarrollar, compilar y ejecutar aplicaciones en contenedor, normalmente hay prioridades diferentes. Al proporcionar diferentes imágenes para estas tareas independientes, con Microsoft es más fácil optimizar los procesos independientes de desarrollo, creación e implementación de aplicaciones.

### <a name="during-development-and-build"></a>Durante el desarrollo y la compilación

Durante el desarrollo, lo importante es la velocidad con que se pueden iterar los cambios y la capacidad para depurar los cambios. El tamaño de la imagen no es tan importante como la capacidad de realizar cambios en el código y ver rápidamente los cambios. Algunas herramientas y "contenedores de agente de compilación" usan la imagen de .NET Core de desarrollo (*mcr.microsoft.com/dotnet/core/sdk:3.1*) durante el proceso de desarrollo y compilación. Al compilar dentro de un contenedor de Docker, los aspectos importantes son los elementos necesarios para compilar la aplicación. Esto incluye el compilador y cualquier otra dependencia de .NET.

¿Por qué es importante este tipo de imagen de compilación? Esta imagen no se implementa para producción, sino que es una imagen que se usa para compilar el contenido que se coloca en una imagen de producción. Esta imagen se usaría en el entorno de integración continua (CI) o el entorno de compilación al utilizar compilaciones de Docker de varias fases.

### <a name="in-production"></a>En producción

Lo importante en producción es la rapidez con que se pueden implementar e iniciar los contenedores según una imagen de .NET Core de producción. Por tanto, la imagen solo en tiempo de ejecución basada en *mcr.microsoft.com/dotnet/core/aspnet:3.1* es pequeña, por lo que puede desplazarse rápidamente a través de la red desde el Registro de Docker hasta los hosts de Docker. El contenido está listo para ejecutarse, lo que agiliza el proceso que va desde iniciar el contenedor hasta procesar los resultados. En el modelo de Docker, no es necesario compilar desde el código C\#, como cuando se ejecuta dotnet build o dotnet publish al usar el contenedor de compilación.

En esta imagen optimizada solo se colocan los archivos binarios y otros contenidos necesarios para ejecutar la aplicación. Por ejemplo, el contenido que crea `dotnet publish` solo contiene los archivos binarios de .NET compilados, las imágenes y los archivos .js y .css. Con el tiempo, verá imágenes que contienen paquetes anteriores a la compilación (la compilación del lenguaje intermedio al nativo que se produce en tiempo de ejecución).

Aunque hay varias versiones de las imágenes de .NET Core y ASP.NET Core, todas ellas comparten una o más capas, incluida la capa base. Por tanto, la cantidad de espacio en disco necesaria para almacenar una imagen es pequeña; consiste únicamente en las diferencias entre la imagen personalizada y su imagen base. El resultado es que es rápido extraer la imagen desde el registro.

Al explorar los repositorios de imágenes de .NET en Docker Hub, encontrará varias versiones de imágenes clasificadas o marcadas con etiquetas. Estas etiquetas ayudan a decidir cuál usar, según la versión que necesite, como las de la tabla siguiente:

| Imagen | Comentarios |
|-------|----------|
| mcr.microsoft.com/dotnet/core/aspnet:**3.1** | ASP.NET Core, solo con tiempo de ejecución y las optimizaciones de ASP.NET Core, en Linux y Windows (multiarquitectura) |
| mcr.microsoft.com/dotnet/core/sdk:**3.1** | .NET Core, con los SDK incluidos, en Linux y Windows (multiarquitectura) |

> [!div class="step-by-step"]
> [Anterior](net-container-os-targets.md)
> [Siguiente](../architect-microservice-container-applications/index.md)
