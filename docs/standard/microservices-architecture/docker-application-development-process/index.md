---
title: Proceso de desarrollo de aplicaciones basadas en Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Proceso de desarrollo de aplicaciones basadas en Docker
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: dc91c7d5e2e27602afd6d583bf09adae3caea59e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="development-process-for-docker-based-applications"></a><span data-ttu-id="1fa56-104">Proceso de desarrollo de aplicaciones basadas en Docker</span><span class="sxs-lookup"><span data-stu-id="1fa56-104">Development Process for Docker-Based Applications</span></span>

<span data-ttu-id="1fa56-105">*Desarrolle aplicaciones .NET en contenedor de la forma que prefiera, ya sea centradas en el IDE con Visual Studio y Visual Studio Tools para Docker o bien centradas en la CLI o el editor con la CLI de Docker y Visual Studio Code.*</span><span class="sxs-lookup"><span data-stu-id="1fa56-105">*Develop containerized .NET applications the way you like, either IDE focused with Visual Studio and Visual Studio tools for Docker or CLI/Editor focused with Docker CLI and Visual Studio Code.*</span></span>

## <a name="development-environment-for-docker-apps"></a><span data-ttu-id="1fa56-106">Entorno de desarrollo para aplicaciones de Docker</span><span class="sxs-lookup"><span data-stu-id="1fa56-106">Development environment for Docker apps</span></span>

### <a name="development-tool-choices-ide-or-editor"></a><span data-ttu-id="1fa56-107">Opciones de herramientas de desarrollo: IDE o editor</span><span class="sxs-lookup"><span data-stu-id="1fa56-107">Development tool choices: IDE or editor</span></span>

<span data-ttu-id="1fa56-108">Tanto si quiere un IDE eficaz y completo como si prefiere un editor ligero y ágil, Microsoft dispone de herramientas que puede usar para desarrollar aplicaciones de Docker.</span><span class="sxs-lookup"><span data-stu-id="1fa56-108">Whether you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has tools that you can use for developing Docker applications.</span></span>

<span data-ttu-id="1fa56-109">**Visual Studio (para Windows)**.</span><span class="sxs-lookup"><span data-stu-id="1fa56-109">**Visual Studio (for Windows)**.</span></span> <span data-ttu-id="1fa56-110">Para desarrollar aplicaciones basadas en Docker, use Visual Studio 2017 o versiones posteriores que se incluyen con las herramientas de Docker ya integradas.</span><span class="sxs-lookup"><span data-stu-id="1fa56-110">To develop Docker-based applications, use Visual Studio 2017 or later versions that comes with tools for Docker already built-in.</span></span> <span data-ttu-id="1fa56-111">Las herramientas de Docker permiten desarrollar, ejecutar y validar las aplicaciones directamente en el entorno de Docker de destino.</span><span class="sxs-lookup"><span data-stu-id="1fa56-111">The tools for Docker let you develop, run, and validate your applications directly in the target Docker environment.</span></span> <span data-ttu-id="1fa56-112">Puede presionar F5 para ejecutar y depurar la aplicación (de un solo contenedor o de varios contenedores) directamente en un host de Docker, o bien presionar CTRL+F5 para editar y actualizar la aplicación sin tener que volver a compilar el contenedor.</span><span class="sxs-lookup"><span data-stu-id="1fa56-112">You can press F5 to run and debug your application (single container or multiple containers) directly into a Docker host, or press CTRL+F5 to edit and refresh your application without having to rebuild the container.</span></span> <span data-ttu-id="1fa56-113">Se trata de la opción de desarrollo más eficaz para aplicaciones basadas en Docker.</span><span class="sxs-lookup"><span data-stu-id="1fa56-113">This is the most powerful development choice for Docker-based apps.</span></span>

<span data-ttu-id="1fa56-114">**Visual Studio para Mac**.</span><span class="sxs-lookup"><span data-stu-id="1fa56-114">**Visual Studio for Mac**.</span></span> <span data-ttu-id="1fa56-115">Se trata de un IDE, una evolución de Xamarin Studio, que se ejecuta en Mac OS y admite el desarrollo de aplicaciones basadas en Docker.</span><span class="sxs-lookup"><span data-stu-id="1fa56-115">It is an IDE, evolution of Xamarin Studio, that runs on macOS and supports Docker-based application development.</span></span> <span data-ttu-id="1fa56-116">Debe ser la opción preferida para los desarrolladores que trabajan en equipos Mac y que también deseen usar un IDE eficaz.</span><span class="sxs-lookup"><span data-stu-id="1fa56-116">This should be the preferred choice for developers working in Mac machines who also want to use a powerful IDE.</span></span>

