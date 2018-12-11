---
title: Entorno de desarrollo para aplicaciones de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 471b52fd577e5560bd93e6da50f2032d63eb2e6f
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152421"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="5d6a0-103">Entorno de desarrollo para aplicaciones de Docker</span><span class="sxs-lookup"><span data-stu-id="5d6a0-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="5d6a0-104">Opciones de herramientas de desarrollo: Editor o IDE</span><span class="sxs-lookup"><span data-stu-id="5d6a0-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="5d6a0-105">Sin importar si lo prefiere, un IDE eficaz y completo o un editor ligero y ágil, Microsoft le puede ayudar en cuanto a desarrollar aplicaciones de Docker.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="5d6a0-106">Visual Studio Code y CLI de Docker (Herramientas multiplataforma para Mac, Linux y Windows)</span><span class="sxs-lookup"><span data-stu-id="5d6a0-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="5d6a0-107">Si prefiere un editor ligero y multiplataforma que admiten cualquier lenguaje de desarrollo, puede usar Visual Studio Code y CLI de Docker.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="5d6a0-108">Estos productos proporcionan una experiencia sencilla y sólida que es fundamental para optimizar el flujo de trabajo de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="5d6a0-109">Al instalar "Docker para Mac" o "Docker para Windows" (entorno de desarrollo), los desarrolladores de Docker pueden utilizar una sola CLI de Docker para crear aplicaciones para Windows o Linux (entorno de tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="5d6a0-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="5d6a0-110">Además, Visual Studio Code admite extensiones para Docker con IntelliSense para Dockerfiles y tareas de acceso directo ejecutar comandos de Docker desde el editor.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="5d6a0-111">Para descargar el código de Visual Studio, vaya a <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>

<span data-ttu-id="5d6a0-112">Para descargar Docker para Mac y Windows, vaya a <https://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools"></a><span data-ttu-id="5d6a0-113">Visual Studio con las herramientas de Docker</span><span class="sxs-lookup"><span data-stu-id="5d6a0-113">Visual Studio with Docker Tools</span></span>

<span data-ttu-id="5d6a0-114">Cuando se usa Visual Studio 2015 puede instalar las herramientas de complemento "Herramientas de Docker para Visual Studio".</span><span class="sxs-lookup"><span data-stu-id="5d6a0-114">When you're using Visual Studio 2015 you can install the add-on tools "Docker Tools for Visual Studio."</span></span> <span data-ttu-id="5d6a0-115">Para Visual Studio 2017, las herramientas de Docker están integradas en ya.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-115">For Visual Studio 2017, Docker Tools come built in already.</span></span> <span data-ttu-id="5d6a0-116">En ambos casos que puede desarrollar, ejecutar y validar sus aplicaciones directamente en el entorno de Docker elegido.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-116">In both cases you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="5d6a0-117">F5 hospedar con la depuración de la aplicación (único contenedor o varios contenedores) directamente en Docker, o presione Ctrl + F5 para editar y actualizar la aplicación sin tener que recompilar el contenedor.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-117">F5 your application (single container or multiple containers) directly into a Docker host with debugging, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="5d6a0-118">Esta es la opción más sencilla y más eficaces para los desarrolladores de Windows para crear contenedores de Docker para Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-118">This is the simplest and more powerful choice for Windows developers creating Docker containers for Linux or Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="5d6a0-119">Para descargar las herramientas de Docker para Visual Studio, vaya a <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-119">To download Docker Tools for Visual Studio, go to <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="5d6a0-120">Opciones de idioma y marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="5d6a0-120">Language and framework choices</span></span>

<span data-ttu-id="5d6a0-121">Puede desarrollar aplicaciones de Docker y las herramientas de Microsoft con los lenguajes más modernos.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-121">You can develop Docker applications and Microsoft tools with most modern languages.</span></span> <span data-ttu-id="5d6a0-122">La siguiente es una lista inicial, pero no está limitado a él:</span><span class="sxs-lookup"><span data-stu-id="5d6a0-122">The following is an initial list, but you are not limited to it:</span></span>

-   <span data-ttu-id="5d6a0-123">.NET Core y ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5d6a0-123">.NET Core and ASP.NET Core</span></span>
-   <span data-ttu-id="5d6a0-124">Node.js</span><span class="sxs-lookup"><span data-stu-id="5d6a0-124">Node.js</span></span>
-   <span data-ttu-id="5d6a0-125">Golang</span><span class="sxs-lookup"><span data-stu-id="5d6a0-125">Golang</span></span>
-   <span data-ttu-id="5d6a0-126">Java</span><span class="sxs-lookup"><span data-stu-id="5d6a0-126">Java</span></span>
-   <span data-ttu-id="5d6a0-127">Ruby</span><span class="sxs-lookup"><span data-stu-id="5d6a0-127">Ruby</span></span>
-   <span data-ttu-id="5d6a0-128">Python</span><span class="sxs-lookup"><span data-stu-id="5d6a0-128">Python</span></span>

<span data-ttu-id="5d6a0-129">Básicamente, puede usar cualquier lenguaje moderno compatible con Docker en Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-129">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5d6a0-130">[Anterior](orchestrate-high-scalability-availability.md)
>[Siguiente](docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5d6a0-130">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-inner-loop-workflow.md)</span></span>