---
title: Compilación de aplicaciones ASP.NET Core implementadas como contenedores de Linux en clústeres de AKS/Kubernetes
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
ms.date: 01/06/2021
ms.openlocfilehash: 7a8f8272ab2faabd0398aeeb2039b6f034b4dedb
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970646"
---
# <a name="build-aspnet-core-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="8eb16-103">Compilación de aplicaciones ASP.NET Core implementadas como contenedores de Linux en un orquestador de AKS/Kubernetes</span><span class="sxs-lookup"><span data-stu-id="8eb16-103">Build ASP.NET Core applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="8eb16-104">Azure Kubernetes Service (AKS) es un servicio de orquestaciones de Kubernetes administrado de Azure que simplifica la implementación y la administración de contenedores.</span><span class="sxs-lookup"><span data-stu-id="8eb16-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="8eb16-105">Estas son las características principales de AKS:</span><span class="sxs-lookup"><span data-stu-id="8eb16-105">AKS main features are:</span></span>

- <span data-ttu-id="8eb16-106">Plano de control hospedado en Azure</span><span class="sxs-lookup"><span data-stu-id="8eb16-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="8eb16-107">Actualizaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="8eb16-107">Automated upgrades</span></span>
- <span data-ttu-id="8eb16-108">Recuperación automática</span><span class="sxs-lookup"><span data-stu-id="8eb16-108">Self-healing</span></span>
- <span data-ttu-id="8eb16-109">Escalado configurable por el usuario</span><span class="sxs-lookup"><span data-stu-id="8eb16-109">User-configurable scaling</span></span>
- <span data-ttu-id="8eb16-110">Experiencia de usuario más sencilla para desarrolladores y operadores de clúster.</span><span class="sxs-lookup"><span data-stu-id="8eb16-110">Simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="8eb16-111">En los ejemplos siguientes se examina la creación de una aplicación de ASP.NET Core 5.0 que se ejecuta en Linux y se implementa en un clúster de AKS en Azure, mientras que el desarrollo se realiza con Visual Studio 2019, versión 16.8.</span><span class="sxs-lookup"><span data-stu-id="8eb16-111">The following examples explore the creation of an ASP.NET Core 5.0 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2019 version 16.8.</span></span>

## <a name="creating-the-aspnet-core-project-using-visual-studio-2019"></a><span data-ttu-id="8eb16-112">Creación del proyecto de ASP.NET Core con Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="8eb16-112">Creating the ASP.NET Core Project using Visual Studio 2019</span></span>

<span data-ttu-id="8eb16-113">ASP.NET Core es una plataforma de desarrollo de uso general de cuyo mantenimiento se encargan Microsoft y la comunidad .NET en GitHub.</span><span class="sxs-lookup"><span data-stu-id="8eb16-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="8eb16-114">Es multiplataforma, admite Windows, macOS y Linux y puede usarse en escenarios de dispositivo, nube, IoT e incrustados.</span><span class="sxs-lookup"><span data-stu-id="8eb16-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="8eb16-115">En este ejemplo se usan un par de proyectos simples basados en plantillas de Visual Studio, por lo que no necesita muchos conocimientos adicionales para crear el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8eb16-115">This example uses a couple of simple projects based on Visual Studio templates, so you don't need much additional knowledge to create the sample.</span></span> <span data-ttu-id="8eb16-116">Solo tiene que crear el proyecto con una plantilla estándar que incluya todos los elementos para ejecutar un proyecto pequeño con una API REST y una aplicación web con Razor Pages, mediante la tecnología ASP.NET Core 5.0.</span><span class="sxs-lookup"><span data-stu-id="8eb16-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API and a Web App with Razor pages, using ASP.NET Core 5.0 technology.</span></span>

![Ventana para agregar nuevo proyecto en Visual Studio, con la aplicación web de ASP.NET Core seleccionada.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-aspnet-core-application.png)

<span data-ttu-id="8eb16-118">**Figura 4-35**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-118">**Figure 4-35**.</span></span> <span data-ttu-id="8eb16-119">Creación de una aplicación web ASP.NET Core en Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="8eb16-119">Creating an ASP.NET Core Web Application in Visual Studio 2019.</span></span>

