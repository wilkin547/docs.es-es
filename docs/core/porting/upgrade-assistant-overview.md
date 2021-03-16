---
title: Información general sobre el Asistente para actualización de .NET
description: Introducción a la herramienta Asistente para actualización de .NET que ayuda a migrar desde .NET Framework y actualiza los proyectos a .NET 5.
author: ardalis
ms.date: 02/25/2021
ms.openlocfilehash: bd1c904586d170d93b76ae058914adb334289f89
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102108285"
---
# <a name="overview-of-the-net-upgrade-assistant"></a><span data-ttu-id="d836e-103">Información general sobre el Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="d836e-103">Overview of the .NET Upgrade Assistant</span></span>

<span data-ttu-id="d836e-104">Es posible que tenga aplicaciones que se ejecutan actualmente en .NET Framework que le interesa portar a .NET 5.</span><span class="sxs-lookup"><span data-stu-id="d836e-104">You might have apps that currently run on the .NET Framework that you're interested in porting to .NET 5.</span></span> <span data-ttu-id="d836e-105">La herramienta Asistente para actualización de .NET puede ayudarle con este proceso.</span><span class="sxs-lookup"><span data-stu-id="d836e-105">The .NET Upgrade Assistant tool can assist with this process.</span></span> <span data-ttu-id="d836e-106">En este artículo se proporciona:</span><span class="sxs-lookup"><span data-stu-id="d836e-106">This article provides:</span></span>

* <span data-ttu-id="d836e-107">Información general sobre el Asistente para actualización de .NET.</span><span class="sxs-lookup"><span data-stu-id="d836e-107">An overview of the .NET Upgrade Assistant.</span></span>
* <span data-ttu-id="d836e-108">Cómo instalar el Asistente para actualización de .NET.</span><span class="sxs-lookup"><span data-stu-id="d836e-108">How to install the .NET Upgrade Assistant.</span></span>

## <a name="what-is-the-net-upgrade-assistant"></a><span data-ttu-id="d836e-109">Qué es el Asistente para actualización de .NET.</span><span class="sxs-lookup"><span data-stu-id="d836e-109">What is the .NET Upgrade Assistant</span></span>

<span data-ttu-id="d836e-110">El Asistente para actualización de .NET es una herramienta de línea de comandos que se puede ejecutar en diferentes tipos de aplicaciones .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d836e-110">The .NET Upgrade Assistant is a command-line tool that can be run on different kinds of .NET Framework apps.</span></span> <span data-ttu-id="d836e-111">Está diseñado para facilitar la actualización de aplicaciones de .NET Framework a .NET 5.</span><span class="sxs-lookup"><span data-stu-id="d836e-111">It's designed to assist with upgrading .NET Framework apps to .NET 5.</span></span> <span data-ttu-id="d836e-112">Después de ejecutar la herramienta, **en la mayoría de los casos, la aplicación necesitará más esfuerzo para completar la migración**.</span><span class="sxs-lookup"><span data-stu-id="d836e-112">After running the tool, **in most cases the app will require more effort to complete the migration**.</span></span> <span data-ttu-id="d836e-113">La herramienta incluye la instalación de analizadores que pueden ayudarle a completar la migración.</span><span class="sxs-lookup"><span data-stu-id="d836e-113">The tool includes the installation of analyzers that can assist with completing the migration.</span></span>

<span data-ttu-id="d836e-114">Actualmente, la herramienta admite los siguientes tipos de aplicaciones .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d836e-114">Currently the tool supports the following .NET Framework app types:</span></span>

- <span data-ttu-id="d836e-115">Aplicaciones .NET Framework de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d836e-115">.NET Framework Windows Forms apps</span></span>
- <span data-ttu-id="d836e-116">Aplicaciones .NET Framework de WPF</span><span class="sxs-lookup"><span data-stu-id="d836e-116">.NET Framework WPF apps</span></span>
- <span data-ttu-id="d836e-117">Aplicaciones .NET Framework de ASP.NET de MVC</span><span class="sxs-lookup"><span data-stu-id="d836e-117">.NET Framework ASP.NET MVC apps</span></span>
- <span data-ttu-id="d836e-118">Aplicaciones de consola .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d836e-118">.NET Framework console apps</span></span>
- <span data-ttu-id="d836e-119">Bibliotecas de clases de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d836e-119">.NET Framework class libraries</span></span>

