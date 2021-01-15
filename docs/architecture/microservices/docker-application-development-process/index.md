---
title: Proceso de desarrollo de aplicaciones basadas en Docker
description: Obtenga una introducción general de las opciones para desarrollar aplicaciones basadas en Docker. Elija entre Visual Studio para Windows, Visual Studio para Mac o Visual Studio Code para la compatibilidad con varias plataformas (Windows, macOS y Linux).
ms.date: 01/13/2021
ms.openlocfilehash: 3a4f4078e745c52e8eca46473668e3319917bfd2
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188301"
---
# <a name="development-process-for-docker-based-applications"></a>Proceso de desarrollo de aplicaciones basadas en Docker

*Desarrolle aplicaciones .NET en contenedor de la forma que prefiera, ya sea centradas en el entorno de desarrollo integrado (IDE) con Visual Studio y Visual Studio Tools para Docker o bien centradas en la CLI o el editor con la CLI de Docker y Visual Studio Code.*

## <a name="development-environment-for-docker-apps"></a>Entorno de desarrollo para aplicaciones de Docker

### <a name="development-tool-choices-ide-or-editor"></a>Opciones de herramientas de desarrollo: IDE o editor

Tanto si quiere un IDE eficaz y completo como si prefiere un editor ligero y ágil, Microsoft dispone de herramientas que puede usar para desarrollar aplicaciones de Docker.

**Visual Studio (para Windows).** El desarrollo de aplicaciones .NET 5 basadas en Docker con Visual Studio requiere la versión 16.4 o posterior de Visual Studio 2019. Visual Studio 2019 incluye herramientas para Docker ya integradas. Las herramientas de Docker permiten desarrollar, ejecutar y validar las aplicaciones directamente en el entorno de Docker de destino. Puede presionar F5 para ejecutar y depurar la aplicación (de un solo contenedor o de varios contenedores) directamente en un host de Docker, o bien presionar CTRL+F5 para editar y actualizar la aplicación sin tener que volver a compilar el contenedor. Este IDE es la opción de desarrollo más eficaz para aplicaciones basadas en Docker.

**Visual Studio para Mac.** Se trata de un IDE, la evolución de Xamarin Studio, que se ejecuta en macOS. Para el desarrollo en .NET 5, se requiere la versión 8.4 o posterior. Esta herramienta también debe ser la opción preferida para los desarrolladores que trabajan en equipos macOS y que también quieran usar un IDE eficaz.

**Visual Studio Code y la CLI de Docker**. Si prefiere un editor ligero y multiplataforma que admita todos los lenguajes de programación, puede usar Visual Studio Code y la CLI de Docker. Este IDE cuenta con un enfoque de desarrollo multiplataforma para macOS, Linux y Windows. Además, Visual Studio Code admite extensiones para Docker como IntelliSense para Dockerfiles y tareas de acceso directo para ejecutar comandos de Docker desde el editor.

Mediante la instalación de [Docker Desktop Community Edition (CE)](https://hub.docker.com/search/?type=edition&offering=community), puede usar una sola CLI de Docker para compilar aplicaciones para Windows y Linux.

### <a name="additional-resources"></a>Recursos adicionales

- **Visual Studio**. Sitio oficial. \
  [https://visualstudio.microsoft.com/vs/](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)

- **Visual Studio Code**. Sitio oficial. \
  <https://code.visualstudio.com/download>

- **Docker Desktop for Windows Community Edition (CE)**  \
  [https://hub.docker.com/editions/community/docker-ce-desktop-windows](https://hub.docker.com/editions/community/docker-ce-desktop-windows)

- **Docker Desktop for Mac Community Edition (CE)**  \
  [https://hub.docker.com/editions/community/docker-ce-desktop-mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac)

## <a name="net-languages-and-frameworks-for-docker-containers"></a>Lenguajes y marcos de .NET para contenedores de Docker

Como se ha mencionado en secciones anteriores de esta guía, puede usar .NET Framework, .NET 5 o el proyecto Mono de código abierto para desarrollar aplicaciones .NET en contenedor de Docker. Puede desarrollar en C\#, F\# o Visual Basic cuando tenga como destino contenedores de Windows o Linux, en función de qué versión de .NET Framework esté en uso. Para obtener más información sobre lenguajes de .NET, vea la entrada de blog [The .NET Language Strategy](https://devblogs.microsoft.com/dotnet/the-net-language-strategy/) (Estrategia de lenguaje de .NET).

>[!div class="step-by-step"]
>[Anterior](../architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)
>[Siguiente](docker-app-development-workflow.md)
