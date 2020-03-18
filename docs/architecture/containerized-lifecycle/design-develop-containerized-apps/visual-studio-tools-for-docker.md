---
title: Visual Studio Tools para Docker en Windows
description: Conozca las herramientas de Docker disponibles en Visual Studio 2017, versión 15.7 y posteriores.
ms.date: 02/15/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 2b6fdc33f9cf850cf9e52fca4a1a9754cd412567
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "68673882"
---
# <a name="use-docker-tools-in-visual-studio-2017-on-windows"></a>Herramientas de Docker en Visual Studio 2017 en Windows

El flujo de trabajo del desarrollador al utilizar las herramientas de Docker incluidas en Visual Studio 2017, versión 15.7 y posteriores, es similar al de usar Visual Studio Code y la CLI de Docker (de hecho, se basa en la misma CLI de Docker), pero es más fácil de iniciar, simplifica el proceso y aumenta la productividad en las tareas de compilación, ejecución y composición. También puede ejecutar y depurar los contenedores a través de las teclas `F5` y `Ctrl+F5` habituales de Visual Studio. Incluso puede depurar una solución completa si sus contenedores se definen en el mismo archivo `docker-compose.yml` en el nivel de solución.

## <a name="configure-your-local-environment"></a>Configuración del entorno local

Con las últimas versiones de Docker para Windows, resulta más fácil que nunca desarrollar aplicaciones de Docker porque la configuración es sencilla, tal y como se explica en las siguientes referencias.