<span data-ttu-id="d836e-120">El Asistente para actualización de .NET está actualmente en versión preliminar y recibe actualizaciones frecuentes.</span><span class="sxs-lookup"><span data-stu-id="d836e-120">The .NET Upgrade Assistant is currently prerelease and is receiving frequent updates.</span></span> <span data-ttu-id="d836e-121">Si detecta problemas con la herramienta, notifíquelos en el [repositorio de GitHub](https://github.com/dotnet/upgrade-assistant) de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="d836e-121">If you discover problems using the tool, please report them in the tool's [GitHub repository](https://github.com/dotnet/upgrade-assistant).</span></span>

## <a name="how-to-install-the-net-upgrade-assistant"></a><span data-ttu-id="d836e-122">Cómo instalar el Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="d836e-122">How to install the .NET Upgrade Assistant</span></span>

<span data-ttu-id="d836e-123">El [Tutorial de introducción](https://aka.ms/dotnet-upgrade-assistant-install) le guía a través de la instalación y el uso del Asistente para actualización de .NET.</span><span class="sxs-lookup"><span data-stu-id="d836e-123">The [Get Started tutorial](https://aka.ms/dotnet-upgrade-assistant-install) walks through how to install and use the .NET Upgrade Assistant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="d836e-124">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d836e-124">Prerequisites</span></span>

1. <span data-ttu-id="d836e-125">Esta herramienta usa MSBuild para trabajar con archivos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="d836e-125">This tool uses MSBuild to work with project files.</span></span> <span data-ttu-id="d836e-126">Asegúrese de que hay instalada una versión reciente de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="d836e-126">Make sure that a recent version of MSBuild is installed.</span></span> <span data-ttu-id="d836e-127">Una manera fácil de hacerlo es [instalar Visual Studio 2019](https://visualstudio.microsoft.com/downloads/).</span><span class="sxs-lookup"><span data-stu-id="d836e-127">An easy way to do this is to [install Visual Studio 2019](https://visualstudio.microsoft.com/downloads/).</span></span>
1. <span data-ttu-id="d836e-128">Esta herramienta depende de [try-convert](https://github.com/dotnet/try-convert).</span><span class="sxs-lookup"><span data-stu-id="d836e-128">This tool depends on [try-convert](https://github.com/dotnet/try-convert).</span></span> <span data-ttu-id="d836e-129">Para que la herramienta se ejecute correctamente, debe instalar la herramienta try-convert para convertir los archivos de proyecto al nuevo estilo de SDK.</span><span class="sxs-lookup"><span data-stu-id="d836e-129">In order for the tool to run correctly, you must install the try-convert tool for converting project files to the new SDK style.</span></span> <span data-ttu-id="d836e-130">Si ya tiene instalado **try-convert**, puede que tenga que actualizarlo (ya que **upgrade-assistant** depende de la versión _0.7.212201_ o una versión posterior).</span><span class="sxs-lookup"><span data-stu-id="d836e-130">If you already have **try-convert** installed, you may need to update it instead (since **upgrade-assistant** depends on version _0.7.212201_ or later)</span></span>
    1. <span data-ttu-id="d836e-131">Para instalar try-convert: `dotnet tool install -g try-convert`</span><span class="sxs-lookup"><span data-stu-id="d836e-131">To install try-convert: `dotnet tool install -g try-convert`</span></span>
    1. <span data-ttu-id="d836e-132">Para actualizar try-convert: `dotnet tool update -g try-convert`</span><span class="sxs-lookup"><span data-stu-id="d836e-132">To update try-convert: `dotnet tool update -g try-convert`</span></span>

### <a name="installation-steps"></a><span data-ttu-id="d836e-133">Pasos de instalación</span><span class="sxs-lookup"><span data-stu-id="d836e-133">Installation steps</span></span>

<span data-ttu-id="d836e-134">La herramienta se puede instalar como una herramienta de la CLI de .NET; para ello, ejecute: `dotnet tool install -g upgrade-assistant --add-source https://pkgs.dev.azure.com/dnceng/public/_packaging/dotnet-tools/nuget/v3/index.json`</span><span class="sxs-lookup"><span data-stu-id="d836e-134">The tool can be installed as a .NET CLI tool by running: `dotnet tool install -g upgrade-assistant --add-source https://pkgs.dev.azure.com/dnceng/public/_packaging/dotnet-tools/nuget/v3/index.json`</span></span>

<span data-ttu-id="d836e-135">Del mismo modo, puesto que el Asistente para actualización de .NET se instala como una herramienta de la CLI de .NET, puede actualizarse fácilmente; para ello, ejecute: `https://pkgs.dev.azure.com/dnceng/public/_packaging/dotnet-tools/nuget/v3/index.json`</span><span class="sxs-lookup"><span data-stu-id="d836e-135">Similarly, because the .NET Upgrade Assistant is installed as a .NET CLI tool, it can be easily updated by running: `https://pkgs.dev.azure.com/dnceng/public/_packaging/dotnet-tools/nuget/v3/index.json`</span></span>

<span data-ttu-id="d836e-136">Para obtener instrucciones detalladas, consulte el archivo [README](https://github.com/dotnet/upgrade-assistant) del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d836e-136">For detailed installation instructions, please refer to the project's [README](https://github.com/dotnet/upgrade-assistant).</span></span>

## <a name="see-also"></a><span data-ttu-id="d836e-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="d836e-137">See also</span></span>

- [<span data-ttu-id="d836e-138">Actualización de una aplicación de WPF a .NET 5 con el Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="d836e-138">Upgrade a WPF App to .NET 5 with the .NET Upgrade Assistant</span></span>](upgrade-assistant-wpf-framework.md)
- [<span data-ttu-id="d836e-139">Actualización de una aplicación de Windows Forms a .NET 5 con el Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="d836e-139">Upgrade a Windows Forms App to .NET 5 with the .NET Upgrade Assistant</span></span>](upgrade-assistant-winforms-framework.md)
- [<span data-ttu-id="d836e-140">Actualización de una aplicación ASP.NET de MVC a .NET 5 con el Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="d836e-140">Upgrade an ASP.NET MVC App to .NET 5 with the .NET Upgrade Assistant</span></span>](upgrade-assistant-aspnetmvc.md)
- [<span data-ttu-id="d836e-141">Repositorio de GitHub del Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="d836e-141">.NET Upgrade Assistant GitHub Repository</span></span>](https://github.com/dotnet/upgrade-assistant)
