---
title: Visual Studio Tools para Docker en Windows
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: cd140c12ef4a0187cce096e013937d5c98cd4b39
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170800"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>Con Visual Studio Tools para Docker (Visual Studio en Windows)

Visual Studio Tools para el flujo de trabajo de desarrollo de Docker es similar al uso de Visual Studio Code y CLI de Docker (se basa en la misma CLI de Docker). Visual Studio Tools para Docker facilita aún más empezar a trabajar, simplifica el proceso y proporciona mayor productividad para la compilación, ejecución y crear tareas. Ejecutar y depurar los contenedores a través de acciones simples, como **F5** y **Ctrl**+**F5**.

> [!NOTE]
> En este artículo se aplica a Visual Studio en Windows y no en Visual Studio para Mac.

## <a name="configure-your-local-environment"></a>Configurar el entorno local

Con las últimas versiones de Docker para Windows ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)), el programa de instalación sencilla facilita la tarea desarrollar aplicaciones de Docker.

Compatibilidad con docker se incluye en Visual Studio 2017. Descargar Visual Studio 2017 aquí: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

## <a name="use-docker-tools-in-visual-studio-2017"></a>Use herramientas de Docker en Visual Studio 2017

Hay dos niveles de compatibilidad con Docker que puede agregar a un proyecto. En los proyectos de aplicación web de .NET Core, puede agregar simplemente un *Dockerfile* archivo al proyecto habilitando la compatibilidad con Docker. El siguiente nivel es la compatibilidad con orquestador de contenedores, que agrega un *Dockerfile* al proyecto (si aún no existe) y un *docker-compose.yml* archivo en el nivel de solución.

El **agregar** > **compatibilidad con Docker** y **agregar** > **la compatibilidad con el orquestador de contenedor** son de comandos ubicado en el menú contextual (o el menú contextual) del nodo de proyecto para un proyecto de aplicación web en **el Explorador de soluciones**, tal y como se muestra en la figura 4-26:

![Agregar la opción de menú de la compatibilidad con Docker en Visual Studio](media/add-docker-support-menu.png)

Figura 4-26: agregar compatibilidad con Docker a un proyecto de Visual Studio 2017

### <a name="add-docker-support"></a>Agregar compatibilidad con Docker

Puede agregar compatibilidad con Docker a un proyecto de aplicación web de .NET Core existente seleccionando **agregar** > **Docker admite** en **el Explorador de soluciones**. También puede habilitar compatibilidad con Docker durante la creación del proyecto seleccionando **habilitar Docker admite** en el **nueva aplicación Web de ASP.NET Core** cuadro de diálogo que se abre al hacer clic en **Aceptar** en el **nuevo proyecto** cuadro de diálogo, como se muestra en la figura 4-27.

![Habilitar compatibilidad con Docker para la nueva aplicación web de ASP.NET Core en Visual Studio](./media/enable-docker-support-visual-studio.png)

Figura 4-27: habilitar la compatibilidad con Docker durante la creación del proyecto en Visual Studio 2017

Al agregar o habilitar la compatibilidad con Docker, Visual Studio agrega un *Dockerfile* archivo al proyecto.

> [!NOTE]
> Cuando se habilita la compatibilidad con Docker Compose durante la creación del proyecto para un proyecto de aplicación web de .NET Framework (no un proyecto .NET Core web app) tal como se muestra en la figura 4-28, también se agrega compatibilidad con orquestador de contenedores.
>
> ![Habilitar Docker compose de soporte técnico para un proyecto de aplicación web de .NET Framework](media/enable-docker-compose-support.png)

> Figura 4-28: habilitar la compatibilidad con Docker Compose en un proyecto de aplicación web de .NET Framework en Visual Studio 2017

### <a name="add-container-orchestrator-support"></a>Agregar compatibilidad con orquestador de contenedores

Cuando desea crear una solución de varios contenedores, agregar compatibilidad con orquestador de contenedores a los proyectos. Cuando se agrega compatibilidad con orquestador de contenedores, Visual Studio agrega un *Dockerfile* para el proyecto (si aún no existe) y un elemento global *docker-compose.yml* archivo en el nivel de solución. Esto le permite ejecutar y depurar un grupo de contenedores (una solución completa) al mismo tiempo si se definen en el mismo *docker-compose.yml* archivo. Si *docker-compose.yml* ya existe, Visual Studio agrega simplemente las líneas de código de configuración necesarias.

Después de agregar compatibilidad con la orquestación de contenedor para el proyecto, verá un archivo Dockerfile que se agrega al proyecto y un **docker-compose** carpeta agregada a la solución en **el Explorador de soluciones**, como se muestra en la figura 4-29:

![Archivos de docker en el Explorador de soluciones en Visual Studio](media/docker-support-solution-explorer.png)

Figura 4-29: archivos de Docker en el Explorador de soluciones en Visual Studio 2017

**Obtener más información:** para obtener más información sobre la implementación de los servicios y el uso de Visual Studio Tools para Docker, lea los artículos siguientes:

Compilar, depurar, actualizar y actualizar aplicaciones en un contenedor de Docker local: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

Implementar un contenedor de Docker de ASP.NET Core en un registro de contenedor: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

>[!div class="step-by-step"]
[Anterior](docker-apps-inner-loop-workflow.md)
[Siguiente](set-up-windows-containers-with-powershell.md)