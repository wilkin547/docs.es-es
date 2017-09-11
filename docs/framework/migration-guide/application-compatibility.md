---
title: Compatibilidad de aplicaciones en .NET Framework
ms.custom: 
ms.date: 05/19/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
- app-compat
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
caps.latest.revision: 19
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b3c7df2984c2c9e8af308ca8070f7207d11ba49e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="application-compatibility-in-the-net-framework"></a><span data-ttu-id="20c35-102">Compatibilidad de aplicaciones en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="20c35-102">Application Compatibility in the .NET Framework</span></span>

## <a name="introduction"></a><span data-ttu-id="20c35-103">Introducción</span><span class="sxs-lookup"><span data-stu-id="20c35-103">Introduction</span></span>

<span data-ttu-id="20c35-104">La compatibilidad es un objetivo muy importante de cada versión .NET.</span><span class="sxs-lookup"><span data-stu-id="20c35-104">Compatibility is a very important goal of each .NET release.</span></span> <span data-ttu-id="20c35-105">La compatibilidad garantiza que cada versión es adicional, por lo que las versiones anteriores siguen funcionando.</span><span class="sxs-lookup"><span data-stu-id="20c35-105">Compatibility ensures that each version is additive, so previous versions will still work.</span></span> <span data-ttu-id="20c35-106">Por otro lado, los cambios en las funciones anteriores (para mejorar el rendimiento, tratar los problemas de seguridad o corregir errores) pueden provocar problemas de compatibilidad en el código existente o en las aplicaciones existentes que se ejecutan en una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="20c35-106">On the other hand, changes to previous functionality (to improve performance, address security issues, or fix bugs) can cause compatibility problems in existing code or existing applications that run under a later version.</span></span> <span data-ttu-id="20c35-107">.NET Framework reconoce los cambios de redestinación y los cambios en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="20c35-107">The .NET Framework recognizes retargeting changes and runtime changes.</span></span> <span data-ttu-id="20c35-108">Los cambios de redestinación afectan a las aplicaciones que se refieren a una versión específica de .NET Framework pero se ejecutan en una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="20c35-108">Retargeting changes affect applications that target a specific version of the .NET Framework but are running on a later version.</span></span> <span data-ttu-id="20c35-109">Los cambios en tiempo de ejecución afectan a todas las aplicaciones que se ejecutan en una versión determinada.</span><span class="sxs-lookup"><span data-stu-id="20c35-109">Runtime changes affect all applications running on a particular version.</span></span>

<span data-ttu-id="20c35-110">Cada aplicación se refiere a una versión específica de .NET Framework, que puede especificarse:</span><span class="sxs-lookup"><span data-stu-id="20c35-110">Each app targets a specific version of the .NET Framework, which can be specified by:</span></span>

- <span data-ttu-id="20c35-111">Al definir una plataforma de destino en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="20c35-111">Defining a target framework in Visual Studio.</span></span>
- <span data-ttu-id="20c35-112">Al especificar la plataforma de destino en un archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="20c35-112">Specifying the target framework in a project file.</span></span>
- <span data-ttu-id="20c35-113">Al aplicar <xref:System.Runtime.Versioning.TargetFrameworkAttribute> en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="20c35-113">Applying a <xref:System.Runtime.Versioning.TargetFrameworkAttribute> to the source code.</span></span>

<span data-ttu-id="20c35-114">Al ejecutarse en una versión más reciente que a la que se refería, .NET Framework usará un comportamiento anómalo para imitar la versión de destino anterior.</span><span class="sxs-lookup"><span data-stu-id="20c35-114">When running on a newer version than what was targeted, the .NET Framework will use quirked behavior to mimic the older targeted version.</span></span> <span data-ttu-id="20c35-115">En otras palabras, la aplicación se ejecutará en la versión más reciente de Framework pero actuará como si se estuviera ejecutando en la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="20c35-115">In other words, the app will run on the newer version of the Framework, but act as if it's running on the older version.</span></span> <span data-ttu-id="20c35-116">Muchos de los problemas de compatibilidad entre versiones de .NET Framework se mitigan a través de este peculiar modelo.</span><span class="sxs-lookup"><span data-stu-id="20c35-116">Many of the compatibility issues between versions of the .NET Framework are mitigated through this quirking model.</span></span>

## <a name="runtime-changes"></a><span data-ttu-id="20c35-117">Cambios en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="20c35-117">Runtime changes</span></span>