<span data-ttu-id="8eb16-120">Para crear el proyecto de ejemplo en Visual Studio, seleccione **Archivo** > **Nuevo** > **Proyecto**, seleccione el tipo de proyecto **Web** y luego la plantilla **Aplicación web ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project type and then the **ASP.NET Core Web Application** template.</span></span> <span data-ttu-id="8eb16-121">También puede buscar la plantilla si la necesita.</span><span class="sxs-lookup"><span data-stu-id="8eb16-121">You can also search for the template if you need it.</span></span>

<span data-ttu-id="8eb16-122">Luego escriba el nombre y la ubicación de la aplicación como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="8eb16-122">Then enter the application name and location as shown in the next image.</span></span>

![Escriba el nombre y la ubicación del proyecto.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/enter-project-name-and-location.png)

<span data-ttu-id="8eb16-124">**Figura 4-36**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-124">**Figure 4-36**.</span></span> <span data-ttu-id="8eb16-125">Especificación del nombre y la ubicación del proyecto en Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="8eb16-125">Enter the project name and location in Visual Studio 2019.</span></span>

<span data-ttu-id="8eb16-126">Compruebe que ha seleccionado ASP.NET Core 5.0 como marco.</span><span class="sxs-lookup"><span data-stu-id="8eb16-126">Verify that you've selected ASP.NET Core 5.0 as the framework.</span></span> <span data-ttu-id="8eb16-127">.NET 5.0 está incluido en la última versión de Visual Studio 2019, y se instala y configura automáticamente al instalar Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8eb16-127">.NET 5.0 is included in the latest release of Visual Studio 2019 and is automatically installed and configured for you when you install Visual Studio.</span></span>

![Cuadro de diálogo de Visual Studio para seleccionar el tipo de aplicación web ASP.NET Core con la opción API seleccionada.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-web-api-application.png)

<span data-ttu-id="8eb16-129">**Figura 4-37**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-129">**Figure 4-37**.</span></span> <span data-ttu-id="8eb16-130">Selección de ASP.NET Core 5.0 y del tipo de proyecto API web</span><span class="sxs-lookup"><span data-stu-id="8eb16-130">Selecting ASP.NET CORE 5.0 and Web API project type</span></span>

<span data-ttu-id="8eb16-131">Observe que la compatibilidad con Docker no está habilitada, solo para mostrar que se puede hacer después de la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8eb16-131">Notice Docker support is not enabled now, just to show it can be done after project creation.</span></span>

<span data-ttu-id="8eb16-132">Si tiene alguna versión anterior de .NET Core, puede descargar e instalar la versión 3.1 desde <https://dotnet.microsoft.com/download>.</span><span class="sxs-lookup"><span data-stu-id="8eb16-132">If you have any previous version of .NET Core, you can download and install the 3.1 version from <https://dotnet.microsoft.com/download>.</span></span>

<span data-ttu-id="8eb16-133">Para mostrar que puede "aplicar Docker" al proyecto en cualquier momento, se va a agregar compatibilidad con Docker ahora.</span><span class="sxs-lookup"><span data-stu-id="8eb16-133">To show you can "Dockerize" your project at any time, you'll add Docker support now.</span></span> <span data-ttu-id="8eb16-134">Haga clic con el botón derecho en el nodo del proyecto en el Explorador de soluciones y seleccione **Agregar** > **Compatibilidad con Docker** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="8eb16-134">So right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![Opción del menú contextual para agregar compatibilidad con Docker a un proyecto existente: Haga clic con el botón derecho (en el proyecto) > Agregar > Compatibilidad con Docker.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-docker-support-to-project.png)

<span data-ttu-id="8eb16-136">**Figura 4-38**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-136">**Figure 4-38**.</span></span> <span data-ttu-id="8eb16-137">Incorporación de compatibilidad con Docker a un proyecto existente</span><span class="sxs-lookup"><span data-stu-id="8eb16-137">Adding Docker support to an existing project</span></span>

<span data-ttu-id="8eb16-138">Para acabar de agregar compatibilidad con Docker, puede elegir Windows o Linux.</span><span class="sxs-lookup"><span data-stu-id="8eb16-138">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="8eb16-139">En este caso, seleccione **Linux**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-139">In this case, select **Linux**.</span></span>

![Cuadro de diálogo de opciones para seleccionar el sistema operativo de destino para el archivo Dockerfile.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-linux-docker-support.png)

<span data-ttu-id="8eb16-141">**Figura 4-39**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-141">**Figure 4-39**.</span></span> <span data-ttu-id="8eb16-142">Selección de contenedores de Linux</span><span class="sxs-lookup"><span data-stu-id="8eb16-142">Selecting Linux containers.</span></span>

