---
title: Visual Studio Tools para Docker en Windows
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: 79e9b5cc9bac317a368583013abbc5124ef2c9ac
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151218"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>Con Visual Studio Tools para Docker (Visual Studio en Windows)

Visual Studio Tools para el flujo de trabajo de desarrollo de Docker es similar al flujo de trabajo cuando se usa Visual Studio Code y CLI de Docker. De hecho, se basa en la misma CLI de Docker, pero es más fácil empezar a trabajar, simplifica el proceso y proporciona mayor productividad para la compilación, ejecución y crear tareas. Ejecutar y depurar los contenedores a través de acciones simples, como **F5** y **Ctrl**+**F5**. Con la compatibilidad con la orquestación de contenedor opcional, además de poder ejecutar y depurar un único contenedor, puede ejecutar y depurar un grupo de contenedores (una solución completa) al mismo tiempo.

> [!NOTE]
> En este artículo se aplica a Visual Studio en Windows y no en Visual Studio para Mac.

## <a name="configure-your-local-environment"></a>Configurar el entorno local

Con las últimas versiones de Docker para Windows ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)), el programa de instalación sencilla facilita la tarea desarrollar aplicaciones de Docker.

Compatibilidad con docker se incluye en Visual Studio 2017. Descargar Visual Studio 2017 aquí: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

## <a name="use-docker-tools-in-visual-studio-2017"></a>Use herramientas de Docker en Visual Studio 2017

Hay dos niveles de compatibilidad con Docker que puede agregar a un proyecto. En los proyectos de aplicación web de .NET Core, puede agregar simplemente un *Dockerfile* archivo al proyecto habilitando la compatibilidad con Docker. El siguiente nivel es el soporte técnico de orquestación de contenedor, que agrega un *Dockerfile* al proyecto (si aún no existe) y un *docker-compose.yml* archivo en el nivel de solución. Compatibilidad con orquestación de contenedores, a través de Docker Compose, se agrega de forma predeterminada en las versiones de Visual Studio 2017 15.7 o una versión anteriores. Compatibilidad con la orquestación de contenedor es una característica opcional en las versiones de Visual Studio 2017 15,8 o versiones posteriores, en cuyo caso Docker Compose y Service Fabric se admiten.

El **agregar** > **compatibilidad con Docker** y **agregar** > **soporte técnico de orquestación de contenedores** son de comandos ubicado en el menú contextual (o el menú contextual) del nodo de proyecto para un proyecto de aplicación web en **el Explorador de soluciones**, tal y como se muestra en la figura 4-26:

![Agregar la opción de menú de la compatibilidad con Docker en Visual Studio](media/add-docker-support-menu.png)

Figura 4-26: Agregar compatibilidad con Docker a un proyecto de Visual Studio 2017

### <a name="add-docker-support"></a>Agregar compatibilidad con Docker

Puede agregar compatibilidad con Docker a un proyecto de aplicación web de .NET Core existente seleccionando **agregar** > **Docker admite** en **el Explorador de soluciones**. También puede habilitar compatibilidad con Docker durante la creación del proyecto seleccionando **habilitar Docker admite** en el **nueva aplicación Web de ASP.NET Core** cuadro de diálogo que se abre al hacer clic en **Aceptar** en el **nuevo proyecto** cuadro de diálogo, como se muestra en la figura 4-27.

![Habilitar compatibilidad con Docker para la nueva aplicación web de ASP.NET Core en Visual Studio](./media/enable-docker-support-visual-studio.png)

Figura 4-27: Habilitar la compatibilidad con Docker durante la creación del proyecto en Visual Studio 2017

Al agregar o habilitar la compatibilidad con Docker, Visual Studio agrega un *Dockerfile* archivo al proyecto.

> [!NOTE]
> Cuando se habilita la compatibilidad con Docker Compose durante la creación del proyecto para un proyecto de aplicación web de .NET Framework (no un proyecto .NET Core web app) tal como se muestra en la figura 4-28, también se agrega compatibilidad con la orquestación de contenedor.
>
> ![Habilitar Docker compose de soporte técnico para un proyecto de aplicación web de .NET Framework](media/enable-docker-compose-support.png)

