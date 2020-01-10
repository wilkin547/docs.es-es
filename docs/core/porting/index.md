---
title: Portabilidad de .NET Framework a .NET Core
description: Comprenda el proceso de portabilidad y descubra herramientas que le pueden resultar útiles al realizar la portabilidad de un proyecto de .NET Framework a .NET Core.
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: b5b010acbccf134afe800aa5bb98a0ae6e9ffa25
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777355"
---
# <a name="overview-of-porting-from-net-framework-to-net-core"></a><span data-ttu-id="d7ab0-103">Introducción a la portabilidad de .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="d7ab0-103">Overview of porting from .NET Framework to .NET Core</span></span>

<span data-ttu-id="d7ab0-104">Es posible que tenga código que se ejecuta actualmente en .NET Framework que le interesa portar a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-104">You might have code that currently runs on the .NET Framework that you're interested in porting to .NET Core.</span></span> <span data-ttu-id="d7ab0-105">En este artículo se proporciona:</span><span class="sxs-lookup"><span data-stu-id="d7ab0-105">This article provides:</span></span>

* <span data-ttu-id="d7ab0-106">Una introducción al proceso de portabilidad.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-106">An overview of the porting process.</span></span>
* <span data-ttu-id="d7ab0-107">Una lista de las herramientas que puede encontrar de utilidad al portar el código a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-107">A list of tools that you may find helpful when you're porting your code to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="d7ab0-108">Introducción al proceso de portabilidad</span><span class="sxs-lookup"><span data-stu-id="d7ab0-108">Overview of the porting process</span></span>

<span data-ttu-id="d7ab0-109">Le recomendamos que use el siguiente proceso al portar un proyecto a .NET Core:</span><span class="sxs-lookup"><span data-stu-id="d7ab0-109">We recommend you use the following process when porting your project to .NET Core:</span></span>

1. <span data-ttu-id="d7ab0-110">Redirija todos los proyectos que quiere portar a .NET Framework 4.7.2 o versiones superiores.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-110">Retarget all projects you wish to port to target .NET Framework 4.7.2 or higher.</span></span>

   <span data-ttu-id="d7ab0-111">Este paso garantiza que puede usar alternativas de API para destinos específicos de .NET Framework en los casos donde .NET Core no admite una API determinada.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-111">This step ensures that you can use API alternatives for .NET Framework-specific targets when .NET Core doesn't support a particular API.</span></span>

2. <span data-ttu-id="d7ab0-112">Use el [Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md) para analizar los ensamblados y ver si se pueden portar a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-112">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to analyze your assemblies and see if they're portable to .NET Core.</span></span>

   <span data-ttu-id="d7ab0-113">La herramienta Analizador de portabilidad de API analiza los ensamblados compilados y genera un informe.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-113">The API Portability Analyzer tool analyzes your compiled assemblies and generates a report.</span></span> <span data-ttu-id="d7ab0-114">Este informe muestra un resumen de portabilidad de alto nivel y un desglose de cada API que está usando y que no está disponible en NET Core.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-114">This report shows a high-level portability summary and a breakdown of each API you're using that isn't available on NET Core.</span></span>

3. <span data-ttu-id="d7ab0-115">Instale el [analizador de API de .NET](../../standard/analyzers/api-analyzer.md) en los proyectos para identificar las API que inician <xref:System.PlatformNotSupportedException> en algunas plataformas y otros posibles problemas de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-115">Install the [.NET API analyzer](../../standard/analyzers/api-analyzer.md) into your projects to identify APIs throwing <xref:System.PlatformNotSupportedException> on some platforms and some other potential compatibility issues.</span></span>

   <span data-ttu-id="d7ab0-116">Esta herramienta es similar al analizador de portabilidad, pero en lugar de analizar si las cosas se pueden basar en .NET Core, analiza si se usa una API de una forma que iniciará <xref:System.PlatformNotSupportedException> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-116">This tool is similar to the portability analyzer, but instead of analyzing if things can build on .NET Core, it analyzes if you're using an API in a way that will throw the <xref:System.PlatformNotSupportedException> at run time.</span></span> <span data-ttu-id="d7ab0-117">Aunque esto no es habitual si va a realizar la portabilidad desde .NET Framework 4.7.2 o superior, es conveniente comprobarlo.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-117">Although this isn't common if you're moving from .NET Framework 4.7.2 or higher, it's good to check.</span></span>

