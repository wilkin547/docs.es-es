---
title: Con Visual Studio Tools para Docker (Visual Studio en Windows)
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: af14c92ab27885deec878dc33e7b94035f43e65b
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45743835"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>Con Visual Studio Tools para Docker (Visual Studio en Windows)

El flujo de trabajo de desarrollo al usar Visual Studio Tools para Docker es similar al flujo de trabajo cuando se usa Visual Studio Code y CLI de Docker. De hecho, se basa en la misma CLI de Docker, pero es más fácil empezar a trabajar, simplifica el proceso y proporciona mayor productividad para la compilación, ejecución y crear tareas. También es capaz de ejecutar y depurar los contenedores a través de acciones simples, como F5 y CTRL+F5 desde Visual Studio. Con la compatibilidad con la orquestación de contenedor opcional, además de poder ejecutar y depurar un único contenedor, puede ejecutar y depurar un grupo de contenedores (una solución completa) al mismo tiempo. Simplemente definen los contenedores en el mismo *docker-compose.yml* archivo en el nivel de solución.

## <a name="configuring-your-local-environment"></a>Para configurar un entorno local

Compatibilidad con docker se incluye en Visual Studio 2017 con cualquiera de las cargas de trabajo de .NET y .NET Core instalados. Instale Docker para Windows por separado.

Con las últimas versiones de Docker para Windows, es más fácil que nunca para desarrollar aplicaciones de Docker porque el programa de instalación es sencilla, como se explica en las siguientes referencias.

**Más información:** para más información acerca de cómo instalar Docker para Windows, vaya a <https://docs.docker.com/docker-for-windows/>.

**Más información:** para obtener instrucciones sobre cómo instalar Visual Studio, vaya a [ https://visualstudio.microsoft.com/downloads/ ](https://visualstudio.microsoft.com/downloads/).

Para obtener más información acerca de la instalación de Visual Studio Tools para Docker, vaya a <http://aka.ms/vstoolsfordocker> y <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>.

## <a name="using-docker-tools-in-visual-studio-2017"></a>Uso de herramientas de Docker en Visual Studio 2017

Al agregar compatibilidad con Docker a un proyecto (consulte la figura 4-26), Visual Studio agrega un *Dockerfile* a la raíz del proyecto.

![Activar la compatibilidad con la solución de Docker en un proyecto de Visual Studio 2017](./media/image32.png)

Figura 4-26: activar la compatibilidad con la solución de Docker en un proyecto de Visual Studio 2017

 Compatibilidad con orquestación de contenedores, a través de Docker Compose, se agrega de forma predeterminada en las versiones de Visual Studio 2017 15.7 o una versión anteriores. Compatibilidad con la orquestación de contenedor es una característica opcional en las versiones de Visual Studio 2017 15,8 o versiones posteriores, en cuyo caso Docker Compose y Service Fabric se admiten.

Con Visual Studio versión 15,8 y versiones posterior, puede agregar compatibilidad para varios proyectos en una solución que cada uno tiene un contenedor asociado. Haga doble clic en el nodo de solución o proyecto en **el Explorador de soluciones**y elija **agregar** > **compatibilidad con la orquestación de contenedor**.  A continuación, elija **Docker Compose** o **Service Fabric** para administrar los contenedores.

Cuando se elige **Docker Compose**, Visual Studio agrega una sección de servicio en la solución *docker-compose.yml* archivos (o crea los archivos si no existen). Es una manera fácil de comenzar a crear la solución de varios contenedor; a continuación, puede abrir el *docker-compose.yml* archivos y debe actualizarlos con características adicionales.

Esta acción agrega las líneas de configuración necesarias de código para un *docker-compose.yml* establecido en el nivel de solución.

También puede activar compatibilidad con Docker al crear un proyecto de ASP.NET Core en Visual Studio 2017, tal como se muestra en la figura 4-27.

![Activar la compatibilidad con Docker al crear un proyecto](./media/image33.png)

Figura 4-27: activar la compatibilidad con Docker al crear un proyecto

Después de agregar compatibilidad con Docker a la solución en Visual Studio, también verá un nuevo árbol de nodos en **el Explorador de soluciones** con agregado *docker-compose.yml* archivos, como se muestra en la figura 4-28.

![archivos docker-compose.yml se muestran ahora en el Explorador de soluciones](./media/image34.PNG)

Figura 4-28: archivos docker-compose.yml se muestran ahora en **el Explorador de soluciones**

Podría implementar una aplicación de varios contenedor mediante una sola *docker-compose.yml* archivo al ejecutar `docker-compose up`; sin embargo, Visual Studio agrega un grupo de ellos, para que pueda sustituir valores según el entorno (desarrollo frente a producción) y la ejecución del tipo (versión frente a depuración). Esta capacidad se explica mejor en los capítulos posteriores.

También puede utilizar a Service Fabric en lugar de Docker Compose para administrar varios contenedores. Consulte [Tutorial: implementar una aplicación .NET en un contenedor de Windows en Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-host-app-in-a-container).

**Más información:** para obtener más información sobre la implementación de los servicios y el uso de Visual Studio Tools para Docker, lea los artículos siguientes:

Compilar, depurar, actualizar y actualizar aplicaciones en un contenedor de Docker local: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

Implementar un contenedor de Docker de ASP.NET Core en un registro de contenedor: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

>[!div class="step-by-step"]
[Anterior](docker-apps-inner-loop-workflow.md)
[Siguiente](set-up-windows-containers-with-powershell.md)
