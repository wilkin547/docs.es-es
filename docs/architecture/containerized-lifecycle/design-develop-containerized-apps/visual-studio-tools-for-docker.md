---
title: Visual Studio Tools para Docker en Windows
description: Conozca las herramientas de Docker disponibles en Visual Studio 2017, versión 15.7 y posteriores.
ms.date: 08/06/2020
ms.custom: vs-dotnet
ms.openlocfilehash: 74cffaae5885a7079ec774b1e8c68241cddda99a
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915331"
---
# <a name="use-docker-tools-in-visual-studio-on-windows"></a>Uso de herramientas de Docker de Visual Studio en Windows

El flujo de trabajo del desarrollador al utilizar las herramientas de Docker incluidas en Visual Studio 2017, versión 15.7 y posteriores, es similar al de usar Visual Studio Code y la CLI de Docker (de hecho, se basa en la misma CLI de Docker), pero es más fácil de iniciar, simplifica el proceso y aumenta la productividad en las tareas de compilación, ejecución y composición. También puede ejecutar y depurar los contenedores a través de las teclas `F5` y `Ctrl+F5` habituales de Visual Studio. Incluso puede depurar una solución completa si sus contenedores se definen en el mismo archivo `docker-compose.yml` en el nivel de solución.

## <a name="configure-your-local-environment"></a>Configuración del entorno local

Con las últimas versiones de Docker para Windows, resulta más fácil que nunca desarrollar aplicaciones de Docker porque la configuración es sencilla, tal y como se explica en las siguientes referencias.

