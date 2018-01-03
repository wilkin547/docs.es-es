---
title: Portabilidad a .NET Core desde .NET Framework
description: "Comprenda el proceso de portabilidad y descubra herramientas que le pueden resultar útiles al realizar la portabilidad de un proyecto de .NET Framework a .NET Core."
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 00d00d38-99af-44f4-a75f-defcd9729dc5
ms.workload: dotnetcore
ms.openlocfilehash: 3413b73c2a0a3c3ebf49b0b3ec81d00c6558d9a8
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="porting-to-net-core-from-net-framework"></a><span data-ttu-id="e4cca-104">Portabilidad a .NET Core desde .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e4cca-104">Porting to .NET Core from .NET Framework</span></span>

<span data-ttu-id="e4cca-105">Si tiene código que se ejecuta en .NET Framework, puede que le interese ejecutarlo en .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="e4cca-105">If you've got code running on the .NET Framework, you may be interested in running your code on .NET Core 1.0.</span></span>  <span data-ttu-id="e4cca-106">Este artículo es una introducción al proceso de portabilidad y describe una lista de las herramientas que puede encontrar de utilidad al realizar la portabilidad a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e4cca-106">This article covers an overview of the porting process and a list of the tools you may find helpful when porting to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="e4cca-107">Información general sobre el proceso de portabilidad</span><span class="sxs-lookup"><span data-stu-id="e4cca-107">Overview of the Porting Process</span></span>

<span data-ttu-id="e4cca-108">El proceso recomendado para realizar la portabilidad sigue estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e4cca-108">The recommended process for porting follows the following series of steps.</span></span>  <span data-ttu-id="e4cca-109">Cada una de estas partes del proceso se trata con más detalle en otros artículos.</span><span class="sxs-lookup"><span data-stu-id="e4cca-109">Each of these parts of the process are covered in more detail in further articles.</span></span>

1. <span data-ttu-id="e4cca-110">Identifique y tenga en cuenta las dependencias de terceros.</span><span class="sxs-lookup"><span data-stu-id="e4cca-110">Identify and account for your third-party dependencies.</span></span>

   <span data-ttu-id="e4cca-111">Esto implica comprender lo que son las dependencias de terceros, cómo depende de ellas, cómo ver si también se ejecutan en .NET Core y los pasos que puede seguir si no lo hacen.</span><span class="sxs-lookup"><span data-stu-id="e4cca-111">This will involve understanding what your third-party dependencies are, how you depend on them, how to see if they also run on .NET Core, and steps you can take if they don't.</span></span>
   
2. <span data-ttu-id="e4cca-112">Redirigir todos los proyectos que desee portar a .NET Framework 4.6.2 de destino.</span><span class="sxs-lookup"><span data-stu-id="e4cca-112">Retarget all projects you wish to port to target .NET Framework 4.6.2.</span></span>

   <span data-ttu-id="e4cca-113">Esto garantiza que puede usar alternativas de API para destinos específicos de .NET Framework en los casos donde .NET Core no pueda admitir una API determinada.</span><span class="sxs-lookup"><span data-stu-id="e4cca-113">This ensures that you can use API alternatives for .NET Framework-specific targets in the cases where .NET Core can't support a particular API.</span></span>
   