<span data-ttu-id="8eb16-143">Con estos sencillos pasos, ya tiene la aplicación de ASP.NET Core 5.0 en ejecución en un contenedor de Linux.</span><span class="sxs-lookup"><span data-stu-id="8eb16-143">With these simple steps, you have your ASP.NET Core 5.0 application running on a Linux container.</span></span>

<span data-ttu-id="8eb16-144">De forma similar, también puede agregar un proyecto **WebApp** muy sencillo (figura 4-40) para usar el punto de conexión de la API web, aunque los detalles no se tratan aquí.</span><span class="sxs-lookup"><span data-stu-id="8eb16-144">In a similar way, you can also add a very simple **WebApp** project (Figure 4-40) to consume the web API endpoint, although the details are not discussed here.</span></span>

<span data-ttu-id="8eb16-145">Después, agregue compatibilidad con el orquestador al proyecto **WebApi** como se muestra a continuación, en la imagen 4-40.</span><span class="sxs-lookup"><span data-stu-id="8eb16-145">After that, you add orchestrator support for your **WebApi** project as shown next, in image 4-40.</span></span>

![Incorporación de compatibilidad con el orquestador al proyecto WebApi](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-orchestrator-support.png)

<span data-ttu-id="8eb16-147">**Figura 4-40**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-147">**Figure 4-40**.</span></span> <span data-ttu-id="8eb16-148">Incorporación de compatibilidad con el orquestador al proyecto *WebApi*.</span><span class="sxs-lookup"><span data-stu-id="8eb16-148">Adding orchestrator support to *WebApi* project.</span></span>

<span data-ttu-id="8eb16-149">Al seleccionar la opción `Docker Compose`, que es correcta para el desarrollo local, Visual Studio agrega el proyecto docker-compose, con los archivos de docker-compose, como se muestra en la imagen 4-41.</span><span class="sxs-lookup"><span data-stu-id="8eb16-149">When you choose the `Docker Compose` option, which is fine for local development, Visual Studio adds the docker-compose project, with the docker-compose files as shown in image 4-41.</span></span>

![docker-compose agregado a la solución](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-compose-project-in-visual-studio.png)

<span data-ttu-id="8eb16-151">**Figura 4-41**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-151">**Figure 4-41**.</span></span> <span data-ttu-id="8eb16-152">Incorporación de compatibilidad con el orquestador al proyecto *WebApi*.</span><span class="sxs-lookup"><span data-stu-id="8eb16-152">Adding orchestrator support to *WebApi* project.</span></span>

<span data-ttu-id="8eb16-153">Los archivos iniciales agregados son similares a estos:</span><span class="sxs-lookup"><span data-stu-id="8eb16-153">The initial files added are similar to these ones:</span></span>

`docker-compose.yml`

```yml
version: "3.4"

services:
  webapi:
    image: ${DOCKER_REGISTRY-}webapi
    build:
      context: .
      dockerfile: WebApi/Dockerfile

  webapp:
    image: ${DOCKER_REGISTRY-}webapp
    build:
      context: .
      dockerfile: WebApp/Dockerfile
```

`docker-compose.override.yml`

```yml
version: "3.4"

services:
  webapi:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=https://+:443;http://+:80
    ports:
      - "80"
      - "443"
    volumes:
      - ${APPDATA}/Microsoft/UserSecrets:/root/.microsoft/usersecrets:ro
      - ${APPDATA}/ASP.NET/Https:/root/.aspnet/https:ro
  webapp:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=https://+:443;http://+:80
    ports:
      - "80"
      - "443"
    volumes:
      - ${APPDATA}/Microsoft/UserSecrets:/root/.microsoft/usersecrets:ro
      - ${APPDATA}/ASP.NET/Https:/root/.aspnet/https:ro
```

<span data-ttu-id="8eb16-154">Para que la aplicación se ejecute con Docker Compose, solo tiene que realizar algunos ajustes en `docker-compose.override.yml`</span><span class="sxs-lookup"><span data-stu-id="8eb16-154">To have you app running with Docker Compose you just have to make a few tweaks to `docker-compose.override.yml`</span></span>

```yml
services:
  webapi:
    #...
    ports:
      - "51080:80"
      - "51443:443"
    #...
  webapp:
    environment:
      #...
      - WebApiBaseAddress=http://webapi
    ports:
      - "50080:80"
      - "50443:443"
    #...
```

