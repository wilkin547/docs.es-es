---
title: Entorno de desarrollo para aplicaciones de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 3da7816127982c3657129561975eed6d1f5aad5a
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104512"
---
# <a name="development-environment-for-docker-apps"></a>Entorno de desarrollo para aplicaciones de Docker

## <a name="development-tools-choices-ide-or-editor"></a>Opciones de herramientas de desarrollo: IDE o editor

Sin importar si prefiere un IDE eficaz y completa o un editor ligero y ágil, Microsoft tiene cubierto en cuanto a desarrollar aplicaciones de Docker.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code y la CLI de Docker (las herramientas multiplataforma para Mac, Linux y Windows)

Si lo prefiere, un editor ligero y multiplataforma admite cualquier lenguaje de programación, puede utilizar código de Visual Studio y la CLI de Docker. Estos productos proporcionan una experiencia sencilla pero sólida, lo cual resulta esencial para optimizar el flujo de trabajo de desarrollador. Instalando "Docker para Mac" o "Docker para Windows" (entorno de desarrollo), los desarrolladores de Docker pueden usar una sola CLI de Docker para crear aplicaciones para Windows o Linux (entorno de tiempo de ejecución). Además, código de Visual Studio admite extensiones de Docker con IntelliSense para los archivos Dockerfile y tareas de accesos directos ejecutar comandos de Docker desde el editor.

> [!NOTE]
> Para descargar el código de Visual Studio, vaya a <https://code.visualstudio.com/download>.

Para descargar Docker para Mac y Windows, vaya a <https://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools"></a>Visual Studio con herramientas de Docker

Cuando se usa Visual Studio 2015 puede instalar las herramientas de complemento "Herramientas de Docker para Visual Studio". Para Visual Studio de 2017, herramientas de Docker incluyen incorporados ya. En ambos casos que puede desarrollar, ejecutar y validar las aplicaciones directamente en el entorno de Docker elegido. F5 (contenedor único o varios contenedores) la aplicación directamente en una Docker hospedar con la depuración, o presione Ctrl + F5 para editar y actualizar la aplicación sin tener que volver a generar el contenedor. Esta es la opción más sencilla y más eficaces para los desarrolladores de Windows para crear contenedores de Docker para Linux o Windows.

> [!NOTE]
> Para descargar herramientas de Docker para Visual Studio, vaya a <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.

## <a name="language-and-framework-choices"></a>Opciones de idioma y el marco de trabajo

Puede desarrollar aplicaciones de Docker y herramientas de Microsoft con lenguajes más modernos. La siguiente es una lista inicial, pero no está limitado a él:

-   .NET core y ASP.NET Core
-   Node.js
-   Golang
-   Java
-   Ruby
-   Plantillas de

Básicamente, puede usar cualquier lenguaje moderno admitido por Docker en Linux o Windows.


>[!div class="step-by-step"]
[Anterior](orchestrate-high-scalability-availability.md)
[Siguiente](docker-apps-inner-loop-workflow.md)