3. <span data-ttu-id="e4cca-114">Use la [herramienta API Portability Analyzer](https://github.com/Microsoft/dotnet-apiport/) para analizar los ensamblados y desarrollar un plan para realizar la portabilidad basándose en los resultados.</span><span class="sxs-lookup"><span data-stu-id="e4cca-114">Use the [API Portability Analyzer tool](https://github.com/Microsoft/dotnet-apiport/) to analyze your assemblies and develop a plan to port based on its results.</span></span>

   <span data-ttu-id="e4cca-115">Esta herramienta analiza los ensamblados compilados y genera un informe que muestra un resumen de portabilidad de alto nivel, junto con un desglose de cada API que usa que no está disponible en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e4cca-115">The API Portability Analyzer tool will analyze your compiled assemblies and generate a report which shows a high-level portability summary and a breakdown of each API you're using that isn't available on .NET Core.</span></span>  <span data-ttu-id="e4cca-116">Puede usar este informe junto con un análisis de su código base para desarrollar un plan de cómo portar el código.</span><span class="sxs-lookup"><span data-stu-id="e4cca-116">You can use this report alongside an analysis of your codebase to develop a plan for how you'll port your code over.</span></span>
   
4. <span data-ttu-id="e4cca-117">Porte el código de prueba.</span><span class="sxs-lookup"><span data-stu-id="e4cca-117">Port your tests code.</span></span>

   <span data-ttu-id="e4cca-118">Dado que portar a .NET Core es un cambio tan grande para el código base, se recomienda encarecidamente portar las pruebas de forma que pueda ejecutarlas mientras porta el código.</span><span class="sxs-lookup"><span data-stu-id="e4cca-118">Because porting to .NET Core is such a big change to your codebase, it's highly recommended to get your tests ported so that you can run tests as you port code over.</span></span>  <span data-ttu-id="e4cca-119">MSTest, xUnit y NUnit todos admiten actualmente .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="e4cca-119">MSTest, xUnit, and NUnit all support .NET Core 1.0 today.</span></span>
   
6. <span data-ttu-id="e4cca-120">Ejecute el plan de portabilidad.</span><span class="sxs-lookup"><span data-stu-id="e4cca-120">Execute your plan for porting!</span></span>

## <a name="tools-to-help"></a><span data-ttu-id="e4cca-121">Herramientas de ayuda</span><span class="sxs-lookup"><span data-stu-id="e4cca-121">Tools to help</span></span>

<span data-ttu-id="e4cca-122">Esta es una pequeña lista de las herramientas que puede encontrar de utilidad:</span><span class="sxs-lookup"><span data-stu-id="e4cca-122">Here's a short list of the tools you'll find helpful:</span></span>

* <span data-ttu-id="e4cca-123">NuGet: [Nuget Client](https://dist.nuget.org/index.html) o [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer), el administrador de paquetes de Microsoft para implementaciones de .NET.</span><span class="sxs-lookup"><span data-stu-id="e4cca-123">NuGet - [Nuget Client](https://dist.nuget.org/index.html) or [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer), Microsoft's package manager for .NET implementations.</span></span>
* <span data-ttu-id="e4cca-124">Api Portability Analyzer: [herramienta de línea de comandos](https://github.com/Microsoft/dotnet-apiport/releases) o [Visual Studio Extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b), una cadena de herramientas que puede generar un informe de lo portátil que es su código entre .NET Framework y .NET Core, con un desglose de problemas ensamblado por ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e4cca-124">Api Portability Analyzer - [command line tool](https://github.com/Microsoft/dotnet-apiport/releases) or [Visual Studio Extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b), a toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core, with an assembly-by-assembly breakdown of issues.</span></span>  <span data-ttu-id="e4cca-125">Para más información, consulte las [herramientas para ayudarle en el proceso](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).</span><span class="sxs-lookup"><span data-stu-id="e4cca-125">See [Tooling to help you on the process](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/) for more information.</span></span>
* <span data-ttu-id="e4cca-126">Reverse Package Search: un [servicio web útil](https://packagesearch.azurewebsites.net) que le permite buscar un tipo y encontrar los paquetes que lo contienen.</span><span class="sxs-lookup"><span data-stu-id="e4cca-126">Reverse Package Search - A [useful web service](https://packagesearch.azurewebsites.net) that allows you to search for a type and find packages containing that type.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e4cca-127">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e4cca-127">Next steps</span></span>

[<span data-ttu-id="e4cca-128">Análisis de las dependencias de terceros.</span><span class="sxs-lookup"><span data-stu-id="e4cca-128">Analyzing your third-party dependencies.</span></span>](third-party-deps.md)
   