<span data-ttu-id="8eb16-155">Ahora puede ejecutar la aplicación con la tecla **F5**, mediante el botón **Reproducir**, o bien la tecla **Ctrl+F5** al seleccionar el proyecto docker-compose, como se muestra en la imagen 4-42.</span><span class="sxs-lookup"><span data-stu-id="8eb16-155">Now you can run your application with the **F5** key, or by using the **Play** button, or the **Ctrl+F5** key, selecting the docker-compose project, as shown in image 4-42.</span></span>

![Ejecución del proyecto docker-compose con Visual Studio](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/running-docker-compose-with-visual-studio.png)

<span data-ttu-id="8eb16-157">**Figura 4-42**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-157">**Figure 4-42**.</span></span> <span data-ttu-id="8eb16-158">Incorporación de compatibilidad con el orquestador al proyecto *WebApi*.</span><span class="sxs-lookup"><span data-stu-id="8eb16-158">Adding orchestrator support to *WebApi* project.</span></span>

<span data-ttu-id="8eb16-159">Al ejecutar la aplicación docker-compose como se ha explicado, se consigue:</span><span class="sxs-lookup"><span data-stu-id="8eb16-159">When running the docker-compose application as explained, you get:</span></span>

1. <span data-ttu-id="8eb16-160">Compilar las imágenes y crear los contenedores según el archivo docker-compose.</span><span class="sxs-lookup"><span data-stu-id="8eb16-160">The images built and containers created as per the docker-compose file.</span></span>
2. <span data-ttu-id="8eb16-161">Abrir el explorador en la dirección configurada en el cuadro de diálogo "Propiedades" del proyecto `docker-compose`.</span><span class="sxs-lookup"><span data-stu-id="8eb16-161">The browser open in the address configured in the "Properties" dialog for the `docker-compose` project.</span></span>
3. <span data-ttu-id="8eb16-162">Abrir la ventana **Contenedor** (en Visual Studio 2019, versión 16.4 y posteriores).</span><span class="sxs-lookup"><span data-stu-id="8eb16-162">The **Container** window open (in Visual Studio 2019 version 16.4 and later).</span></span>
4. <span data-ttu-id="8eb16-163">Compatibilidad del depurador con todos los proyectos de la solución, como se muestra en las siguientes imágenes.</span><span class="sxs-lookup"><span data-stu-id="8eb16-163">Debugger support for all projects in the solution, as shown in the following images.</span></span>

<span data-ttu-id="8eb16-164">Explorador abierto:</span><span class="sxs-lookup"><span data-stu-id="8eb16-164">Browser opened:</span></span>

![Vista del explorador con aplicación web en ejecución](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/browser-opened.png)

<span data-ttu-id="8eb16-166">**Figura 4-43**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-166">**Figure 4-43**.</span></span> <span data-ttu-id="8eb16-167">Ventana del explorador con una aplicación en ejecución en varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="8eb16-167">Browser window with an application running on multiple containers.</span></span>

<span data-ttu-id="8eb16-168">Ventana Contenedores:</span><span class="sxs-lookup"><span data-stu-id="8eb16-168">Containers window:</span></span>

![Ventana "Contenedores" de Visual Studio](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/visual-studio-containers-window.png)

<span data-ttu-id="8eb16-170">**Figura 4-44**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-170">**Figure 4-44**.</span></span> <span data-ttu-id="8eb16-171">Ventana "Contenedores" de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8eb16-171">Visual Studio "Containers" window</span></span>

<span data-ttu-id="8eb16-172">La ventana **Contenedores** permite ver los contenedores en ejecución, examinar las imágenes disponibles, ver variables de entorno, registros y asignaciones de puertos, inspeccionar el sistema de archivos, adjuntar un depurador o abrir una ventana de terminal dentro del entorno del contenedor.</span><span class="sxs-lookup"><span data-stu-id="8eb16-172">The **Containers** window lets you view running containers, browse available images, view environment variables, logs, and port mappings, inspect the filesystem, attach a debugger, or open a terminal window inside the container environment.</span></span>

<span data-ttu-id="8eb16-173">Como puede ver, la integración entre Visual Studio 2019 y Docker está totalmente orientada a la productividad del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="8eb16-173">As you can see, the integration between Visual Studio 2019 and Docker is completely oriented to the developer's productivity.</span></span>

