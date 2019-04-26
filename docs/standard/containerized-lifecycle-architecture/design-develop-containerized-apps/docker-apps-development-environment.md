---
title: Entorno de desarrollo para aplicaciones de Docker
description: Familiarícese con las opciones de herramienta de desarrollo más importantes que admiten el ciclo de vida de desarrollo de Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 3a2fcbe3b9380083622b6ce72cea4bab17d7c2ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61799325"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="2f459-103">Entorno de desarrollo para aplicaciones de Docker</span><span class="sxs-lookup"><span data-stu-id="2f459-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="2f459-104">Opciones de herramientas de desarrollo: IDE o editor</span><span class="sxs-lookup"><span data-stu-id="2f459-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="2f459-105">Sin importar si lo prefiere, un IDE eficaz y completo o un editor ligero y ágil, Microsoft le puede ayudar en cuanto a desarrollar aplicaciones de Docker.</span><span class="sxs-lookup"><span data-stu-id="2f459-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="2f459-106">Visual Studio Code y CLI de Docker (Herramientas multiplataforma para Mac, Linux y Windows)</span><span class="sxs-lookup"><span data-stu-id="2f459-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="2f459-107">Si prefiere un editor ligero y multiplataforma que admiten cualquier lenguaje de desarrollo, puede usar Visual Studio Code y CLI de Docker.</span><span class="sxs-lookup"><span data-stu-id="2f459-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="2f459-108">Estos productos proporcionan una experiencia sencilla y sólida que es fundamental para optimizar el flujo de trabajo de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="2f459-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="2f459-109">Al instalar "Docker para Mac" o "Docker para Windows" (entorno de desarrollo), los desarrolladores de Docker pueden utilizar una sola CLI de Docker para crear aplicaciones para Windows o Linux (entorno de tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="2f459-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="2f459-110">Además, Visual Studio Code admite extensiones para Docker con IntelliSense para Dockerfiles y tareas de acceso directo ejecutar comandos de Docker desde el editor.</span><span class="sxs-lookup"><span data-stu-id="2f459-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
>
> <span data-ttu-id="2f459-111">Para descargar el código de Visual Studio, vaya a <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="2f459-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>
>
> <span data-ttu-id="2f459-112">Para descargar Docker para Mac y Windows, vaya a <https://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="2f459-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a><span data-ttu-id="2f459-113">Visual Studio con las herramientas de Docker (máquina de desarrollo de Windows)</span><span class="sxs-lookup"><span data-stu-id="2f459-113">Visual Studio with Docker Tools (Windows development machine)</span></span>

<span data-ttu-id="2f459-114">Se recomienda usar Visual Studio 2017 (o posterior) con las herramientas integradas de Docker habilitado.</span><span class="sxs-lookup"><span data-stu-id="2f459-114">We recommend you use Visual Studio 2017 (or later) with the built-in Docker Tools enabled.</span></span> <span data-ttu-id="2f459-115">Con Visual Studio, puede desarrollar, ejecutar y validar sus aplicaciones directamente en el entorno de Docker elegido.</span><span class="sxs-lookup"><span data-stu-id="2f459-115">With Visual Studio, you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="2f459-116">Presione F5 para depurar la aplicación (único contenedor o varios contenedores) directamente en un host de Docker, o presione Ctrl + F5 para editar y actualizar la aplicación sin tener que recompilar el contenedor.</span><span class="sxs-lookup"><span data-stu-id="2f459-116">Press F5 to debug your application (single container or multiple containers) directly in a Docker host, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="2f459-117">Es la opción más sencilla y más eficaces para desarrolladores de Windows crear contenedores de Docker para Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="2f459-117">It's the simplest and most powerful choice for Windows developers to create Docker containers for Linux or Windows.</span></span>

### <a name="visual-studio-for-mac-mac-development-machine"></a><span data-ttu-id="2f459-118">Visual Studio para Mac (máquina de desarrollo de Mac)</span><span class="sxs-lookup"><span data-stu-id="2f459-118">Visual Studio for Mac (Mac development machine)</span></span>

<span data-ttu-id="2f459-119">Puede usar [Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) al desarrollar aplicaciones basadas en Docker.</span><span class="sxs-lookup"><span data-stu-id="2f459-119">You can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) when developing Docker-based applications.</span></span> <span data-ttu-id="2f459-120">Visual Studio para Mac ofrece un IDE más rico en comparación con el código de Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="2f459-120">Visual Studio for Mac offers a richer IDE when compared to Visual Studio Code for Mac.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="2f459-121">Opciones de idioma y marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="2f459-121">Language and framework choices</span></span>

<span data-ttu-id="2f459-122">Puede desarrollar aplicaciones de Docker con herramientas de Microsoft con los lenguajes más modernos.</span><span class="sxs-lookup"><span data-stu-id="2f459-122">You can develop Docker applications using Microsoft tools with most modern languages.</span></span> <span data-ttu-id="2f459-123">La siguiente es una lista inicial, pero no está limitado a él:</span><span class="sxs-lookup"><span data-stu-id="2f459-123">The following is an initial list, but you're not limited to it:</span></span>

- <span data-ttu-id="2f459-124">.NET Core y ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2f459-124">.NET Core and ASP.NET Core</span></span>
- <span data-ttu-id="2f459-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="2f459-125">Node.js</span></span>
- <span data-ttu-id="2f459-126">Ir</span><span class="sxs-lookup"><span data-stu-id="2f459-126">Go</span></span>
- <span data-ttu-id="2f459-127">Java</span><span class="sxs-lookup"><span data-stu-id="2f459-127">Java</span></span>
- <span data-ttu-id="2f459-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="2f459-128">Ruby</span></span>
- <span data-ttu-id="2f459-129">Python</span><span class="sxs-lookup"><span data-stu-id="2f459-129">Python</span></span>

<span data-ttu-id="2f459-130">Básicamente, puede usar cualquier lenguaje moderno compatible con Docker en Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="2f459-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2f459-131">[Anterior](deploy-azure-kubernetes-service.md)
>[Siguiente](docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2f459-131">[Previous](deploy-azure-kubernetes-service.md)
[Next](docker-apps-inner-loop-workflow.md)</span></span>