<span data-ttu-id="1fa56-117">**Visual Studio Code y la CLI de Docker**.</span><span class="sxs-lookup"><span data-stu-id="1fa56-117">**Visual Studio Code and Docker CLI**.</span></span> <span data-ttu-id="1fa56-118">Si prefiere un editor ligero multiplataforma que admita todos los lenguajes de programación, puede usar Microsoft Visual Studio Code (VS Code) y la CLI de Docker.</span><span class="sxs-lookup"><span data-stu-id="1fa56-118">If you prefer a lightweight and cross-platform editor that supports any development language, you can use Microsoft Visual Studio Code (VS Code) and the Docker CLI.</span></span> <span data-ttu-id="1fa56-119">Se trata de un enfoque de desarrollo multiplataforma para Mac, Linux y Windows.</span><span class="sxs-lookup"><span data-stu-id="1fa56-119">This is a cross-platform development approach for Mac, Linux, and Windows.</span></span>

<span data-ttu-id="1fa56-120">Mediante la instalación de las herramientas de [Docker Community Edition (CE)](https://www.docker.com/community-edition), puede usar una sola CLI de Docker para compilar aplicaciones para Windows y Linux.</span><span class="sxs-lookup"><span data-stu-id="1fa56-120">By installing [Docker Community Edition (CE)](https://www.docker.com/community-edition) tools, you can use a single Docker CLI to build apps for both Windows and Linux.</span></span> <span data-ttu-id="1fa56-121">Además, Visual Studio Code admite extensiones para Docker como IntelliSense para Dockerfiles y tareas de acceso directo para ejecutar comandos de Docker desde el editor.</span><span class="sxs-lookup"><span data-stu-id="1fa56-121">Additionally, Visual Studio Code supports extensions for Docker such as IntelliSense for Dockerfiles and shortcut tasks to run Docker commands from the editor.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1fa56-122">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1fa56-122">Additional resources</span></span>

-   <span data-ttu-id="1fa56-123">**Visual Studio Tools para Docker**
    [*https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker*](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span><span class="sxs-lookup"><span data-stu-id="1fa56-123">**Visual Studio Tools for Docker**
[*https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker*](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span></span>

-   <span data-ttu-id="1fa56-124">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="1fa56-124">**Visual Studio Code**.</span></span> <span data-ttu-id="1fa56-125">Sitio oficial.</span><span class="sxs-lookup"><span data-stu-id="1fa56-125">Official site.</span></span>
    [<span data-ttu-id="1fa56-126">*https://code.visualstudio.com/download*</span><span class="sxs-lookup"><span data-stu-id="1fa56-126">*https://code.visualstudio.com/download*</span></span>](https://code.visualstudio.com/download)

-   <span data-ttu-id="1fa56-127">**Docker Community Edition (CE) para Mac y Windows**
    [*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)</span><span class="sxs-lookup"><span data-stu-id="1fa56-127">**Docker Community Edition (CE) for Mac and Windows**
[*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)</span></span>

## <a name="net-languages-and-frameworks-for-docker-containers"></a><span data-ttu-id="1fa56-128">Lenguajes y marcos de .NET para contenedores de Docker</span><span class="sxs-lookup"><span data-stu-id="1fa56-128">.NET languages and frameworks for Docker containers</span></span>

<span data-ttu-id="1fa56-129">Como se ha mencionado en secciones anteriores de esta guía, puede usar .NET Framework, .NET Core o el proyecto Mono de código abierto para desarrollar aplicaciones .NET en contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="1fa56-129">As mentioned in earlier sections of this guide, you can use .NET Framework, .NET Core, or the open-source Mono project when developing Docker containerized .NET applications.</span></span> <span data-ttu-id="1fa56-130">Puede desarrollar en C\#, F\# o Visual Basic cuando tenga como destino contenedores de Windows o Linux, en función de qué versión de .NET Framework esté en uso.</span><span class="sxs-lookup"><span data-stu-id="1fa56-130">You can develop in C\#, F\#, or Visual Basic when targeting Linux or Windows Containers, depending on which .NET framework is in use.</span></span> <span data-ttu-id="1fa56-131">Para obtener más información sobre lenguajes de .NET, vea la entrada de blog [The .NET Language Strategy](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/) (Estrategia de lenguaje de .NET).</span><span class="sxs-lookup"><span data-stu-id="1fa56-131">For more details about.NET languages, see the blog post [The .NET Language Strategy](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="1fa56-132">[Anterior] (../architect-microservice-container-applications/using-azure-service-fabric.md) [Siguiente] (docker-app-development-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1fa56-132">[Previous] (../architect-microservice-container-applications/using-azure-service-fabric.md) [Next] (docker-app-development-workflow.md)</span></span>