4. <span data-ttu-id="d7ab0-118">Convierta todas las dependencias de `packages.config` en el formato de [PackageReference](/nuget/consume-packages/package-references-in-project-files) con la [herramienta de conversión en Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).</span><span class="sxs-lookup"><span data-stu-id="d7ab0-118">Convert all of your `packages.config` dependencies to the [PackageReference](/nuget/consume-packages/package-references-in-project-files) format with the [conversion tool in Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).</span></span>

   <span data-ttu-id="d7ab0-119">Este paso implica convertir las dependencias del formato `packages.config` heredado.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-119">This step involves converting your dependencies from the legacy `packages.config` format.</span></span> <span data-ttu-id="d7ab0-120">`packages.config` no funciona en .NET Core, por lo que esta conversión es necesaria si tiene dependencias de paquete.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-120">`packages.config` doesn't work on .NET Core, so this conversion is required if you have package dependencies.</span></span>

5. <span data-ttu-id="d7ab0-121">Cree nuevos proyectos para .NET Core y copie en los archivos de código fuente, o intente convertir el archivo de proyecto existente con una herramienta.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-121">Create new projects for .NET Core and copy over source files, or attempt to convert your existing project file with a tool.</span></span>

   <span data-ttu-id="d7ab0-122">.NET Core usa un [formato de archivo de proyecto](../tools/csproj.md) simplificado y diferente al de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-122">.NET Core uses a simplified (and different) [project file format](../tools/csproj.md) than .NET Framework.</span></span> <span data-ttu-id="d7ab0-123">Deberá convertir los archivos de proyecto en este formato para continuar.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-123">You'll need to convert your project files into this format to continue.</span></span>

6. <span data-ttu-id="d7ab0-124">Porte el código de prueba.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-124">Port your test code.</span></span>

   <span data-ttu-id="d7ab0-125">Dado que portar a .NET Core es un cambio considerable para el código base, se recomienda encarecidamente portar las proyectos de prueba de forma que se puedan ejecutar mientras porta el código.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-125">Because porting to .NET Core is such a significant change to your codebase, it's highly recommended to port your test projects so that you can run tests as you port your code over.</span></span> <span data-ttu-id="d7ab0-126">MSTest, xUnit y NUnit funcionan en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-126">MSTest, xUnit, and NUnit all work on .NET Core.</span></span>

<span data-ttu-id="d7ab0-127">Además, puede intentar portar soluciones más pequeñas o proyectos individuales en una operación en el formato de archivo de proyecto de .NET Core con la herramienta [dotnet try-convert](https://github.com/dotnet/try-convert).</span><span class="sxs-lookup"><span data-stu-id="d7ab0-127">Additionally, you can attempt to port smaller solutions or individual projects in one operation to the .NET Core project file format with the [dotnet try-convert](https://github.com/dotnet/try-convert) tool.</span></span> <span data-ttu-id="d7ab0-128">No hay ninguna garantía de que `dotnet try-convert` funcione con todos los proyectos y puede provocar cambios sutiles de comportamiento de los que dependa.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-128">`dotnet try-convert` is not guaranteed to work for all your projects, and it may cause subtle changes in behavior that you depended on.</span></span> <span data-ttu-id="d7ab0-129">Use esta herramienta como _punto inicial_ que automatice los elementos básicos que se pueden automatizar.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-129">Use it as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="d7ab0-130">No es una solución garantizada para migrar un proyecto.</span><span class="sxs-lookup"><span data-stu-id="d7ab0-130">It isn't a guaranteed solution to migrating a project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d7ab0-131">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d7ab0-131">Next steps</span></span>

>[!div class="nextstepaction"]
>[<span data-ttu-id="d7ab0-132">Tecnologías no disponibles en .NET Core</span><span class="sxs-lookup"><span data-stu-id="d7ab0-132">Unavailable technologies on .NET Core</span></span>](net-framework-tech-unavailable.md)
