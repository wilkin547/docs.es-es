---
title: Entorno de desarrollo para aplicaciones de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 4adbdd7099dfc1c5ef13d5bbb4370ae2f14aba1e
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696785"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="b4ab4-103">Entorno de desarrollo para aplicaciones de Docker</span><span class="sxs-lookup"><span data-stu-id="b4ab4-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="b4ab4-104">Opciones de herramientas de desarrollo: IDE o editor</span><span class="sxs-lookup"><span data-stu-id="b4ab4-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="b4ab4-105">Sin importar si prefiere un IDE eficaz y completa o un editor ligero y ágil, Microsoft tiene cubierto en cuanto a desarrollar aplicaciones de Docker.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="b4ab4-106">Visual Studio Code y la CLI de Docker (las herramientas multiplataforma para Mac, Linux y Windows)</span><span class="sxs-lookup"><span data-stu-id="b4ab4-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="b4ab4-107">Si lo prefiere, un editor ligero y multiplataforma admite cualquier lenguaje de programación, puede utilizar código de Visual Studio y la CLI de Docker.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="b4ab4-108">Estos productos proporcionan una experiencia sencilla pero sólida, lo cual resulta esencial para optimizar el flujo de trabajo de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="b4ab4-109">Instalando "Docker para Mac" o "Docker para Windows" (entorno de desarrollo), los desarrolladores de Docker pueden usar una sola CLI de Docker para crear aplicaciones para Windows o Linux (entorno de tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="b4ab4-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="b4ab4-110">Además, código de Visual Studio admite extensiones de Docker con IntelliSense para los archivos Dockerfile y tareas de accesos directos ejecutar comandos de Docker desde el editor.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="b4ab4-111">Para descargar el código de Visual Studio, vaya a <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>

<span data-ttu-id="b4ab4-112">Para descargar Docker para Mac y Windows, vaya a <https://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools"></a><span data-ttu-id="b4ab4-113">Visual Studio con herramientas de Docker</span><span class="sxs-lookup"><span data-stu-id="b4ab4-113">Visual Studio with Docker Tools</span></span>

<span data-ttu-id="b4ab4-114">Cuando se usa Visual Studio 2015 puede instalar las herramientas de complemento "Herramientas de Docker para Visual Studio".</span><span class="sxs-lookup"><span data-stu-id="b4ab4-114">When you're using Visual Studio 2015 you can install the add-on tools "Docker Tools for Visual Studio."</span></span> <span data-ttu-id="b4ab4-115">Para Visual Studio de 2017, herramientas de Docker incluyen incorporados ya.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-115">For Visual Studio 2017, Docker Tools come built in already.</span></span> <span data-ttu-id="b4ab4-116">En ambos casos que puede desarrollar, ejecutar y validar las aplicaciones directamente en el entorno de Docker elegido.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-116">In both cases you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="b4ab4-117">F5 (contenedor único o varios contenedores) la aplicación directamente en una Docker hospedar con la depuración, o presione Ctrl + F5 para editar y actualizar la aplicación sin tener que volver a generar el contenedor.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-117">F5 your application (single container or multiple containers) directly into a Docker host with debugging, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="b4ab4-118">Esta es la opción más sencilla y más eficaces para los desarrolladores de Windows para crear contenedores de Docker para Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-118">This is the simplest and more powerful choice for Windows developers creating Docker containers for Linux or Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="b4ab4-119">Para descargar herramientas de Docker para Visual Studio, vaya a <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-119">To download Docker Tools for Visual Studio, go to <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="b4ab4-120">Opciones de idioma y el marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="b4ab4-120">Language and framework choices</span></span>

<span data-ttu-id="b4ab4-121">Puede desarrollar aplicaciones de Docker y herramientas de Microsoft con lenguajes más modernos.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-121">You can develop Docker applications and Microsoft tools with most modern languages.</span></span> <span data-ttu-id="b4ab4-122">La siguiente es una lista inicial, pero no está limitado a él:</span><span class="sxs-lookup"><span data-stu-id="b4ab4-122">The following is an initial list, but you are not limited to it:</span></span>

-   <span data-ttu-id="b4ab4-123">.NET core y ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b4ab4-123">.NET Core and ASP.NET Core</span></span>
-   <span data-ttu-id="b4ab4-124">Node.js</span><span class="sxs-lookup"><span data-stu-id="b4ab4-124">Node.js</span></span>
-   <span data-ttu-id="b4ab4-125">Golang</span><span class="sxs-lookup"><span data-stu-id="b4ab4-125">Golang</span></span>
-   <span data-ttu-id="b4ab4-126">Java</span><span class="sxs-lookup"><span data-stu-id="b4ab4-126">Java</span></span>
-   <span data-ttu-id="b4ab4-127">Ruby</span><span class="sxs-lookup"><span data-stu-id="b4ab4-127">Ruby</span></span>
-   <span data-ttu-id="b4ab4-128">Plantillas de</span><span class="sxs-lookup"><span data-stu-id="b4ab4-128">Python</span></span>

<span data-ttu-id="b4ab4-129">Básicamente, puede usar cualquier lenguaje moderno admitido por Docker en Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="b4ab4-129">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="b4ab4-130">[Anterior] (orquestar-alta-escalabilidad-availability.md) [siguiente] (docker-aplicaciones-interna-bucle-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b4ab4-130">[Previous] (orchestrate-high-scalability-availability.md) [Next] (docker-apps-inner-loop-workflow.md)</span></span>
