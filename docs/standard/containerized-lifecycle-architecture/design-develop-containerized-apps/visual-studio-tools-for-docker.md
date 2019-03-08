---
title: Visual Studio Tools para Docker en Windows
description: Familiarícese con las herramientas de Docker disponibles en Visual Studio 2017 versión 15.7 y versiones posterior.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 78ea3e553e4e449b307bc3585ed66fa48d2c0d8e
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57680365"
---
# <a name="use-docker-tools-in-visual-studio-2017-on-windows"></a>Use herramientas de Docker en Visual Studio 2017 en Windows

El flujo de trabajo de desarrollador al usar las herramientas de Docker que se incluye en Visual Studio 2017 versión 15.7 y versiones posterior, es similar a usar Visual Studio Code y CLI de Docker (de hecho, se basa en la misma CLI de Docker), pero es más fácil empezar a trabajar, se simplifica el proceso, y Proporciona una mayor productividad para la compilación, ejecución y crear tareas. También puede ejecutar y depurar los contenedores a través de la habitual `F5` y `Ctrl+F5` claves desde Visual Studio. Incluso puede depurar una solución completa si sus contenedores se definen en el mismo `docker-compose.yml` archivo en el nivel de solución.

## <a name="configure-your-local-environment"></a>Configurar el entorno local

Con las últimas versiones de Docker para Windows, es más fácil que nunca para desarrollar aplicaciones de Docker porque el programa de instalación es sencilla, como se explica en las siguientes referencias.

