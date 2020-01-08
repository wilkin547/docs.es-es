---
title: Proceso de desarrollo de aplicaciones basadas en Docker
description: Obtenga una introducción general de las opciones para desarrollar aplicaciones basadas en Docker. Elija entre Visual Studio para Windows, Visual Studio para Mac o Visual Studio Code para la compatibilidad con varias plataformas (Windows, macOS y Linux).
ms.date: 09/27/2018
ms.openlocfilehash: 95e940371f4dbef3b3a8f327c13acbbc55ff29ef
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337697"
---
# <a name="development-process-for-docker-based-applications"></a>Proceso de desarrollo de aplicaciones basadas en Docker

*Desarrolle aplicaciones .NET en contenedor de la forma que prefiera, ya sea centradas en el IDE con Visual Studio y Visual Studio Tools para Docker o bien centradas en la CLI o el editor con la CLI de Docker y Visual Studio Code.*

## <a name="development-environment-for-docker-apps"></a>Entorno de desarrollo para aplicaciones de Docker

### <a name="development-tool-choices-ide-or-editor"></a>Opciones de herramientas de desarrollo: IDE o editor

Tanto si quiere un IDE eficaz y completo como si prefiere un editor ligero y ágil, Microsoft dispone de herramientas que puede usar para desarrollar aplicaciones de Docker.

**Visual Studio (para Windows).** Cuando desarrolle aplicaciones basadas en Docker con Visual Studio, se recomienda usar la versión 15.7 de Visual Studio 2017 o versiones posteriores, que incluyen herramientas de Docker ya integradas. Las herramientas de Docker permiten desarrollar, ejecutar y validar las aplicaciones directamente en el entorno de Docker de destino. Puede presionar F5 para ejecutar y depurar la aplicación (de un solo contenedor o de varios contenedores) directamente en un host de Docker, o bien presionar CTRL+F5 para editar y actualizar la aplicación sin tener que volver a compilar el contenedor. Se trata de la opción de desarrollo más eficaz para aplicaciones basadas en Docker.

**Visual Studio para Mac.** Es un IDE, evolución de Xamarin Studio, que se ejecuta en macOS y es compatible con Docker desde mediados de 2017. Debe ser la opción preferida para los desarrolladores que trabajan en equipos macOS y que también quieran usar un IDE eficaz.

**Visual Studio Code y la CLI de Docker**. Si prefiere un editor ligero multiplataforma que admita todos los lenguajes de programación, puede usar Microsoft Visual Studio Code (VS Code) y la CLI de Docker. Se trata de un enfoque de desarrollo multiplataforma para macOS, Linux y Windows. Además, Visual Studio Code admite extensiones para Docker como IntelliSense para Dockerfiles y tareas de acceso directo para ejecutar comandos de Docker desde el editor.

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

Como se ha mencionado en secciones anteriores de esta guía, puede usar .NET Framework, .NET Core o el proyecto Mono de código abierto para desarrollar aplicaciones .NET en contenedor de Docker. Puede desarrollar en C\#, F\# o Visual Basic cuando tenga como destino contenedores de Windows o Linux, en función de qué versión de .NET Framework esté en uso. Para obtener más información sobre lenguajes de .NET, vea la entrada de blog [The .NET Language Strategy](https://devblogs.microsoft.com/dotnet/the-net-language-strategy/) (Estrategia de lenguaje de .NET).

>[!div class="step-by-step"]
>[Anterior](../architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)
>[Siguiente](docker-app-development-workflow.md)
