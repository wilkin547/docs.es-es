---
title: Entorno de desarrollo para aplicaciones de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 471b52fd577e5560bd93e6da50f2032d63eb2e6f
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152421"
---
# <a name="development-environment-for-docker-apps"></a>Entorno de desarrollo para aplicaciones de Docker

## <a name="development-tools-choices-ide-or-editor"></a>Opciones de herramientas de desarrollo: Editor o IDE

Sin importar si lo prefiere, un IDE eficaz y completo o un editor ligero y ágil, Microsoft le puede ayudar en cuanto a desarrollar aplicaciones de Docker.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code y CLI de Docker (Herramientas multiplataforma para Mac, Linux y Windows)

Si prefiere un editor ligero y multiplataforma que admiten cualquier lenguaje de desarrollo, puede usar Visual Studio Code y CLI de Docker. Estos productos proporcionan una experiencia sencilla y sólida que es fundamental para optimizar el flujo de trabajo de desarrollador. Al instalar "Docker para Mac" o "Docker para Windows" (entorno de desarrollo), los desarrolladores de Docker pueden utilizar una sola CLI de Docker para crear aplicaciones para Windows o Linux (entorno de tiempo de ejecución). Además, Visual Studio Code admite extensiones para Docker con IntelliSense para Dockerfiles y tareas de acceso directo ejecutar comandos de Docker desde el editor.

> [!NOTE]
> Para descargar el código de Visual Studio, vaya a <https://code.visualstudio.com/download>.

Para descargar Docker para Mac y Windows, vaya a <https://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools"></a>Visual Studio con las herramientas de Docker

Cuando se usa Visual Studio 2015 puede instalar las herramientas de complemento "Herramientas de Docker para Visual Studio". Para Visual Studio 2017, las herramientas de Docker están integradas en ya. En ambos casos que puede desarrollar, ejecutar y validar sus aplicaciones directamente en el entorno de Docker elegido. F5 hospedar con la depuración de la aplicación (único contenedor o varios contenedores) directamente en Docker, o presione Ctrl + F5 para editar y actualizar la aplicación sin tener que recompilar el contenedor. Esta es la opción más sencilla y más eficaces para los desarrolladores de Windows para crear contenedores de Docker para Linux o Windows.

> [!NOTE]
> Para descargar las herramientas de Docker para Visual Studio, vaya a <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.

## <a name="language-and-framework-choices"></a>Opciones de idioma y marco de trabajo

Puede desarrollar aplicaciones de Docker y las herramientas de Microsoft con los lenguajes más modernos. La siguiente es una lista inicial, pero no está limitado a él:

-   .NET Core y ASP.NET Core
-   Node.js
-   Golang
-   Java
-   Ruby
-   Python

Básicamente, puede usar cualquier lenguaje moderno compatible con Docker en Linux o Windows.

>[!div class="step-by-step"]
>[Anterior](orchestrate-high-scalability-availability.md)
>[Siguiente](docker-apps-inner-loop-workflow.md)