> [! INFORMACIÓN] para más información acerca de cómo instalar Docker para Windows, vaya a (<https://docs.docker.com/docker-for-windows/>).

## <a name="docker-support-in-visual-studio-2017"></a>Compatibilidad con docker en Visual Studio 2017

Hay dos niveles de compatibilidad con Docker que puede agregar a un proyecto. En los proyectos de ASP.NET Core, puede agregar simplemente un `Dockerfile` archivo al proyecto habilitando la compatibilidad con Docker. El siguiente nivel es el soporte técnico de orquestación de contenedor, que agrega un `Dockerfile` al proyecto (si aún no existe) y un `docker-compose.yml` archivo en el nivel de solución. Compatibilidad con orquestación de contenedores, a través de Docker Compose, se agrega de forma predeterminada en las versiones de Visual Studio 2017 15.0 a 15.7. Compatibilidad con la orquestación de contenedor es una característica opcional en las versiones de Visual Studio 2017 15,8 o posteriores. Versión 15,8 una posterior admite Docker Compose y Service Fabric.

El **Agregar > compatibilidad con Docker** y **Agregar > compatibilidad con el contenedor de orquestador** los comandos se encuentran en el menú contextual (o el menú contextual) del nodo de proyecto para un proyecto de ASP.NET Core en  **El Explorador de soluciones**, como se muestra en la figura 4-31:

![Agregar la opción de menú de la compatibilidad con Docker en Visual Studio](./media/add-docker-support-menu.png)

**Figura 4-31**. Agregar compatibilidad con Docker a un proyecto de Visual Studio 2017

### <a name="add-docker-support"></a>Agregar compatibilidad con Docker

Puede agregar compatibilidad con Docker a un proyecto de ASP.NET Core existente seleccionando **agregar** > **Docker admite** en **el Explorador de soluciones**. También puede habilitar compatibilidad con Docker durante la creación del proyecto seleccionando **habilitar Docker admite** en el **nueva aplicación Web de ASP.NET Core** cuadro de diálogo que se abre al hacer clic en **Aceptar** en el **nuevo proyecto** cuadro de diálogo, como se muestra en la figura 4-32.

![Habilitar compatibilidad con Docker para la nueva aplicación web de ASP.NET Core en Visual Studio](./media/enable-docker-support-visual-studio.png)

**Figura 4-32**. Habilitar la compatibilidad con Docker durante la creación del proyecto en Visual Studio 2017

Al agregar o habilitar la compatibilidad con Docker, Visual Studio agrega un *Dockerfile* archivo al proyecto.

> [!NOTE]
> Cuando se habilita la compatibilidad con Docker Compose durante la creación del proyecto para un proyecto ASP.NET (.NET Framework, no en un proyecto .NET Core) tal como se muestra en la figura 4-33, también se agrega compatibilidad con la orquestación de contenedor.

![Habilitar Docker compose de soporte técnico para un proyecto de ASP.NET](media/enable-docker-compose-support.png)

**Figura 4-33**. Habilitar la compatibilidad con Docker Compose para un proyecto de ASP.NET en Visual Studio 2017

### <a name="add-container-orchestration-support"></a>Agregar compatibilidad con la orquestación de contenedor

Cuando desea crear una solución de varios contenedor, agregar compatibilidad con la orquestación de contenedor a sus proyectos. Esto le permite ejecutar y depurar un grupo de contenedores (una solución completa) al mismo tiempo si se definen en el mismo *docker-compose.yml* archivo.

Para agregar compatibilidad con la orquestación de contenedor, haga doble clic en el nodo de solución o proyecto en **el Explorador de soluciones**y elija **Agregar > soporte técnico de orquestación de contenedor**. A continuación, elija **Docker Compose** o **Service Fabric** para administrar los contenedores.

Después de agregar compatibilidad con la orquestación de contenedor para el proyecto, verá un archivo Dockerfile que se agrega al proyecto y un **docker-compose** carpeta agregada a la solución en **el Explorador de soluciones**, como se muestra en la figura 4-34:

![Archivos de docker en el Explorador de soluciones en Visual Studio](media/docker-support-solution-explorer.png)

**Figura 4-34**. Archivos de docker en el Explorador de soluciones en Visual Studio 2017

Si *docker-compose.yml* ya existe, Visual Studio agrega simplemente las líneas de código de configuración necesarias.

## <a name="configure-docker-tools"></a>Configurar las herramientas de Docker

En el menú principal, elija **Herramientas > opciones**y expanda **contenedor Herramientas > opciones**. La configuración de las herramientas de contenedor aparece.

![Docker en Visual Studio herramientas opciones, que muestra: Extraiga automáticamente imágenes de Docker necesarias al cargar el proyecto, iniciar automáticamente los contenedores en segundo plano, terminar automáticamente los contenedores en Cerrar solución y no preguntar para confiar en certificado SSL.](./media/visual-studio-docker-tools-options.png)

**Figura 4-35**. Opciones de herramientas de docker

En la tabla siguiente puede ayudarle a decidir cómo establecer estas opciones.

| nombre | Configuración predeterminada | Se aplica a | Descripción |
| -----|:---------------:|:----------:| ----------- |
| Extraiga automáticamente imágenes de Docker necesarias al cargar el proyecto | Activado | Docker Compose | Para aumentar el rendimiento al cargar los proyectos de Visual Studio se iniciará una operación de extracción de Docker en segundo plano para que cuando esté listo para ejecutar el código, ya se descarga la imagen o en el proceso de descarga. Si simplemente está cargando proyectos y código de exploración, puede desactivar esta opción para evitar la descarga de imágenes de contenedor que no es necesario. |
| Iniciar automáticamente los contenedores en segundo plano | Activado | Docker Compose | Nuevo para aumentar el rendimiento, Visual Studio crea un contenedor con montajes de volumen listo al compilar y ejecutar el contenedor. Si desea controlar cuando se crea el contenedor, desactivar esta opción. |
| Cerrar automáticamente de contenedores de interrupción en la solución | Activado | Docker Compose | Desactivar esta opción si desea que los contenedores de la solución seguir ejecutándose después de cerrar la solución o cerrar Visual Studio. |
| No preguntar para confiar en certificado SSL de localhost | Desactivado | Proyectos de ASP.NET Core 2.1 | Si el certificado SSL de localhost no es de confianza, Visual Studio le pedirá cada vez que ejecute el proyecto, a menos que se activa esta casilla. |

> [!WARNING]
> Si el certificado SSL de localhost no es de confianza y la casilla para suprimir la solicitud, a continuación, las solicitudes HTTPS web pueden producir un error en tiempo de ejecución en su aplicación o servicio. En ese caso, desactive la **no preguntar** checkbox, ejecute el proyecto e indicar confianza en el símbolo del sistema.

> [! INFORMACIÓN] para obtener más información sobre la implementación de los servicios y el uso de Visual Studio Tools para Docker, lea los artículos siguientes:
>
>Depuración de aplicaciones en un contenedor de Docker local: <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh>
>
>Implementar un contenedor ASP.NET en un registro de contenedor con Visual Studio: <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

>[!div class="step-by-step"]
>[Anterior](docker-apps-inner-loop-workflow.md)
>[Siguiente](set-up-windows-containers-with-powershell.md)
