---
title: Entorno de desarrollo para aplicaciones de Docker
description: Familiarícese con las opciones de herramienta de desarrollo más importantes que admiten el ciclo de vida de desarrollo de Docker.
ms.date: 02/15/2019
ms.openlocfilehash: 0f71ffa5e6870f45908e4def6577120a17ec744c
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641421"
---
# <a name="development-environment-for-docker-apps"></a>Entorno de desarrollo para aplicaciones de Docker

## <a name="development-tools-choices-ide-or-editor"></a>Opciones de herramientas de desarrollo: IDE o editor

Sin importar si lo prefiere, un IDE eficaz y completo o un editor ligero y ágil, Microsoft le puede ayudar en cuanto a desarrollar aplicaciones de Docker.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code y CLI de Docker (Herramientas multiplataforma para Mac, Linux y Windows)

Si prefiere un editor ligero y multiplataforma que admiten cualquier lenguaje de desarrollo, puede usar Visual Studio Code y CLI de Docker. Estos productos proporcionan una experiencia sencilla y sólida que es fundamental para optimizar el flujo de trabajo de desarrollador. Al instalar "Docker para Mac" o "Docker para Windows" (entorno de desarrollo), los desarrolladores de Docker pueden utilizar una sola CLI de Docker para crear aplicaciones para Windows o Linux (entorno de tiempo de ejecución). Además, Visual Studio Code admite extensiones para Docker con IntelliSense para Dockerfiles y tareas de acceso directo ejecutar comandos de Docker desde el editor.

> [!NOTE]
>
> Para descargar el código de Visual Studio, vaya a <https://code.visualstudio.com/download>.
>
> Para descargar Docker para Mac y Windows, vaya a <https://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a>Visual Studio con las herramientas de Docker (máquina de desarrollo de Windows)

Se recomienda usar Visual Studio 2017 (o posterior) con las herramientas integradas de Docker habilitado. Con Visual Studio, puede desarrollar, ejecutar y validar sus aplicaciones directamente en el entorno de Docker elegido. Presione F5 para depurar la aplicación (único contenedor o varios contenedores) directamente en un host de Docker, o presione Ctrl + F5 para editar y actualizar la aplicación sin tener que recompilar el contenedor. Es la opción más sencilla y más eficaces para desarrolladores de Windows crear contenedores de Docker para Linux o Windows.

### <a name="visual-studio-for-mac-mac-development-machine"></a>Visual Studio para Mac (máquina de desarrollo de Mac)

Puede usar [Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) al desarrollar aplicaciones basadas en Docker. Visual Studio para Mac ofrece un IDE más rico en comparación con el código de Visual Studio para Mac.

## <a name="language-and-framework-choices"></a>Opciones de idioma y marco de trabajo

Puede desarrollar aplicaciones de Docker con herramientas de Microsoft con los lenguajes más modernos. La siguiente es una lista inicial, pero no está limitado a él:

- .NET Core y ASP.NET Core
- Node.js
- Ir
- Java
- Ruby
- Python

Básicamente, puede usar cualquier lenguaje moderno compatible con Docker en Linux o Windows.

>[!div class="step-by-step"]
>[Anterior](deploy-azure-kubernetes-service.md)
>[Siguiente](docker-apps-inner-loop-workflow.md)