> Figura 4-28: Habilitar la compatibilidad con Docker Compose en un proyecto de aplicación web de .NET Framework en Visual Studio 2017

### <a name="add-container-orchestration-support"></a>Agregar compatibilidad con la orquestación de contenedor

Cuando desea crear una solución de varios contenedores, agregar compatibilidad con la orquestación de contenedor a sus proyectos. Esto le permite ejecutar y depurar un grupo de contenedores (una solución completa) al mismo tiempo si se definen en el mismo *docker-compose.yml* archivo.

Para agregar compatibilidad con la orquestación de contenedor, haga doble clic en el nodo de solución o proyecto en **el Explorador de soluciones**y elija **agregar** > **contenedoradmitelaorquestación**. A continuación, elija **Docker Compose** o **Service Fabric** para administrar los contenedores.

Después de agregar compatibilidad con la orquestación de contenedor para el proyecto, verá un archivo Dockerfile que se agrega al proyecto y un **docker-compose** carpeta agregada a la solución en **el Explorador de soluciones**, como se muestra en la figura 4-29:

![Archivos de docker en el Explorador de soluciones en Visual Studio](media/docker-support-solution-explorer.png)

Figura 4-29: Archivos de docker en el Explorador de soluciones en Visual Studio 2017

Si *docker-compose.yml* ya existe, Visual Studio agrega simplemente las líneas de código de configuración necesarias.

## <a name="configure-docker-tools"></a>Configurar las herramientas de Docker

En el menú principal, elija **herramientas** > **opciones**y expanda **herramientas de contenedor** > **configuración**. La configuración de las herramientas de contenedor aparece.

![](./media/visual-studio-docker-tools-options.png)

Figura 4-30: Opciones de herramientas de docker

En la tabla siguiente puede ayudarle a decidir cómo establecer estas opciones.

| nombre | Configuración predeterminada | Se aplica a | Descripción |
| -----|:---------------:|:----------:| ----------- |
| Extraiga automáticamente imágenes de Docker necesarias al cargar el proyecto | Activado | Docker Compose | Para aumentar el rendimiento, al cargar los proyectos, Visual Studio se iniciará una operación de extracción de Docker en segundo plano para que cuando esté listo para ejecutar el código, ya se descarga la imagen o en el proceso de descarga. Si simplemente está cargando proyectos y código de exploración, puede desactivar esta opción para evitar la descarga de imágenes de contenedor que no es necesario. |
| Iniciar automáticamente los contenedores en segundo plano | Activado | Docker Compose | Nuevo para aumentar el rendimiento, Visual Studio crea un contenedor con montajes de volumen listo al compilar y ejecutar el contenedor. Si desea controlar cuando se crea el contenedor, desactivar esta opción. |
| Cerrar automáticamente de contenedores de interrupción en la solución | Activado | Docker Compose | Desactivar esta opción si desea que los contenedores de la solución seguir ejecutándose después de cerrar la solución o cerrar Visual Studio. |
| No preguntar para confiar en certificado SSL de localhost | Desactivado | Proyectos de ASP.NET Core 2.1 | Si el certificado SSL de localhost no es de confianza, Visual Studio le pedirá cada vez que ejecute el proyecto, a menos que se activa esta casilla. |

> [!WARNING]
> Si el certificado SSL de localhost no es de confianza y la casilla para suprimir la solicitud, a continuación, las solicitudes HTTPS web pueden producir un error en tiempo de ejecución en su aplicación o servicio. En ese caso, desactive la **no preguntar** checkbox, ejecute el proyecto e indicar confianza en el símbolo del sistema.

**Obtener más información:** para obtener más información sobre la implementación de los servicios y el uso de Visual Studio Tools para Docker, lea los artículos siguientes:

Compilar, depurar, actualizar y actualizar aplicaciones en un contenedor de Docker local: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

Implementar un contenedor de Docker de ASP.NET Core en un registro de contenedor: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

>[!div class="step-by-step"]
>[Anterior](docker-apps-inner-loop-workflow.md)
>[Siguiente](set-up-windows-containers-with-powershell.md)