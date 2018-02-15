---
title: Entorno de desarrollo para aplicaciones de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ad1a6e4cb0974ebb067cf1a7be987d696e8bc82a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="5a0de-104">Entorno de desarrollo para aplicaciones de Docker</span><span class="sxs-lookup"><span data-stu-id="5a0de-104">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="5a0de-105">Opciones de herramientas de desarrollo: IDE o editor</span><span class="sxs-lookup"><span data-stu-id="5a0de-105">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="5a0de-106">Sin importar si prefiere un IDE eficaz y completa o un editor ligero y ágil, Microsoft tiene cubierto en cuanto a desarrollar aplicaciones de Docker.</span><span class="sxs-lookup"><span data-stu-id="5a0de-106">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="5a0de-107">Visual Studio Code y la CLI de Docker (las herramientas multiplataforma para Mac, Linux y Windows)</span><span class="sxs-lookup"><span data-stu-id="5a0de-107">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="5a0de-108">Si lo prefiere, un editor ligero y multiplataforma admite cualquier lenguaje de programación, puede utilizar código de Visual Studio y la CLI de Docker.</span><span class="sxs-lookup"><span data-stu-id="5a0de-108">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="5a0de-109">Estos productos proporcionan una experiencia sencilla pero sólida, lo cual resulta esencial para optimizar el flujo de trabajo de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="5a0de-109">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="5a0de-110">Instalando "Docker para Mac" o "Docker para Windows" (entorno de desarrollo), los desarrolladores de Docker pueden usar una sola CLI de Docker para crear aplicaciones para Windows o Linux (entorno de tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="5a0de-110">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="5a0de-111">Además, código de Visual Studio admite extensiones de Docker con IntelliSense para los archivos Dockerfile y tareas de accesos directos ejecutar comandos de Docker desde el editor.</span><span class="sxs-lookup"><span data-stu-id="5a0de-111">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="5a0de-112">Para descargar el código de Visual Studio, vaya a <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="5a0de-112">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>

<span data-ttu-id="5a0de-113">Para descargar Docker para Mac y Windows, vaya a <http://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="5a0de-113">To download Docker for Mac and Windows, go to <http://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools"></a><span data-ttu-id="5a0de-114">Visual Studio con herramientas de Docker</span><span class="sxs-lookup"><span data-stu-id="5a0de-114">Visual Studio with Docker Tools</span></span>

<span data-ttu-id="5a0de-115">Cuando se usa Visual Studio 2015 puede instalar las herramientas de complemento "Herramientas de Docker para Visual Studio".</span><span class="sxs-lookup"><span data-stu-id="5a0de-115">When you're using Visual Studio 2015 you can install the add-on tools "Docker Tools for Visual Studio."</span></span> <span data-ttu-id="5a0de-116">Para Visual Studio de 2017, herramientas de Docker incluyen incorporados ya.</span><span class="sxs-lookup"><span data-stu-id="5a0de-116">For Visual Studio 2017, Docker Tools come built in already.</span></span> <span data-ttu-id="5a0de-117">En ambos casos que puede desarrollar, ejecutar y validar las aplicaciones directamente en el entorno de Docker elegido.</span><span class="sxs-lookup"><span data-stu-id="5a0de-117">In both cases you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="5a0de-118">F5 (contenedor único o varios contenedores) la aplicación directamente en una Docker hospedar con la depuración, o presione Ctrl + F5 para editar y actualizar la aplicación sin tener que volver a generar el contenedor.</span><span class="sxs-lookup"><span data-stu-id="5a0de-118">F5 your application (single container or multiple containers) directly into a Docker host with debugging, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="5a0de-119">Esta es la opción más sencilla y más eficaces para los desarrolladores de Windows para crear contenedores de Docker para Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="5a0de-119">This is the simplest and more powerful choice for Windows developers creating Docker containers for Linux or Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="5a0de-120">Para descargar herramientas de Docker para Visual Studio, vaya a <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span><span class="sxs-lookup"><span data-stu-id="5a0de-120">To download Docker Tools for Visual Studio, go to <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="5a0de-121">Opciones de idioma y el marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="5a0de-121">Language and framework choices</span></span>

<span data-ttu-id="5a0de-122">Puede desarrollar aplicaciones de Docker y herramientas de Microsoft con lenguajes más modernos.</span><span class="sxs-lookup"><span data-stu-id="5a0de-122">You can develop Docker applications and Microsoft tools with most modern languages.</span></span> <span data-ttu-id="5a0de-123">La siguiente es una lista inicial, pero no está limitado a él:</span><span class="sxs-lookup"><span data-stu-id="5a0de-123">The following is an initial list, but you are not limited to it:</span></span>

-   <span data-ttu-id="5a0de-124">.NET core y ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5a0de-124">.NET Core and ASP.NET Core</span></span>

-   <span data-ttu-id="5a0de-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="5a0de-125">Node.js</span></span>

-   <span data-ttu-id="5a0de-126">Golang</span><span class="sxs-lookup"><span data-stu-id="5a0de-126">Golang</span></span>

-   <span data-ttu-id="5a0de-127">Java</span><span class="sxs-lookup"><span data-stu-id="5a0de-127">Java</span></span>

-   <span data-ttu-id="5a0de-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="5a0de-128">Ruby</span></span>

-   <span data-ttu-id="5a0de-129">Python</span><span class="sxs-lookup"><span data-stu-id="5a0de-129">Python</span></span>

<span data-ttu-id="5a0de-130">Básicamente, puede usar cualquier lenguaje moderno admitido por Docker en Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="5a0de-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="5a0de-131">[Anterior] (orquestar-alta-escalabilidad-availability.md) [siguiente] (docker-aplicaciones-interna-bucle-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5a0de-131">[Previous] (orchestrate-high-scalability-availability.md) [Next] (docker-apps-inner-loop-workflow.md)</span></span>
