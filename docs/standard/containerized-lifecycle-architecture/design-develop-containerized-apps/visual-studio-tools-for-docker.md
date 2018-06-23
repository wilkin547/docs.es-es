---
title: Con Visual Studio Tools para Docker (Visual Studio en Windows)
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 62da6a3ff595422e42450cb1341976424acc5a52
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2018
ms.locfileid: "36314716"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a><span data-ttu-id="5cfd8-103">Con Visual Studio Tools para Docker (Visual Studio en Windows)</span><span class="sxs-lookup"><span data-stu-id="5cfd8-103">Using Visual Studio Tools for Docker (Visual Studio on Windows)</span></span>

<span data-ttu-id="5cfd8-104">El flujo de trabajo de desarrollador cuando se usa Visual Studio Tools para Docker es similar al flujo de trabajo cuando se usa código de Visual Studio y la CLI de Docker (de hecho, se basa en la misma CLI de Docker), pero es más fácil empezar a trabajar, simplifica el proceso y proporciona una mayor productividad de la compilación, ejecución y crear tareas.</span><span class="sxs-lookup"><span data-stu-id="5cfd8-104">The developer workflow when using Visual Studio Tools for Docker is similar to the workflow when using Visual Studio Code and Docker CLI (in fact, it is based on the same Docker CLI), but it is easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="5cfd8-105">También es capaz de ejecutar y depurar los contenedores a través de acciones simples como F5 y CTRL+F5 desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5cfd8-105">It's also able to execute and debug your containers via simple actions like F5 and Ctrl+F5 from Visual Studio.</span></span> <span data-ttu-id="5cfd8-106">Aún más, con Visual 2017 Studio, además de poder ejecutar y depurar un único contenedor, también puede ejecutar y depurar un grupo de contenedores (una solución completa) a la vez que se hayan definido en el mismo archivo de compose.yml de docker en el nivel de solución.</span><span class="sxs-lookup"><span data-stu-id="5cfd8-106">Even more, with Visual Studio 2017, in addition to being able to run and debug a single container, you also can run and debug a group of containers (a whole solution) at the same time if they are defined in the same docker-compose.yml file at the solution level.</span></span>

## <a name="configuring-your-local-environment"></a><span data-ttu-id="5cfd8-107">Cómo configurar el entorno local</span><span class="sxs-lookup"><span data-stu-id="5cfd8-107">Configuring your local environment</span></span>

<span data-ttu-id="5cfd8-108">Con las versiones más recientes de Docker para Windows, es más fácil que nunca para desarrollar aplicaciones de Docker porque el programa de instalación es sencilla, como se explica en las siguientes referencias.</span><span class="sxs-lookup"><span data-stu-id="5cfd8-108">With the latest versions of Docker for Windows, it is easier than ever to develop Docker applications because the setup is straightforward, as explained in the following references.</span></span>

<span data-ttu-id="5cfd8-109">**Obtener más información:** para más información sobre la instalación de Docker para Windows, vaya a <https://docs.docker.com/docker-for-windows/>.</span><span class="sxs-lookup"><span data-stu-id="5cfd8-109">**More info:** To learn more about installing Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>

<span data-ttu-id="5cfd8-110">Si usa Visual Studio 2015, debe tener la actualización 3 o una versión posterior y Visual Studio Tools para Docker.</span><span class="sxs-lookup"><span data-stu-id="5cfd8-110">If you're using Visual Studio 2015, you must have Update 3 or a later version plus the Visual Studio Tools for Docker.</span></span>

