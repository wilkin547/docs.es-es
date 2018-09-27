---
title: Visual Studio Tools para Docker en Windows
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: cd140c12ef4a0187cce096e013937d5c98cd4b39
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47235720"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a><span data-ttu-id="a4d64-103">Con Visual Studio Tools para Docker (Visual Studio en Windows)</span><span class="sxs-lookup"><span data-stu-id="a4d64-103">Using Visual Studio Tools for Docker (Visual Studio on Windows)</span></span>

<span data-ttu-id="a4d64-104">Visual Studio Tools para el flujo de trabajo de desarrollo de Docker es similar al uso de Visual Studio Code y CLI de Docker (se basa en la misma CLI de Docker).</span><span class="sxs-lookup"><span data-stu-id="a4d64-104">The Visual Studio Tools for Docker developer workflow is similar to using Visual Studio Code and Docker CLI (it is based on the same Docker CLI).</span></span> <span data-ttu-id="a4d64-105">Visual Studio Tools para Docker facilita aún más empezar a trabajar, simplifica el proceso y proporciona mayor productividad para la compilación, ejecución y crear tareas.</span><span class="sxs-lookup"><span data-stu-id="a4d64-105">Visual Studio Tools for Docker makes it even easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="a4d64-106">Ejecutar y depurar los contenedores a través de acciones simples, como **F5** y **Ctrl**+**F5**.</span><span class="sxs-lookup"><span data-stu-id="a4d64-106">Execute and debug your containers via simple actions like **F5** and **Ctrl**+**F5**.</span></span>

> [!NOTE]
> <span data-ttu-id="a4d64-107">En este artículo se aplica a Visual Studio en Windows y no en Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="a4d64-107">This article applies to Visual Studio on Windows, and not Visual Studio for Mac.</span></span>

## <a name="configure-your-local-environment"></a><span data-ttu-id="a4d64-108">Configurar el entorno local</span><span class="sxs-lookup"><span data-stu-id="a4d64-108">Configure your local environment</span></span>

<span data-ttu-id="a4d64-109">Con las últimas versiones de Docker para Windows ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)), el programa de instalación sencilla facilita la tarea desarrollar aplicaciones de Docker.</span><span class="sxs-lookup"><span data-stu-id="a4d64-109">With the latest versions of Docker for Windows ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)), the straightforward setup makes it easy to develop Docker applications.</span></span>

<span data-ttu-id="a4d64-110">Compatibilidad con docker se incluye en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="a4d64-110">Docker support is included in Visual Studio 2017.</span></span> <span data-ttu-id="a4d64-111">Descargar Visual Studio 2017 aquí: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span><span class="sxs-lookup"><span data-stu-id="a4d64-111">Download Visual Studio 2017 here: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span></span>

## <a name="use-docker-tools-in-visual-studio-2017"></a><span data-ttu-id="a4d64-112">Use herramientas de Docker en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="a4d64-112">Use Docker Tools in Visual Studio 2017</span></span>

