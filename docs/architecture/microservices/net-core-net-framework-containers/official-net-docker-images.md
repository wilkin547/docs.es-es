---
title: Imágenes oficiales de Docker de .NET
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Imágenes de Docker de .NET oficiales
ms.date: 01/13/2021
ms.openlocfilehash: 072e565260bf81c123ee837ccca46fbdf7c67361
ms.sourcegitcommit: 78eb25647b0c750cd80354ebd6ce83a60668e22c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "99065127"
---
# <a name="official-net-docker-images"></a>Imágenes oficiales de Docker de .NET

Las imágenes oficiales de Docker de .NET son imágenes de Docker que Microsoft ha creado y optimizado. Están disponibles públicamente en los repositorios de Microsoft en [Docker Hub](https://hub.docker.com/u/microsoft/). Cada repositorio puede contener varias imágenes, según las versiones de .NET y según el sistema operativo y las versiones (Linux Debian, Linux Alpine, Windows Nano Server, Windows Server Core, etcétera).

Desde .NET Core 2.1, todas las imágenes de .NET Core o versiones posteriores, incluidas las de ASP.NET Core, están disponibles en Docker Hub, en el repositorio de imágenes de .NET <https://hub.docker.com/_/microsoft-dotnet/>.

Desde mayo de 2018, las imágenes de Microsoft [se distribuyen en Microsoft Container Registry](https://azure.microsoft.com/blog/microsoft-syndicates-container-catalog/). El catálogo oficial todavía está disponible, pero únicamente en Docker Hub, y allí encontrará la dirección actualizada para extraer la imagen.

La mayoría de los repositorios de imágenes ofrece un etiquetado exhaustivo con el que es más fácil elegir no solo la versión de un marco concreto, sino también un sistema operativo (distribución de Linux o versión de Windows).

## <a name="net-and-docker-image-optimizations-for-development-versus-production"></a>Optimizaciones de imágenes de .NET y Docker para desarrollo frente a para producción

Al compilar imágenes de Docker para desarrolladores, Microsoft se centró en los siguientes escenarios principales:

- Imágenes que se usan para *desarrollar* y compilar aplicaciones de .NET.

- Imágenes que se usan para *ejecutar* aplicaciones de .NET.

¿Por qué varias imágenes? Al desarrollar, compilar y ejecutar aplicaciones en contenedor, normalmente hay prioridades diferentes. Al proporcionar diferentes imágenes para estas tareas independientes, con Microsoft es más fácil optimizar los procesos independientes de desarrollo, creación e implementación de aplicaciones.

### <a name="during-development-and-build"></a>Durante el desarrollo y la compilación

Durante el desarrollo, lo importante es la velocidad con que se pueden iterar los cambios y la capacidad para depurar los cambios. El tamaño de la imagen no es tan importante como la capacidad de realizar cambios en el código y ver rápidamente los cambios. Algunas herramientas y "contenedores de agente de compilación" usan la imagen de .NET de desarrollo (*mcr.microsoft.com/dotnet/sdk:5.0*) durante el proceso de desarrollo y compilación. Al compilar dentro de un contenedor de Docker, los aspectos importantes son los elementos necesarios para compilar la aplicación. Esto incluye el compilador y cualquier otra dependencia de .NET.

¿Por qué es importante este tipo de imagen de compilación? Esta imagen no se implementa para producción, sino que es una imagen que se usa para compilar el contenido que se coloca en una imagen de producción. Esta imagen se usaría en el entorno de integración continua (CI) o el entorno de compilación al utilizar compilaciones de Docker de varias fases.

### <a name="in-production"></a>En producción

Lo importante en producción es la rapidez con la que se pueden implementar e iniciar los contenedores según una imagen de .NET de producción. Por tanto, la imagen solo en entorno de ejecución basada en *mcr.microsoft.com/dotnet/aspnet:5.0* es pequeña, de modo que puede viajar rápidamente a través de la red desde el registro de Docker hasta los hosts de Docker. El contenido está listo para ejecutarse, lo que agiliza el proceso que va desde iniciar el contenedor hasta procesar los resultados. En el modelo de Docker, no es necesario compilar desde el código C\#, como cuando se ejecuta dotnet build o dotnet publish al usar el contenedor de compilación.

En esta imagen optimizada solo se colocan los archivos binarios y otros contenidos necesarios para ejecutar la aplicación. Por ejemplo, el contenido que crea `dotnet publish` solo contiene los archivos binarios de .NET compilados, las imágenes y los archivos .js y .css. Con el tiempo, verá imágenes que contienen paquetes anteriores a la compilación (la compilación del lenguaje intermedio al nativo que se produce en tiempo de ejecución).

Aunque hay varias versiones de las imágenes de .NET y ASP.NET Core, todas ellas comparten una o más capas, incluida la capa base. Por tanto, la cantidad de espacio en disco necesaria para almacenar una imagen es pequeña; consiste únicamente en las diferencias entre la imagen personalizada y su imagen base. El resultado es que es rápido extraer la imagen desde el registro.

Al explorar los repositorios de imágenes de .NET en Docker Hub, encontrará varias versiones de imágenes clasificadas o marcadas con etiquetas. Estas etiquetas ayudan a decidir cuál usar, según la versión que necesite, como las de la tabla siguiente:

| Imagen | Comentarios |
|-------|----------|
| mcr.microsoft.com/dotnet/aspnet:**5.0** | ASP.NET Core, solo con tiempo de ejecución y las optimizaciones de ASP.NET Core, en Linux y Windows (multiarquitectura) |
| mcr.microsoft.com/dotnet/sdk:**5.0** | .NET 5, con los SDK incluidos, en Linux y Windows (arquitectura múltiple) |

> [!div class="step-by-step"]
> [Anterior](net-container-os-targets.md)
> [Siguiente](../architect-microservice-container-applications/index.md)