<span data-ttu-id="8eb16-174">Por supuesto, también puede enumerar las imágenes mediante el comando `docker images`.</span><span class="sxs-lookup"><span data-stu-id="8eb16-174">Of course, you can also list the images using the `docker images` command.</span></span> <span data-ttu-id="8eb16-175">Debería ver las imágenes `webapi` y `webapp` con las etiquetas `dev` creadas por la implementación automática del proyecto con Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="8eb16-175">You should see the `webapi` and `webapp` images with the `dev` tags created by the automatic deployment of our project with Visual Studio 2019.</span></span>

```console
docker images
```

![Salida de la consola del comando de imágenes de Docker, en la que se muestra una lista con los siguientes elementos: Repositorio, Etiqueta, Id. de imagen, Creado (fecha) y Tamaño.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-images-command.png)

<span data-ttu-id="8eb16-177">**Figura 4-45**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-177">**Figure 4-45**.</span></span> <span data-ttu-id="8eb16-178">Vista de imágenes de Docker</span><span class="sxs-lookup"><span data-stu-id="8eb16-178">View of Docker images</span></span>

## <a name="register-the-solution-in-an-azure-container-registry-acr"></a><span data-ttu-id="8eb16-179">Registro de la solución en una instancia de Azure Container Registry (ACR)</span><span class="sxs-lookup"><span data-stu-id="8eb16-179">Register the Solution in an Azure Container Registry (ACR)</span></span>

<span data-ttu-id="8eb16-180">Puede cargar las imágenes en [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/), pero también puede usar Docker Hub o cualquier otro registro de modo que las imágenes puedan implementarse en el clúster de AKS desde ese registro.</span><span class="sxs-lookup"><span data-stu-id="8eb16-180">You can upload the images to the [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/), but you could also use Docker Hub or any other registry, so the images can be deployed to the AKS cluster from that registry.</span></span>

### <a name="create-an-acr-instance"></a><span data-ttu-id="8eb16-181">Creación de una instancia de ACR</span><span class="sxs-lookup"><span data-stu-id="8eb16-181">Create an ACR instance</span></span>

<span data-ttu-id="8eb16-182">Ejecute el siguiente comando desde **az cli**:</span><span class="sxs-lookup"><span data-stu-id="8eb16-182">Run the following command from the **az cli**:</span></span>

```powershell
az acr create --name exploredocker --resource-group explore-docker-aks-rg --sku basic --admin-enabled
```

