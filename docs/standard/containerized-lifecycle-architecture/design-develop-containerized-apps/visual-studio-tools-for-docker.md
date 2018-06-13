---
title: Con Visual Studio Tools para Docker (Visual Studio en Windows)
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 05db5cf8e8dc073dd341fbffab619c326b48f136
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569296"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>Con Visual Studio Tools para Docker (Visual Studio en Windows)

El flujo de trabajo de desarrollador cuando se usa Visual Studio Tools para Docker es similar al flujo de trabajo cuando se usa código de Visual Studio y la CLI de Docker (de hecho, se basa en la misma CLI de Docker), pero es más fácil empezar a trabajar, simplifica el proceso y proporciona una mayor productividad de la compilación, ejecución y crear tareas. También es capaz de ejecutar y depurar los contenedores a través de acciones simples como F5 y CTRL+F5 desde Visual Studio. Aún más, con Visual 2017 Studio, además de poder ejecutar y depurar un único contenedor, también puede ejecutar y depurar un grupo de contenedores (una solución completa) a la vez que se hayan definido en el mismo archivo de compose.yml de docker en el nivel de solución.

## <a name="configuring-your-local-environment"></a>Cómo configurar el entorno local

Con las versiones más recientes de Docker para Windows, es más fácil que nunca para desarrollar aplicaciones de Docker porque el programa de instalación es sencilla, como se explica en las siguientes referencias.

**Obtener más información:** para más información sobre la instalación de Docker para Windows, vaya a <https://docs.docker.com/docker-for-windows/>.

Si usa Visual Studio 2015, debe tener la actualización 3 o una versión posterior y Visual Studio Tools para Docker.

**Obtener más información:** para obtener instrucciones acerca de cómo instalar Visual Studio, vaya a [ https://www.visualstudio.com/\ productos/vs-2015--ediciones de productos](https://www.visualstudio.com/products/vs-2015-product-editions).

Para obtener más información acerca de la instalación de Visual Studio Tools para Docker, vaya a <http://aka.ms/vstoolsfordocker> y <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>.

Si usa Visual Studio de 2017, ya se incluye compatibilidad con Docker.

## <a name="using-docker-tools-in-visual-studio-2015"></a>Con las herramientas de Docker en Visual Studio de 2015

Visual Studio Tools para Docker proporciona una manera coherente para desarrollar y validar localmente los contenedores de Docker para Linux en un host Linux Docker o VM o los contenedores de Windows directamente en Windows.

Si usa un único contenedor, lo primero que necesita para empezar es desactivar la compatibilidad con Docker en el proyecto de .NET Core. Para ello, haga clic en el archivo de proyecto, como se muestra en la figura 4-25.

![https://i1.visualstudiogallery.msdn.s-msft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4/image/file/205468/1/add-docker-support.png](./media/image31.png)

Figura 4-25: activar la compatibilidad de Docker para el proyecto de Visual Studio

## <a name="using-docker-tools-in-visual-studio-2017"></a>Con las herramientas de Docker en Visual Studio de 2017

Al agregar compatibilidad con Docker a un proyecto de servicio de la solución (consulte la figura 4-26), Visual Studio es no limitarse a agregar un archivo DockerFile al proyecto, agrega también una sección de servicio en la solución docker compose.yml archivos (o crear los archivos si no ha existe). Es una manera sencilla de empezar a crear la solución multicontainer; a continuación, puede abrir los archivos de docker compose.yml y actualizarlas con características adicionales.

![](./media/image32.png)

Figura 4: 26: activar la compatibilidad de la solución de Docker en un proyecto de Visual Studio de 2017

Esta acción no solo agrega el DockerFile al proyecto, también agrega las líneas de configuración necesarias de código para establecer en el nivel de solución un compose.yml docker global.

También puede activar en la compatibilidad con Docker al crear un proyecto de ASP.NET Core en 2017 de Visual Studio, tal como se muestra en la figura 4-27.

![](./media/image33.png)

Figura 4-27: activar la compatibilidad con Docker al crear un proyecto

Después de agregar compatibilidad de Docker a la solución en Visual Studio, también verá un nuevo árbol de nodo en el Explorador de soluciones con los archivos compose.yml de docker agregada, como se muestra en la figura 4-28.

![](./media/image34.PNG)

Figura 4-28: archivos de compose.yml de docker se muestran ahora en el Explorador de soluciones

Podría implementar un multicontainer docker componer de aplicación mediante un archivo de docker-compose.yml único cuando se ejecuta; Sin embargo, Visual Studio agrega un grupo de ellos, por lo que puede invalidar valores según el entorno (desarrollo frente a producción) y la ejecución del tipo (versión en comparación con depuración). Esta capacidad se explican mejor en capítulos posteriores.

**Obtener más información:** para obtener más información sobre la implementación de los servicios y el uso de Visual Studio Tools para Docker, lea los siguientes artículos:

Compilar, depurar, actualizar y actualizar aplicaciones en un contenedor de Docker local: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

Implementar un contenedor ASP.NET en un host de Docker remoto: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)


>[!div class="step-by-step"]
[Anterior] (docker-aplicaciones-interna-bucle-workflow.md) [siguiente] (set-up-windows-containers-with-powershell.md)