<span data-ttu-id="5cfd8-111">**Obtener más información:** para obtener instrucciones acerca de cómo instalar Visual Studio, vaya a [ https://visualstudio.microsoft.com/\ productos/vs-2015--ediciones de productos](https://visualstudio.microsoft.com/products/vs-2015-product-editions).</span><span class="sxs-lookup"><span data-stu-id="5cfd8-111">**More info:** For instructions on installing Visual Studio, go to [https://visualstudio.microsoft.com/\ products/vs-2015-product-editions](https://visualstudio.microsoft.com/products/vs-2015-product-editions).</span></span>

<span data-ttu-id="5cfd8-112">Para obtener más información acerca de la instalación de Visual Studio Tools para Docker, vaya a <http://aka.ms/vstoolsfordocker> y <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>.</span><span class="sxs-lookup"><span data-stu-id="5cfd8-112">To see more about installing Visual Studio Tools for Docker, go to <http://aka.ms/vstoolsfordocker> and <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>.</span></span>

<span data-ttu-id="5cfd8-113">Si usa Visual Studio de 2017, ya se incluye compatibilidad con Docker.</span><span class="sxs-lookup"><span data-stu-id="5cfd8-113">If you're using Visual Studio 2017, Docker support is already included.</span></span>

## <a name="using-docker-tools-in-visual-studio-2015"></a><span data-ttu-id="5cfd8-114">Con las herramientas de Docker en Visual Studio de 2015</span><span class="sxs-lookup"><span data-stu-id="5cfd8-114">Using Docker Tools in Visual Studio 2015</span></span>

<span data-ttu-id="5cfd8-115">Visual Studio Tools para Docker proporciona una manera coherente para desarrollar y validar localmente los contenedores de Docker para Linux en un host Linux Docker o VM o los contenedores de Windows directamente en Windows.</span><span class="sxs-lookup"><span data-stu-id="5cfd8-115">The Visual Studio Tools for Docker provides a consistent way to develop and validate locally your Docker containers for Linux in a Linux Docker host or VM, or your Windows Containers directly on Windows.</span></span>

<span data-ttu-id="5cfd8-116">Si usa un único contenedor, lo primero que necesita para empezar es desactivar la compatibilidad con Docker en el proyecto de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5cfd8-116">If you're using a single container, the first thing you need to begin is to turn on Docker support into your .NET Core project.</span></span> <span data-ttu-id="5cfd8-117">Para ello, haga clic en el archivo de proyecto, como se muestra en la figura 4-25.</span><span class="sxs-lookup"><span data-stu-id="5cfd8-117">To do this, right-click your project file, as shown in Figure 4-25.</span></span>

![https://i1.visualstudiogallery.msdn.s-msft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4/image/file/205468/1/add-docker-support.png](./media/image31.png)

<span data-ttu-id="5cfd8-118">Figura 4-25: activar la compatibilidad de Docker para el proyecto de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5cfd8-118">Figure 4-25: Turning on Docker support for your Visual Studio project</span></span>

## <a name="using-docker-tools-in-visual-studio-2017"></a><span data-ttu-id="5cfd8-119">Con las herramientas de Docker en Visual Studio de 2017</span><span class="sxs-lookup"><span data-stu-id="5cfd8-119">Using Docker Tools in Visual Studio 2017</span></span>

<span data-ttu-id="5cfd8-120">Al agregar compatibilidad con Docker a un proyecto de servicio de la solución (consulte la figura 4-26), Visual Studio es no limitarse a agregar un archivo DockerFile al proyecto, agrega también una sección de servicio en la solución docker compose.yml archivos (o crear los archivos si no ha existe).</span><span class="sxs-lookup"><span data-stu-id="5cfd8-120">When you add Docker support to a service project in your solution (see Figure 4-26), Visual Studio is not just adding a DockerFile file to your project, it also is adding a service section in your solution's docker-compose.yml files (or creating the files if they didn't exist).</span></span> <span data-ttu-id="5cfd8-121">Es una manera sencilla de empezar a crear la solución multicontainer; a continuación, puede abrir los archivos de docker compose.yml y actualizarlas con características adicionales.</span><span class="sxs-lookup"><span data-stu-id="5cfd8-121">It's an easy way to begin composing your multicontainer solution; you then can open the docker-compose.yml files and update them with additional features.</span></span>

![](./media/image32.png)

<span data-ttu-id="5cfd8-122">Figura 4: 26: activar la compatibilidad de la solución de Docker en un proyecto de Visual Studio de 2017</span><span class="sxs-lookup"><span data-stu-id="5cfd8-122">Figure 4-26: Turning on Docker Solution support in a Visual Studio 2017 project</span></span>

<span data-ttu-id="5cfd8-123">Esta acción no solo agrega el DockerFile al proyecto, también agrega las líneas de configuración necesarias de código para establecer en el nivel de solución un compose.yml docker global.</span><span class="sxs-lookup"><span data-stu-id="5cfd8-123">This action not only adds the DockerFile to your project, it also adds the required configuration lines of code to a global docker-compose.yml set at the solution level.</span></span>

<span data-ttu-id="5cfd8-124">También puede activar en la compatibilidad con Docker al crear un proyecto de ASP.NET Core en 2017 de Visual Studio, tal como se muestra en la figura 4-27.</span><span class="sxs-lookup"><span data-stu-id="5cfd8-124">You also can turn on Docker support when creating an ASP.NET Core project in Visual Studio 2017, as shown in Figure 4-27.</span></span>

![](./media/image33.png)

<span data-ttu-id="5cfd8-125">Figura 4-27: activar la compatibilidad con Docker al crear un proyecto</span><span class="sxs-lookup"><span data-stu-id="5cfd8-125">Figure 4-27: Turning on Docker support when creating a project</span></span>

<span data-ttu-id="5cfd8-126">Después de agregar compatibilidad de Docker a la solución en Visual Studio, también verá un nuevo árbol de nodo en el Explorador de soluciones con los archivos compose.yml de docker agregada, como se muestra en la figura 4-28.</span><span class="sxs-lookup"><span data-stu-id="5cfd8-126">After you add Docker support to your solution in Visual Studio, you also will see a new node tree in Solution Explorer with the added docker-compose.yml files, as depicted in Figure 4-28.</span></span>

![](./media/image34.PNG)

<span data-ttu-id="5cfd8-127">Figura 4-28: archivos de compose.yml de docker se muestran ahora en el Explorador de soluciones</span><span class="sxs-lookup"><span data-stu-id="5cfd8-127">Figure 4-28: docker-compose.yml files now display in Solution Explorer</span></span>

<span data-ttu-id="5cfd8-128">Podría implementar un multicontainer docker componer de aplicación mediante un archivo de docker-compose.yml único cuando se ejecuta; Sin embargo, Visual Studio agrega un grupo de ellos, por lo que puede invalidar valores según el entorno (desarrollo frente a producción) y la ejecución del tipo (versión en comparación con depuración).</span><span class="sxs-lookup"><span data-stu-id="5cfd8-128">You could deploy a multicontainer application by using a single docker-compose.yml file when you run docker-compose up; however, Visual Studio adds a group of them, so you can override values depending on the environment (development versus production) and the execution type (release versus debug).</span></span> <span data-ttu-id="5cfd8-129">Esta capacidad se explican mejor en capítulos posteriores.</span><span class="sxs-lookup"><span data-stu-id="5cfd8-129">This capability will be better explained in later chapters.</span></span>

<span data-ttu-id="5cfd8-130">**Obtener más información:** para obtener más información sobre la implementación de los servicios y el uso de Visual Studio Tools para Docker, lea los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="5cfd8-130">**More info:** For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>

<span data-ttu-id="5cfd8-131">Compilar, depurar, actualizar y actualizar aplicaciones en un contenedor de Docker local: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="5cfd8-131">Build, debug, update, and refresh apps in a local Docker container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

<span data-ttu-id="5cfd8-132">Implementar un contenedor ASP.NET en un host de Docker remoto: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="5cfd8-132">Deploy an ASP.NET container to a remote Docker host: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="5cfd8-133">[Anterior] (docker-aplicaciones-interna-bucle-workflow.md) [siguiente] (set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="5cfd8-133">[Previous] (docker-apps-inner-loop-workflow.md) [Next] (set-up-windows-containers-with-powershell.md)</span></span>