<span data-ttu-id="20c35-118">Los problemas en tiempo de ejecución son los que aparecen cuando se coloca un nuevo runtime en un equipo y se ejecutan los mismos binarios, pero se observa un comportamiento diferente.</span><span class="sxs-lookup"><span data-stu-id="20c35-118">Runtime issues are those that arise when a new runtime is placed on a machine and the same binaries are run, but different behavior is seen.</span></span> <span data-ttu-id="20c35-119">Si un binario se ha compilado para .NET Framework 4.0 se ejecutará en el modo de compatibilidad de .NET Framework 4.0 en 4.5 o en versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="20c35-119">If a binary was compiled for .NET Framework 4.0 it will run in .NET Framework 4.0 compatibility mode on 4.5 or later versions.</span></span> <span data-ttu-id="20c35-120">Muchos de los cambios que afectan a la versión 4.5 no afectarán a un binario compilado para 4.0.</span><span class="sxs-lookup"><span data-stu-id="20c35-120">Many of the changes that affect 4.5 will not affect a binary compiled for 4.0.</span></span> <span data-ttu-id="20c35-121">Esto es específico del AppDomain y depende de la configuración del ensamblado de entrada.</span><span class="sxs-lookup"><span data-stu-id="20c35-121">This is specific to the AppDomain and depends on the settings of the entry assembly.</span></span>

## <a name="retargeting-changes"></a><span data-ttu-id="20c35-122">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="20c35-122">Retargeting changes</span></span>

<span data-ttu-id="20c35-123">Los problemas de redestinación son los que aparecen cuando un ensamblado que se refería a la versión 4.0 ahora se establece para referirse a la versión 4.5.</span><span class="sxs-lookup"><span data-stu-id="20c35-123">Retargeting issues are those that arise when an assembly that was targeting 4.0 is now set to target 4.5.</span></span> <span data-ttu-id="20c35-124">Ahora el ensamblado participa en las características nuevas así como en los problemas de compatibilidad potenciales de las características antiguas.</span><span class="sxs-lookup"><span data-stu-id="20c35-124">Now the assembly opts into the new features as well as potential compatibility issues to old features.</span></span> <span data-ttu-id="20c35-125">De nuevo, esto lo indica el ensamblado de entrada; es decir, la aplicación de consola que usa el ensamblado, o el sitio web que hace referencia a este.</span><span class="sxs-lookup"><span data-stu-id="20c35-125">Again, this is dictated by the entry assembly, so the console app that uses the assembly, or the website that references the assembly.</span></span>

## <a name="net-compatibility-diagnostics"></a><span data-ttu-id="20c35-126">Diagnósticos de compatibilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="20c35-126">.NET Compatibility Diagnostics</span></span>

<span data-ttu-id="20c35-127">Los diagnósticos de compatibilidad de .NET son analizadores de Roslyn que ayudan a identificar problemas de compatibilidad de aplicaciones entre versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="20c35-127">The .NET Compatibility Diagnostics are Roslyn-powered analyzers that help identify application compatibility issues between versions of the .NET Framework.</span></span> <span data-ttu-id="20c35-128">Esta lista contiene todos los analizadores disponibles, aunque solo se aplicará un subconjunto de ellos a una migración determinada.</span><span class="sxs-lookup"><span data-stu-id="20c35-128">This list contains all of the analyzers available, although only a subset will apply to any specific migration.</span></span> <span data-ttu-id="20c35-129">Los analizadores determinarán qué problemas son aplicables para la migración planeada y serán los únicos que muestren.</span><span class="sxs-lookup"><span data-stu-id="20c35-129">The analyzers will determine which issues are applicable for the planned migration and will only surface those.</span></span>

<span data-ttu-id="20c35-130">Cada problema incluye la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="20c35-130">Each issue includes the following information:</span></span>

-   <span data-ttu-id="20c35-131">La descripción de los cambios con respecto a una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="20c35-131">The description of what has changed from a previous version.</span></span>

-   <span data-ttu-id="20c35-132">Cómo afecta el cambio a los clientes y si hay alguna solución alternativa disponible para mantener la compatibilidad entre versiones.</span><span class="sxs-lookup"><span data-stu-id="20c35-132">How the change affects customers and whether any workarounds are available to preserve compatibility across versions.</span></span>