> [!NOTE]
> <span data-ttu-id="8eb16-183">El nombre del registro de contenedor (p. ej. `exploredocker`) debe ser único dentro de Azure y contener entre 5 y 50 caracteres alfanuméricos.</span><span class="sxs-lookup"><span data-stu-id="8eb16-183">The container registry name (e.g `exploredocker`) must be unique within Azure, and contain 5-50 alphanumeric characters.</span></span> <span data-ttu-id="8eb16-184">Para obtener más información, vea [Creación de un registro de contenedor](/azure/container-registry/container-registry-get-started-azure-cli#create-a-container-registry)</span><span class="sxs-lookup"><span data-stu-id="8eb16-184">For more details, refer [Create a container registry](/azure/container-registry/container-registry-get-started-azure-cli#create-a-container-registry)</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="8eb16-185">Creación de la imagen en modo de versión</span><span class="sxs-lookup"><span data-stu-id="8eb16-185">Create the image in Release mode</span></span>

<span data-ttu-id="8eb16-186">Ahora va a crear la imagen en modo **Versión** (listo para producción). Para ello, cambie a **Versión**, como se muestra en la figura 4-46, y ejecute la aplicación como antes.</span><span class="sxs-lookup"><span data-stu-id="8eb16-186">You'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-46, and running the application as you did before.</span></span>

![Opción de la barra de herramientas de Visual Studio para compilar en modo de versión.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-release-mode.png)

<span data-ttu-id="8eb16-188">**Figura 4-46**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-188">**Figure 4-46**.</span></span> <span data-ttu-id="8eb16-189">Selección del modo de versión</span><span class="sxs-lookup"><span data-stu-id="8eb16-189">Selecting Release Mode</span></span>

<span data-ttu-id="8eb16-190">Si ejecuta el comando `docker images`, ve que se crean dos imágenes, una para el modo `debug` (**desarrollo**) y otra para el modo `release` (**más reciente**).</span><span class="sxs-lookup"><span data-stu-id="8eb16-190">If you execute the `docker images` command, you'll see both images created, one for `debug` (**dev**) and the other for `release` (**latest**) mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="8eb16-191">Creación de una nueva etiqueta para la imagen</span><span class="sxs-lookup"><span data-stu-id="8eb16-191">Create a new Tag for the Image</span></span>

<span data-ttu-id="8eb16-192">Es preciso etiquetar cada imagen de contenedor con el nombre `loginServer` del registro.</span><span class="sxs-lookup"><span data-stu-id="8eb16-192">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="8eb16-193">Esta etiqueta se usa para el enrutamiento al insertar imágenes de contenedor en un registro de imágenes.</span><span class="sxs-lookup"><span data-stu-id="8eb16-193">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="8eb16-194">Para ver el nombre `loginServer` desde Azure Portal, tome la información de Azure Container Registry.</span><span class="sxs-lookup"><span data-stu-id="8eb16-194">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![Vista del explorador con el nombre de Azure Container Registry en la esquina superior derecha.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/loginServer-name.png)

<span data-ttu-id="8eb16-196">**Figura 4-47**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-196">**Figure 4-47**.</span></span> <span data-ttu-id="8eb16-197">Vista del nombre del Registro</span><span class="sxs-lookup"><span data-stu-id="8eb16-197">View of the name of the Registry</span></span>

<span data-ttu-id="8eb16-198">También puede ejecutar el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="8eb16-198">Or by running the following command:</span></span>

```console
az acr list --resource-group <resource-group-name> --query "[].{acrLoginServer:loginServer}" --output table
```

![Salida de la consola del comando anterior.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/az-cli-loginServer-name.png)

<span data-ttu-id="8eb16-200">**Figura 4-48**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-200">**Figure 4-48**.</span></span> <span data-ttu-id="8eb16-201">Obtención del nombre del registro mediante **az cli**</span><span class="sxs-lookup"><span data-stu-id="8eb16-201">Get the name of the registry using **az cli**</span></span>

<span data-ttu-id="8eb16-202">En ambos casos, obtendrá el nombre.</span><span class="sxs-lookup"><span data-stu-id="8eb16-202">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="8eb16-203">En nuestro ejemplo, se trata de `exploredocker.azurecr.io`.</span><span class="sxs-lookup"><span data-stu-id="8eb16-203">In our example, `exploredocker.azurecr.io`.</span></span>

<span data-ttu-id="8eb16-204">Ahora puede etiquetar la imagen. Para ello, tome la imagen más reciente (la imagen de versión) con este comando:</span><span class="sxs-lookup"><span data-stu-id="8eb16-204">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag <image-name>:latest <login-server-name>/<image-name>:v1
```

<span data-ttu-id="8eb16-205">Después de ejecutar el comando `docker tag`, muestre las imágenes con el comando `docker images`. Debería ver la imagen con la nueva etiqueta.</span><span class="sxs-lookup"><span data-stu-id="8eb16-205">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![Salida de la consola del comando de imágenes de Docker.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/tagged-docker-images-list.png)

<span data-ttu-id="8eb16-207">**Figura 4-49**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-207">**Figure 4-49**.</span></span> <span data-ttu-id="8eb16-208">Vista de las imágenes etiquetadas</span><span class="sxs-lookup"><span data-stu-id="8eb16-208">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="8eb16-209">Inserción de la imagen en Azure ACR</span><span class="sxs-lookup"><span data-stu-id="8eb16-209">Push the image into the Azure ACR</span></span>

<span data-ttu-id="8eb16-210">Inicie sesión en Azure Container Registry.</span><span class="sxs-lookup"><span data-stu-id="8eb16-210">Log in to the Azure Container Registry</span></span>

```console
az acr login --name exploredocker
```

<span data-ttu-id="8eb16-211">Inserte la imagen en Azure ACR con el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="8eb16-211">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push <login-server-name>/<image-name>:v1
```

<span data-ttu-id="8eb16-212">Este comando tarda un poco en cargar las imágenes, pero proporciona información durante el proceso.</span><span class="sxs-lookup"><span data-stu-id="8eb16-212">This command takes a while uploading the images but gives you feedback in the process.</span></span> <span data-ttu-id="8eb16-213">En la imagen siguiente puede ver la salida de una imagen completada y otra en curso.</span><span class="sxs-lookup"><span data-stu-id="8eb16-213">In the following image, you can see the output from one image completed and another in progress.</span></span>

![Salida de la consola del comando push de Docker.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/uploading-docker-images-complete.png)

<span data-ttu-id="8eb16-215">**Figura 4-50**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-215">**Figure 4-50**.</span></span> <span data-ttu-id="8eb16-216">Salida de la consola del comando push.</span><span class="sxs-lookup"><span data-stu-id="8eb16-216">Console output from the push command.</span></span>

<span data-ttu-id="8eb16-217">Para implementar la aplicación de varios contenedores en el clúster de AKS, necesita algunos archivos `.yaml` de manifiesto que tengan la mayoría de las propiedades tomadas de los archivos `docker-compose.yml` y `docker-compose.override.yml`.</span><span class="sxs-lookup"><span data-stu-id="8eb16-217">To deploy your multi-container app into your AKS cluster you need some manifest `.yaml` files that have, most of the properties taken from the `docker-compose.yml` and `docker-compose.override.yml` files.</span></span>

#### `deploy-webapi.yml`

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapi
  labels:
    app: weather-forecast
spec:
  replicas: 1
  selector:
    matchLabels:
      service: webapi
  template:
    metadata:
      labels:
        app: weather-forecast
        service: webapi
    spec:
      containers:
        - name: webapi
          image: exploredocker.azurecr.io/webapi:v1
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 80
              protocol: TCP
          env:
            - name: ASPNETCORE_URLS
              value: http://+:80
---
apiVersion: v1
kind: Service
metadata:
  name: webapi
  labels:
    app: weather-forecast
    service: webapi
spec:
  ports:
    - port: 80
      targetPort: 80
      protocol: TCP
  selector:
    service: webapi
```

#### `deploy-webapp.yml`

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapp
  labels:
    app: weather-forecast
spec:
  replicas: 1
  selector:
    matchLabels:
      service: webapp
  template:
    metadata:
      labels:
        app: weather-forecast
        service: webapp
    spec:
      containers:
        - name: webapp
          image: exploredocker.azurecr.io/webapp:v1
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 80
              protocol: TCP
          env:
            - name: ASPNETCORE_URLS
              value: http://+:80
            - name: WebApiBaseAddress
              value: http://webapi
---
apiVersion: v1
kind: Service
metadata:
  name: webapp
  labels:
    app: weather-forecast
    service: webapp
spec:
  type: LoadBalancer
  ports:
    - port: 80
      targetPort: 80
      protocol: TCP
  selector:
    service: webapp
```

> [!NOTE]
> <span data-ttu-id="8eb16-218">Los archivos `.yml` anteriores solo habilitan los puertos `HTTP` mediante el parámetro `ASPNETCORE_URLS` para evitar problemas con el certificado que falta en la aplicación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8eb16-218">The previous `.yml` files only enable the `HTTP` ports, using the `ASPNETCORE_URLS` parameter, to avoid issues with the missing certificate in the sample app.</span></span>

> [!TIP]
> <span data-ttu-id="8eb16-219">Si quiere saber cómo se crea el clúster de AKS para este ejemplo, vea la sección [**Implementación en Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) de esta guía.</span><span class="sxs-lookup"><span data-stu-id="8eb16-219">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

<span data-ttu-id="8eb16-220">Ya está casi listo para implementar con **kubectl**, pero primero debe obtener las credenciales del clúster de AKS con este comando:</span><span class="sxs-lookup"><span data-stu-id="8eb16-220">Now you're almost ready to deploy using **kubectl**, but first you must get the credentials from the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![Salida de la consola del comando anterior: "explore-docker-aks" combinado como contexto actual de C:\Users\Miguel.kube\config](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/getting-aks-credentials.png)

<span data-ttu-id="8eb16-222">**Figura 4-51**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-222">**Figure 4-51**.</span></span> <span data-ttu-id="8eb16-223">Obtención de credenciales de AKS en el entorno de kubectl.</span><span class="sxs-lookup"><span data-stu-id="8eb16-223">Getting credentials from AKS into the kubectl environment.</span></span>

<span data-ttu-id="8eb16-224">También debe permitir que el clúster de AKS extraiga imágenes de la instancia de ACR con este comando:</span><span class="sxs-lookup"><span data-stu-id="8eb16-224">You also have to allow the AKS cluster to pull images from the ACR, using this command:</span></span>

```console
az aks update --name explore-docker-aks --resource-group explore-docker-aks-rg --attach-acr exploredocker
```

<span data-ttu-id="8eb16-225">El comando anterior puede tardar un par de minutos en terminar.</span><span class="sxs-lookup"><span data-stu-id="8eb16-225">The previous command might take a couple of minutes to complete.</span></span> <span data-ttu-id="8eb16-226">Luego use el comando `kubectl apply` para iniciar las implementaciones; entonces, `kubectl get all` indica los objetos del clúster.</span><span class="sxs-lookup"><span data-stu-id="8eb16-226">Then, use the `kubectl apply` command to launch the deployments, and then `kubectl get all` get list the cluster objects.</span></span>

```console
kubectl apply -f deploy-webapi.yml
kubectl apply -f deploy-webapp.yml

kubectl get all
```

![Salida de la consola de los comandos anteriores: implementaciones aplicadas.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubectl-apply-command.png)

<span data-ttu-id="8eb16-229">**Figura 4-52**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-229">**Figure 4-52**.</span></span> <span data-ttu-id="8eb16-230">Implementación en Kubernetes</span><span class="sxs-lookup"><span data-stu-id="8eb16-230">Deployment to Kubernetes</span></span>

<span data-ttu-id="8eb16-231">Tiene que esperar un rato para que el equilibrador de carga obtenga la dirección IP externa al consultar con `kubectl get services` y, luego, la aplicación debe estar disponible en esa dirección, como se muestra en la siguiente imagen:</span><span class="sxs-lookup"><span data-stu-id="8eb16-231">You'll have to wait a while until the load balancer gets the external IP, checking with `kubectl get services`, and then the application should be available at that address, as shown in the next image:</span></span>

![Vista del explorador de la aplicación implementada en AKS](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/aks-deployed-application.png)

<span data-ttu-id="8eb16-233">**Figura 4-53**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-233">**Figure 4-53**.</span></span> <span data-ttu-id="8eb16-234">Implementación en Kubernetes</span><span class="sxs-lookup"><span data-stu-id="8eb16-234">Deployment to Kubernetes</span></span>

<span data-ttu-id="8eb16-235">Una vez finalizada la implementación, puede acceder a la [interfaz de usuario web de Kubernetes](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) con un proxy local, mediante un túnel SSH.</span><span class="sxs-lookup"><span data-stu-id="8eb16-235">When the deployment completes, you can access the [Kubernetes Web UI](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) with a local proxy, using an ssh tunnel.</span></span>

<span data-ttu-id="8eb16-236">En primer lugar, debe crear un elemento ClusterRoleBinding con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="8eb16-236">First you must create a ClusterRoleBinding with the following command:</span></span>

```console
kubectl create clusterrolebinding kubernetes-dashboard --clusterrole=cluster-admin --serviceaccount=kube-system:kubernetes-dashboard
```

<span data-ttu-id="8eb16-237">Y luego este comando para iniciar el proxy:</span><span class="sxs-lookup"><span data-stu-id="8eb16-237">And then this command to start the proxy:</span></span>

```console
az aks browse --resource-group exploredocker-aks-rg --name explore-docker-aks
```

<span data-ttu-id="8eb16-238">Se debe abrir una ventana del explorador en `http://127.0.0.1:8001` con una vista similar a esta:</span><span class="sxs-lookup"><span data-stu-id="8eb16-238">A browser window should open at `http://127.0.0.1:8001` with a view similar to this one:</span></span>

![Vista del explorador del panel de Kubernetes, en el que se muestran los elementos Implementaciones, Pods, Conjuntos de réplicas y Servicios.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubernetes-cluster-information.png)

<span data-ttu-id="8eb16-240">**Figura 4-54**.</span><span class="sxs-lookup"><span data-stu-id="8eb16-240">**Figure 4-54**.</span></span> <span data-ttu-id="8eb16-241">Vista de la información del clúster de Kubernetes</span><span class="sxs-lookup"><span data-stu-id="8eb16-241">View Kubernetes cluster information</span></span>

<span data-ttu-id="8eb16-242">Ya tiene la aplicación ASP.NET Core en ejecución en contenedores de Linux e implementada en un clúster de AKS en Azure.</span><span class="sxs-lookup"><span data-stu-id="8eb16-242">Now you have your ASP.NET Core application, running in Linux containers, and deployed to an AKS cluster on Azure.</span></span>

> [!NOTE]
> <span data-ttu-id="8eb16-243">Para obtener más información sobre la implementación con Kubernetes, vea <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>.</span><span class="sxs-lookup"><span data-stu-id="8eb16-243">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="8eb16-244">[Anterior](set-up-windows-containers-with-powershell.md)
> [Siguiente](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="8eb16-244">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