> [!TIP]
> Para más información sobre cómo instalar Docker para Windows, vaya a (<https://docs.docker.com/docker-for-windows/>).

## <a name="docker-support-in-visual-studio"></a>Compatibilidad con Docker en Visual Studio

Hay dos niveles de compatibilidad con Docker que puede agregar a un proyecto. En los proyectos de ASP.NET Core, basta con agregar un archivo `Dockerfile` al proyecto habilitando la compatibilidad con Docker. El siguiente nivel es la compatibilidad con la orquestación de contenedores, que agrega un archivo `Dockerfile` al proyecto (si aún no existe) y un archivo `docker-compose.yml` en el nivel de solución. La compatibilidad con la orquestación de contenedores, mediante Docker Compose, se agrega de forma predeterminada en las versiones 15.0 a 15.7 de Visual Studio 2017. La compatibilidad con la orquestación de contenedores es una característica opcional en Visual Studio 2017, versión 15.8 o posteriores. Visual Studio 2019 y versiones posteriores también admiten la implementación de **Kubernetes/Helm**.

Los comandos **Agregar > Compatibilidad con Docker** y **Agregar > Compatibilidad con el orquestador de contenedores** se encuentran en el menú contextual del nodo de proyecto de un proyecto de ASP.NET Core en el **Explorador de soluciones**, tal y como se muestra en la figura 4-31:

![Opción de menú Agregar compatibilidad con Docker en Visual Studio](media/add-docker-support-menu.png)

**Figura 4-31**. Incorporación de compatibilidad con Docker a un proyecto de Visual Studio 2019

### <a name="add-docker-support"></a>Agregue compatibilidad con Docker

Además de la opción para agregar compatibilidad con Docker a una aplicación existente, como se ha mostrado en la sección anterior, también puede habilitar la compatibilidad con Docker durante la creación del proyecto si selecciona **Habilitar compatibilidad con Docker** en el cuadro de diálogo **Nueva aplicación web ASP.NET Core** que se abre al hacer clic en **Aceptar** en el cuadro de diálogo **Nuevo proyecto**, como se muestra en la figura 4-32.

![Habilitación de la compatibilidad con Docker para una nueva aplicación web de ASP.NET Core en Visual Studio](media/enable-docker-support-visual-studio.png)

**Figura 4-32**. Habilitación de la compatibilidad con Docker durante la creación del proyecto en Visual Studio 2019

Al agregar o habilitar la compatibilidad con Docker, Visual Studio agrega al proyecto un archivo _Dockerfile_ que incluye referencias a todos los proyectos necesarios de la solución.

### <a name="add-container-orchestration-support"></a>Incorporación de compatibilidad con la orquestación de contenedores

Cuando quiera crear una solución de varios contenedores, agregue compatibilidad con la orquestación de contenedores a sus proyectos. De esta manera podrá ejecutar y depurar un grupo de contenedores (una solución completa) al mismo tiempo si se definen en el mismo archivo _docker-compose.yml_.

Para agregar compatibilidad con la orquestación de contenedores, haga clic con el botón derecho en el nodo de la solución o del proyecto en el **Explorador de soluciones** y elija **Agregar > Compatibilidad con la orquestación de contenedores**. Luego seleccione **Kubernetes/Helm** o **Docker Compose** para administrar los contenedores.

Después de agregar al proyecto compatibilidad con la orquestación de contenedores, ve que se han agregado un archivo Dockerfile al proyecto y una carpeta **docker-compose** a la solución en el **Explorador de soluciones**, como se muestra en la figura 4-33:

![Archivos de Docker en el Explorador de soluciones en Visual Studio](media/docker-support-solution-explorer.png)

**Figura 4-33**. Archivos de Docker en el Explorador de soluciones de Visual Studio 2019

Si _docker-compose.yml_ ya existe, Visual Studio le agrega simplemente las líneas de código de configuración necesarias.

## <a name="configure-docker-tools"></a>Configuración de herramientas de Docker

En el menú principal, elija **Herramientas > Opciones** y expanda **Herramientas de contenedor > Configuración**. Aparecerá la configuración de las herramientas de contenedor.

![Opciones de herramientas de Docker de Visual Studio con tres páginas: General, Proyecto único y Docker Compose, detalles en el texto del artículo.](media/visual-studio-docker-tools-options.png)

**Figura 4-34**. Opciones de herramientas de Docker

La tabla siguiente puede ayudarle a decidir cómo configurar estas opciones.

| Página o valor                                |  Valor predeterminado   | Descripción                                                                                                                                                                                                                                                                                                                                                                                                           |
| ------------------------------------------- | :----------------: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Página General**                            |
| Instalar Docker Desktop si es necesario            |     Preguntarme      |
| Iniciar Docker Desktop si es necesario              |     Preguntarme      |
| Confiar en el certificado SSL de ASP.NET Core          |     Preguntarme      | Si el certificado SSL de localhost no se ha marcado como de confianza (con `dotnet dev-certs https --trust`), Visual Studio le pregunta cada vez que ejecuta el proyecto.                                                                                                                                                                                                                                                    |
| **Página Proyecto único**                     |
| Extraer las imágenes de Docker necesarias al abrir el proyecto |        True        | Para un mejor rendimiento al ejecutar el proyecto, Visual Studio inicia una operación pull de Docker en segundo plano para que cuando esté listo para ejecutar el código, la imagen ya esté descargada o en proceso de descarga. Si simplemente carga proyectos y explora código, puede desactivar esta opción para evitar la descarga de imágenes de contenedor que no son necesarias. Esto puede ralentizar la experiencia del usuario de apertura del proyecto. |
| Extraer las imágenes de Docker actualizadas al abrir el proyecto  | Proyectos de .NET Core | Extraiga las actualizaciones de las imágenes existentes para obtener las últimas actualizaciones al abrir el proyecto. Esto puede ralentizar la experiencia del usuario de apertura del proyecto.                                                                                                                                                                                                                                                                                          |
| Quitar los contenedores al cerrar el proyecto          |        True        | Limpie al cerrar el proyecto. Esto puede ralentizar la experiencia del usuario de cierre del proyecto, pero suele ser rápido de todos modos.                                                                                                                                                                                                                                                                                                            |
| Ejecutar contenedores al abrir el proyecto              |        True        | Para un mejor rendimiento al ejecutar el proyecto, Visual Studio inicia todos los contenedores de la solución. Esto puede ralentizar la experiencia del usuario de apertura del proyecto.                                                                                                                                                                                                                                                        |
| **Docker Compose**                          |                    | La página Docker Compose contiene la misma configuración que la página Proyecto único, pero se aplica a las soluciones de varios contenedores.                                                                                                                                                                                                                                                                                           |

> [!WARNING]
> Si el certificado SSL de localhost no es de confianza y la opción se establece en **Nunca**, se puede producir un error de las solicitudes web HTTPS en tiempo de ejecución en la aplicación o el servicio. En ese caso, vuelva a establecer el valor en **Preguntarme** o, mejor aún, confíe en los certificados del equipo de desarrollo mediante el comando `dotnet dev-certs https --trust`.

> [!TIP]
> Para más información sobre la implementación de servicios y el uso de Visual Studio Tools para Docker, lea los artículos siguientes:
>
> Depuración de aplicaciones en un contenedor de Docker local: <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh>
>
> Implementación de un contenedor ASP.NET en un registro de contenedor con Visual Studio: <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

> [!div class="step-by-step"]
> [Anterior](docker-apps-inner-loop-workflow.md)
> [Siguiente](set-up-windows-containers-with-powershell.md)