-   <span data-ttu-id="20c35-133">Una valoración de la importancia que tiene el cambio.</span><span class="sxs-lookup"><span data-stu-id="20c35-133">An assessment of how important the change is.</span></span> <span data-ttu-id="20c35-134">Los problemas de compatibilidad de aplicaciones se dividen en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="20c35-134">Application compatibility issue are categorized as follows:</span></span>

    |   |   |
    |---|---|
    |<span data-ttu-id="20c35-135">Major</span><span class="sxs-lookup"><span data-stu-id="20c35-135">Major</span></span>|<span data-ttu-id="20c35-136">Un cambio significativo que afecta a un gran número de aplicaciones o que requiere una modificación sustancial del código.</span><span class="sxs-lookup"><span data-stu-id="20c35-136">A significant change that affects a large number of apps or requires substantial modification of code.</span></span>|
    |<span data-ttu-id="20c35-137">Secundaria</span><span class="sxs-lookup"><span data-stu-id="20c35-137">Minor</span></span>|<span data-ttu-id="20c35-138">Un cambio que afecta a un pequeño número de aplicaciones o que requiere una leve modificación del código.</span><span class="sxs-lookup"><span data-stu-id="20c35-138">A change that affects a small number of apps or that requires minor modification of code.</span></span>|
    |<span data-ttu-id="20c35-139">Caso avanzado</span><span class="sxs-lookup"><span data-stu-id="20c35-139">Edge case</span></span>|<span data-ttu-id="20c35-140">Un cambio que afecta a aplicaciones en situaciones muy concretas y poco frecuentes.</span><span class="sxs-lookup"><span data-stu-id="20c35-140">A change that affects apps under very specific, uncommon scenarios.</span></span>|
    |<span data-ttu-id="20c35-141">Transparente</span><span class="sxs-lookup"><span data-stu-id="20c35-141">Transparent</span></span>|<span data-ttu-id="20c35-142">Un cambio que no tiene ningún efecto apreciable para el desarrollador o el usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="20c35-142">A change with no noticeable effect on the application's developer or user.</span></span>|

-   <span data-ttu-id="20c35-143">La versión, que indica la primera aparición del cambio en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="20c35-143">Version indicates when the change first appears in the framework.</span></span> <span data-ttu-id="20c35-144">Algunos de los cambios se presentan en una versión determinada y se revierten en una versión posterior; que también se indica.</span><span class="sxs-lookup"><span data-stu-id="20c35-144">Some of the changes are introduced in a particular version and reverted in a later version; that is indicated as well.</span></span>

-   <span data-ttu-id="20c35-145">El tipo de cambio:</span><span class="sxs-lookup"><span data-stu-id="20c35-145">The type of change:</span></span>

    |   |   |
    |---|---|
    |<span data-ttu-id="20c35-146">Redestinación</span><span class="sxs-lookup"><span data-stu-id="20c35-146">Retargeting</span></span>|<span data-ttu-id="20c35-147">El cambio afecta a aplicaciones que se vuelven a compilar para tener como destino una nueva versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="20c35-147">The change affects apps that are recompiled to target a new version of the .NET Framework.</span></span>|
    |<span data-ttu-id="20c35-148">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="20c35-148">Runtime</span></span>|<span data-ttu-id="20c35-149">El cambio afecta a una aplicación existente que tiene como destino una versión anterior de .NET Framework, pero que se ejecuta en una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="20c35-149">The change affects an existing app that targets a previous version of the .NET Framework but runs on a later version.</span></span>|

-   <span data-ttu-id="20c35-150">Las API afectadas, si las hubiera.</span><span class="sxs-lookup"><span data-stu-id="20c35-150">The affected APIS, if any.</span></span>

-   <span data-ttu-id="20c35-151">Los identificadores de los diagnósticos disponibles.</span><span class="sxs-lookup"><span data-stu-id="20c35-151">The IDs of the available diagnostics</span></span>

## <a name="usage"></a><span data-ttu-id="20c35-152">Uso</span><span class="sxs-lookup"><span data-stu-id="20c35-152">Usage</span></span>

<span data-ttu-id="20c35-153">Para comenzar, seleccione el tipo de cambio de compatibilidad a continuación:</span><span class="sxs-lookup"><span data-stu-id="20c35-153">To begin, select the type of compatibility change below:</span></span>

- [<span data-ttu-id="20c35-154">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="20c35-154">Retargeting Changes</span></span>](./retargeting/index.md)
- [<span data-ttu-id="20c35-155">Cambios en el runtime</span><span class="sxs-lookup"><span data-stu-id="20c35-155">Runtime Changes</span></span>](./runtime/index.md)


## <a name="see-also"></a><span data-ttu-id="20c35-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="20c35-156">See also</span></span>

<span data-ttu-id="20c35-157">[Versiones y dependencias](../../../docs/framework/migration-guide/versions-and-dependencies.md) </span><span class="sxs-lookup"><span data-stu-id="20c35-157">[Versions and Dependencies](../../../docs/framework/migration-guide/versions-and-dependencies.md) </span></span>  
<span data-ttu-id="20c35-158">[Novedades](../../../docs/framework/whats-new/index.md) </span><span class="sxs-lookup"><span data-stu-id="20c35-158">[What's New](../../../docs/framework/whats-new/index.md) </span></span>  
[<span data-ttu-id="20c35-159">Lo obsoleto en la biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="20c35-159">What's Obsolete in the Class Library</span></span>](../../../docs/framework/whats-new/whats-obsolete.md)