<span data-ttu-id="a4d64-113">Hay dos niveles de compatibilidad con Docker que puede agregar a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="a4d64-113">There are two levels of Docker support you can add to a project.</span></span> <span data-ttu-id="a4d64-114">En los proyectos de aplicación web de .NET Core, puede agregar simplemente un *Dockerfile* archivo al proyecto habilitando la compatibilidad con Docker.</span><span class="sxs-lookup"><span data-stu-id="a4d64-114">In .NET Core web app projects, you can just add a *Dockerfile* file to the project by enabling Docker support.</span></span> <span data-ttu-id="a4d64-115">El siguiente nivel es la compatibilidad con orquestador de contenedores, que agrega un *Dockerfile* al proyecto (si aún no existe) y un *docker-compose.yml* archivo en el nivel de solución.</span><span class="sxs-lookup"><span data-stu-id="a4d64-115">The next level is container orchestrator support, which adds a *Dockerfile* to the project (if it doesn't already exist) and a *docker-compose.yml* file at the solution level.</span></span>

<span data-ttu-id="a4d64-116">El **agregar** > **compatibilidad con Docker** y **agregar** > **la compatibilidad con el orquestador de contenedor** son de comandos ubicado en el menú contextual (o el menú contextual) del nodo de proyecto para un proyecto de aplicación web en **el Explorador de soluciones**, tal y como se muestra en la figura 4-26:</span><span class="sxs-lookup"><span data-stu-id="a4d64-116">The **Add** > **Docker Support** and **Add** > **Container Orchestrator Support** commands are located on the right-click menu (or context menu) of the project node for a web app project in **Solution Explorer**, as shown in Figure 4-26:</span></span>

![Agregar la opción de menú de la compatibilidad con Docker en Visual Studio](media/add-docker-support-menu.png)

<span data-ttu-id="a4d64-118">Figura 4-26: agregar compatibilidad con Docker a un proyecto de Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="a4d64-118">Figure 4-26: Adding Docker support to a Visual Studio 2017 project</span></span>

### <a name="add-docker-support"></a><span data-ttu-id="a4d64-119">Agregar compatibilidad con Docker</span><span class="sxs-lookup"><span data-stu-id="a4d64-119">Add Docker support</span></span>

<span data-ttu-id="a4d64-120">Puede agregar compatibilidad con Docker a un proyecto de aplicación web de .NET Core existente seleccionando **agregar** > **Docker admite** en **el Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="a4d64-120">You can add Docker support to an existing .NET Core web app project by selecting **Add** > **Docker Support** in **Solution Explorer**.</span></span> <span data-ttu-id="a4d64-121">También puede habilitar compatibilidad con Docker durante la creación del proyecto seleccionando **habilitar Docker admite** en el **nueva aplicación Web de ASP.NET Core** cuadro de diálogo que se abre al hacer clic en **Aceptar** en el **nuevo proyecto** cuadro de diálogo, como se muestra en la figura 4-27.</span><span class="sxs-lookup"><span data-stu-id="a4d64-121">You can also enable Docker support during project creation by selecting **Enable Docker Support** in the **New ASP.NET Core Web Application** dialog box that opens after you click **OK** in the **New Project** dialog box, as shown in Figure 4-27.</span></span>

![Habilitar compatibilidad con Docker para la nueva aplicación web de ASP.NET Core en Visual Studio](./media/enable-docker-support-visual-studio.png)

<span data-ttu-id="a4d64-123">Figura 4-27: habilitar la compatibilidad con Docker durante la creación del proyecto en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="a4d64-123">Figure 4-27: Enable Docker support during project creation in Visual Studio 2017</span></span>

<span data-ttu-id="a4d64-124">Al agregar o habilitar la compatibilidad con Docker, Visual Studio agrega un *Dockerfile* archivo al proyecto.</span><span class="sxs-lookup"><span data-stu-id="a4d64-124">When you add or enable Docker support, Visual Studio adds a *Dockerfile* file to the project.</span></span>

> [!NOTE]
> <span data-ttu-id="a4d64-125">Cuando se habilita la compatibilidad con Docker Compose durante la creación del proyecto para un proyecto de aplicación web de .NET Framework (no un proyecto .NET Core web app) tal como se muestra en la figura 4-28, también se agrega compatibilidad con orquestador de contenedores.</span><span class="sxs-lookup"><span data-stu-id="a4d64-125">When you enable Docker Compose support during project creation for a .NET Framework web app project (not a .NET Core web app project) as shown in Figure 4-28, container orchestrator support is also added.</span></span>
>
> ![Habilitar Docker compose de soporte técnico para un proyecto de aplicación web de .NET Framework](media/enable-docker-compose-support.png)

> <span data-ttu-id="a4d64-127">Figura 4-28: habilitar la compatibilidad con Docker Compose en un proyecto de aplicación web de .NET Framework en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="a4d64-127">Figure 4-28: Enabling Docker Compose support on a .NET Framework web app project in Visual Studio 2017</span></span>

### <a name="add-container-orchestrator-support"></a><span data-ttu-id="a4d64-128">Agregar compatibilidad con orquestador de contenedores</span><span class="sxs-lookup"><span data-stu-id="a4d64-128">Add container orchestrator support</span></span>

<span data-ttu-id="a4d64-129">Cuando desea crear una solución de varios contenedores, agregar compatibilidad con orquestador de contenedores a los proyectos.</span><span class="sxs-lookup"><span data-stu-id="a4d64-129">When you want to compose a multicontainer solution, add container orchestrator support to your projects.</span></span> <span data-ttu-id="a4d64-130">Cuando se agrega compatibilidad con orquestador de contenedores, Visual Studio agrega un *Dockerfile* para el proyecto (si aún no existe) y un elemento global *docker-compose.yml* archivo en el nivel de solución.</span><span class="sxs-lookup"><span data-stu-id="a4d64-130">When you add container orchestrator support, Visual Studio adds a *Dockerfile* to the project (if it doesn't already exist) and a global *docker-compose.yml* file at the solution level.</span></span> <span data-ttu-id="a4d64-131">Esto le permite ejecutar y depurar un grupo de contenedores (una solución completa) al mismo tiempo si se definen en el mismo *docker-compose.yml* archivo.</span><span class="sxs-lookup"><span data-stu-id="a4d64-131">This lets you run and debug a group of containers (a whole solution) at the same time if they're defined in the same *docker-compose.yml* file.</span></span> <span data-ttu-id="a4d64-132">Si *docker-compose.yml* ya existe, Visual Studio agrega simplemente las líneas de código de configuración necesarias.</span><span class="sxs-lookup"><span data-stu-id="a4d64-132">If *docker-compose.yml* already exists, Visual Studio just adds the required lines of configuration code to it.</span></span>

<span data-ttu-id="a4d64-133">Después de agregar compatibilidad con la orquestación de contenedor para el proyecto, verá un archivo Dockerfile que se agrega al proyecto y un **docker-compose** carpeta agregada a la solución en **el Explorador de soluciones**, como se muestra en la figura 4-29:</span><span class="sxs-lookup"><span data-stu-id="a4d64-133">After you add container orchestration support to your project, you see a Dockerfile added to the project and a **docker-compose** folder added to the solution in **Solution Explorer**, as shown in Figure 4-29:</span></span>

![Archivos de docker en el Explorador de soluciones en Visual Studio](media/docker-support-solution-explorer.png)

<span data-ttu-id="a4d64-135">Figura 4-29: archivos de Docker en el Explorador de soluciones en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="a4d64-135">Figure 4-29: Docker files in Solution Explorer in Visual Studio 2017</span></span>

<span data-ttu-id="a4d64-136">**Obtener más información:** para obtener más información sobre la implementación de los servicios y el uso de Visual Studio Tools para Docker, lea los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a4d64-136">**More information:** For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>

<span data-ttu-id="a4d64-137">Compilar, depurar, actualizar y actualizar aplicaciones en un contenedor de Docker local: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="a4d64-137">Build, debug, update, and refresh apps in a local Docker container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

<span data-ttu-id="a4d64-138">Implementar un contenedor de Docker de ASP.NET Core en un registro de contenedor: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="a4d64-138">Deploy an ASP.NET Core Docker container to a container registry: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="a4d64-139">[Anterior](docker-apps-inner-loop-workflow.md)
[Siguiente](set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="a4d64-139">[Previous](docker-apps-inner-loop-workflow.md)
[Next](set-up-windows-containers-with-powershell.md)</span></span>