> [!TIP]
> Para más información sobre cómo instalar Docker para Windows, vaya a (<https://docs.docker.com/docker-for-windows/>).

## <a name="docker-support-in-visual-studio-2017"></a>Compatibilidad con Docker en Visual Studio 2017

Hay dos niveles de compatibilidad con Docker que puede agregar a un proyecto. En los proyectos de ASP.NET Core, basta con agregar un archivo `Dockerfile` al proyecto habilitando la compatibilidad con Docker. El siguiente nivel es la compatibilidad con la orquestación de contenedores, que agrega un archivo `Dockerfile` al proyecto (si aún no existe) y un archivo `docker-compose.yml` en el nivel de solución. La compatibilidad con la orquestación de contenedores, mediante Docker Compose, se agrega de forma predeterminada en las versiones 15.0 a 15.7 de Visual Studio 2017. La compatibilidad con la orquestación de contenedores es una característica opcional en Visual Studio 2017, versión 15.8 o posteriores. La versión 15.8 y posteriores admiten Docker Compose y Service Fabric.

Los comandos **Agregar > Compatibilidad con Docker** y **Agregar > Compatibilidad con el orquestador de contenedores** se encuentran en el menú contextual del nodo de proyecto de un proyecto de ASP.NET Core en el **Explorador de soluciones**, tal y como se muestra en la figura 4-31:

![Opción de menú Agregar compatibilidad con Docker en Visual Studio](./media/add-docker-support-menu.png)

**Figura 4-31**. Incorporación de compatibilidad con Docker a un proyecto de Visual Studio 2017

### <a name="add-docker-support"></a>Adición de compatibilidad con Docker

Puede agregar compatibilidad con Docker a un proyecto de ASP.NET Core existente si selecciona **Agregar** > **Compatibilidad con Docker** en el **Explorador de soluciones**. También puede habilitar compatibilidad con Docker durante la creación del proyecto si selecciona **Habilitar compatibilidad con Docker** en el cuadro de diálogo **Nueva aplicación web ASP.NET Core** que se abre al hacer clic en **Aceptar** en el cuadro de diálogo **Nuevo proyecto**, tal y como se muestra en la figura 4-32.

![Habilitación de la compatibilidad con Docker para una nueva aplicación web de ASP.NET Core en Visual Studio](./media/enable-docker-support-visual-studio.png)

**Figura 4-32**. Habilitación de la compatibilidad con Docker durante la creación del proyecto en Visual Studio 2017

Al agregar o habilitar la compatibilidad con Docker, Visual Studio agrega el archivo *Dockerfile* al proyecto.

> [!NOTE]
> Al habilitar la compatibilidad con Docker Compose durante la creación de un proyecto de ASP.NET (.NET Framework, no un proyecto de .NET Core), tal y como se muestra en la figura 4-33, también se agrega compatibilidad con la orquestación de contenedores.

![Habilitación de la compatibilidad con Docker Compose para un proyecto de ASP.NET](media/enable-docker-compose-support.png)

**Figura 4-33**. Habilitación de la compatibilidad con Docker Compose para un proyecto de ASP.NET en Visual Studio 2017

### <a name="add-container-orchestration-support"></a>Incorporación de compatibilidad con la orquestación de contenedores

Cuando quiera crear una solución de varios contenedores, agregue compatibilidad con la orquestación de contenedores a sus proyectos. De esta manera podrá ejecutar y depurar un grupo de contenedores (una solución completa) al mismo tiempo si se definen en el mismo archivo *docker-compose.yml*.

Para agregar compatibilidad con la orquestación de contenedores, haga clic con el botón derecho en el nodo de la solución o del proyecto en el **Explorador de soluciones** y elija **Agregar > Compatibilidad con la orquestación de contenedores**. Luego elija **Docker Compose** o **Service Fabric** para administrar los contenedores.

Después de agregar al proyecto compatibilidad con la orquestación de contenedores, verá que se agrega un archivo Dockerfile al proyecto y una carpeta **docker-compose** a la solución en el **Explorador de soluciones**, tal y como se muestra en la figura 4-34:

![Archivos de Docker en el Explorador de soluciones en Visual Studio](media/docker-support-solution-explorer.png)

**Figura 4-34**. Archivos de Docker en el Explorador de soluciones en Visual Studio 2017

Si *docker-compose.yml* ya existe, Visual Studio le agrega simplemente las líneas de código de configuración necesarias.

## <a name="configure-docker-tools"></a>Configuración de herramientas de Docker

En el menú principal, elija **Herramientas > Opciones** y expanda **Herramientas de contenedor > Configuración**. Aparecerá la configuración de las herramientas de contenedor.

![Opciones de herramientas de Docker en Visual Studio, que muestran: Extraer automáticamente las imágenes de Docker necesarias al cargar el proyecto, Iniciar automáticamente los contenedores en segundo plano, Terminar automáticamente los contenedores al cerrar la solución y No pedir confirmación para confiar en el certificado SSL de localhost.](./media/visual-studio-docker-tools-options.png)

**Figura 4-35**. Opciones de herramientas de Docker

La tabla siguiente puede ayudarle a decidir cómo configurar estas opciones.

| NOMBRE | Valor predeterminado | Se aplica a | Descripción |
| -----|:---------------:|:----------:| ----------- |
| Extraer automáticamente las imágenes de Docker necesarias al cargar el proyecto | Activado | Docker Compose | Para aumentar el rendimiento al cargar proyectos, Visual Studio iniciará una operación docker pull en segundo plano para que cuando se esté listo para ejecutar el código, la imagen ya esté descargada o en proceso de descarga. Si simplemente carga proyectos y explora código, puede desactivar esta opción para evitar la descarga de imágenes de contenedor que no son necesarias. |
| Iniciar automáticamente los contenedores en segundo plano | Activado | Docker Compose | Una vez más, para aumentar el rendimiento, Visual Studio crea un contenedor con montajes de volumen listos para cuando se compile y ejecute el contenedor. Si desea controlar cuándo se crea el contenedor, desactive esta opción. |
| Terminar automáticamente los contenedores al cerrar la solución | Activado | Docker Compose | Desactive esta opción si quiere que los contenedores de la solución sigan ejecutándose después de cerrar la solución o de cerrar Visual Studio. |
| No pedir confirmación para confiar en el certificado SSL de localhost | Desactivado | Proyectos de ASP.NET Core 2.2 | Si el certificado SSL de localhost no es de confianza, Visual Studio le pedirá confirmación cada vez que ejecute el proyecto, a menos que se active esta casilla. |

> [!WARNING]
> Si el certificado SSL de localhost no es de confianza y se activa la casilla de supresión de la confirmación, las solicitudes HTTPS web pueden producir un error en tiempo de ejecución en la aplicación o el servicio. En ese caso, desmarque la casilla **Do not prompt** (No pedir confirmación), ejecute el proyecto e indique que confía en la solicitud.

> [!TIP]
> Para más información sobre la implementación de servicios y el uso de Visual Studio Tools para Docker, lea los artículos siguientes:
>
>Depuración de aplicaciones en un contenedor de Docker local: <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh>
>
>Implementación de un contenedor ASP.NET en un registro de contenedor con Visual Studio: <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

>[!div class="step-by-step"]
>[Anterior](docker-apps-inner-loop-workflow.md)
>[Siguiente](set-up-windows-containers-with-powershell.md)
