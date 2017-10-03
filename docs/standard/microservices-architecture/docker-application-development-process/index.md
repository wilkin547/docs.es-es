---
title: Proceso de desarrollo de aplicaciones basadas en Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Proceso de desarrollo de aplicaciones basadas en Docker
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: f4c241f463ff1270037c7d66ba39409ca5d9e728
ms.contentlocale: es-es
ms.lasthandoff: 09/05/2017

---
# <a name="development-process-for-docker-based-applications"></a>Proceso de desarrollo de aplicaciones basadas en Docker

*Desarrolle aplicaciones .NET en contenedor de la forma que prefiera, ya sea centradas en el IDE con Visual Studio y Visual Studio Tools para Docker o bien centradas en la CLI o el editor con la CLI de Docker y Visual Studio Code.*

## <a name="development-environment-for-docker-apps"></a>Entorno de desarrollo para aplicaciones de Docker

### <a name="development-tool-choices-ide-or-editor"></a>Opciones de herramientas de desarrollo: IDE o editor

Tanto si quiere un IDE eficaz y completo como si prefiere un editor ligero y ágil, Microsoft dispone de herramientas que puede usar para desarrollar aplicaciones de Docker.

**Visual Studio Tools para Docker**. Si usa Visual Studio 2015, puede instalar el complemento [Visual Studio Tools para Docker](https://marketplace.visualstudio.com/items?itemName=MicrosoftCloudExplorer.VisualStudioToolsforDocker-Preview). Si usa Visual Studio 2017, las herramientas para Docker ya están integradas. En cualquier caso, las herramientas para Docker permiten desarrollar, ejecutar y validar las aplicaciones directamente en el entorno de Docker de destino. Puede presionar F5 para ejecutar y depurar la aplicación (de un solo contenedor o de varios contenedores) directamente en un host de Docker, o bien presionar CTRL+F5 para editar y actualizar la aplicación sin tener que volver a compilar el contenedor. Esta es la opción más sencilla y más eficaz para los desarrolladores de Windows que tienen como destino contenedores de Docker para Linux o Windows.

**Visual Studio Code y la CLI de Docker**. Si prefiere un editor ligero multiplataforma que admita todos los lenguajes de programación, puede usar Microsoft Visual Studio Code (VS Code) y la CLI de Docker. Se trata de un enfoque de desarrollo multiplataforma para Mac, Linux y Windows.

Estos productos proporcionan una experiencia sencilla pero sólida que agiliza el flujo de trabajo del desarrollador. Mediante la instalación de las herramientas de [Docker Community Edition (CE)](https://www.docker.com/community-edition), puede usar una sola CLI de Docker para compilar aplicaciones para Windows y Linux. Además, Visual Studio Code admite extensiones para Docker como IntelliSense para Dockerfiles y tareas de acceso directo para ejecutar comandos de Docker desde el editor.

### <a name="additional-resources"></a>Recursos adicionales

-   **Visual Studio Tools para Docker**
    [*https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4*](https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4)

-   **Visual Studio Code**. Sitio oficial.
    [*https://code.visualstudio.com/download*](https://code.visualstudio.com/download)

-   **Docker Community Edition (CE) para Mac y Windows**
    [*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)

## <a name="net-languages-and-frameworks-for-docker-containers"></a>Lenguajes y marcos de .NET para contenedores de Docker

Como se ha mencionado en secciones anteriores de esta guía, puede usar .NET Framework, .NET Core o el proyecto Mono de código abierto para desarrollar aplicaciones .NET en contenedor de Docker. Puede desarrollar en C\#, F\# o Visual Basic cuando tenga como destino contenedores de Windows o Linux, en función de qué versión de .NET Framework esté en uso. Para obtener más información sobre lenguajes de .NET, vea la entrada de blog [The .NET Language Strategy](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/) (Estrategia de lenguaje de .NET).


>[!div class="step-by-step"]
[Anterior] (../architect-microservice-container-applications/using-azure-service-fabric.md) [Siguiente] (docker-app-development-workflow.md)

