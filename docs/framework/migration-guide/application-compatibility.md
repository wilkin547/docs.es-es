---
title: 'Cambios de runtime y redestinación: .NET Framework'
description: Obtenga información sobre la compatibilidad de las aplicaciones en .NET Framework y cómo se ve afectada por los cambios del entorno de ejecución y la redestinación al migrar a otra versión.
ms.date: 10/29/2019
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
ms.openlocfilehash: 26f36dd34c6c5ecae8fc5ab373ff60d9e56f8245
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475494"
---
# <a name="application-compatibility-in-the-net-framework"></a><span data-ttu-id="4b29e-103">Compatibilidad de aplicaciones en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4b29e-103">Application compatibility in the .NET Framework</span></span>

<span data-ttu-id="4b29e-104">La compatibilidad es un objetivo importante de todas las versiones de .NET.</span><span class="sxs-lookup"><span data-stu-id="4b29e-104">Compatibility is an important goal of each .NET release.</span></span> <span data-ttu-id="4b29e-105">La compatibilidad garantiza que cada versión es aditiva, para que las versiones anteriores sigan funcionando.</span><span class="sxs-lookup"><span data-stu-id="4b29e-105">Compatibility ensures that each version is additive, so previous versions will continue to work.</span></span> <span data-ttu-id="4b29e-106">Por otro lado, los cambios en las funciones anteriores (por ejemplo para mejorar el rendimiento, abordar problemas de seguridad o corregir errores) pueden provocar problemas de compatibilidad en el código o las aplicaciones existentes que se ejecutan en una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="4b29e-106">On the other hand, changes to previous functionality (for example, to improve performance, address security issues, or fix bugs) can cause compatibility problems in existing code or existing applications that run under a later version.</span></span>

<span data-ttu-id="4b29e-107">Cada aplicación se destina a una versión específica de .NET Framework de esta forma:</span><span class="sxs-lookup"><span data-stu-id="4b29e-107">Each app targets a specific version of the .NET Framework by:</span></span>

- <span data-ttu-id="4b29e-108">Al definir una plataforma de destino en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4b29e-108">Defining a target framework in Visual Studio.</span></span>
- <span data-ttu-id="4b29e-109">Al especificar la plataforma de destino en un archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b29e-109">Specifying the target framework in a project file.</span></span>
- <span data-ttu-id="4b29e-110">Al aplicar <xref:System.Runtime.Versioning.TargetFrameworkAttribute> en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="4b29e-110">Applying a <xref:System.Runtime.Versioning.TargetFrameworkAttribute> to the source code.</span></span>

<span data-ttu-id="4b29e-111">Al migrar desde una versión de .NET Framework a otra, hay dos tipos de cambios que se deben tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="4b29e-111">When migrating from one version of the .NET Framework to another, there are two types of changes to consider:</span></span>

- [<span data-ttu-id="4b29e-112">Cambios en el runtime</span><span class="sxs-lookup"><span data-stu-id="4b29e-112">Runtime changes</span></span>](#runtime-changes)
- [<span data-ttu-id="4b29e-113">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="4b29e-113">Retargeting changes</span></span>](#retargeting-changes)

## <a name="runtime-changes"></a><span data-ttu-id="4b29e-114">Cambios en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4b29e-114">Runtime changes</span></span>

<span data-ttu-id="4b29e-115">Los problemas en tiempo de ejecución son los que aparecen cuando se coloca un nuevo runtime en un equipo y cambia el comportamiento de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b29e-115">Runtime issues are those that arise when a new runtime is placed on a machine and an app's behavior changes.</span></span> <span data-ttu-id="4b29e-116">Al ejecutarse en una versión más reciente que la seleccionada como destino, .NET Framework usa un comportamiento *anómalo* para imitar la versión de destino anterior.</span><span class="sxs-lookup"><span data-stu-id="4b29e-116">When running on a newer version than what was targeted, the .NET Framework uses *quirked* behavior to mimic the older targeted version.</span></span> <span data-ttu-id="4b29e-117">La aplicación se ejecuta en la versión más reciente, pero actúa como si se ejecutara en la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="4b29e-117">The app runs on the newer version but acts as if it's running on the older version.</span></span> <span data-ttu-id="4b29e-118">Muchos de los problemas de compatibilidad entre versiones de .NET Framework se mitigan a través de este peculiar modelo.</span><span class="sxs-lookup"><span data-stu-id="4b29e-118">Many of the compatibility issues between versions of the .NET Framework are mitigated through this quirking model.</span></span> <span data-ttu-id="4b29e-119">Por ejemplo, si un binario se ha compilado para .NET Framework 4.0 pero se ejecuta en un equipo con .NET Framework 4.5 o posterior, se ejecuta en el modo de compatibilidad de .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="4b29e-119">For example, if a binary was compiled for .NET Framework 4.0 but runs on a machine with .NET Framework 4.5 or later, it runs in .NET Framework 4.0 compatibility mode.</span></span> <span data-ttu-id="4b29e-120">Esto significa que muchos de los cambios de la versión posterior no afectan al binario.</span><span class="sxs-lookup"><span data-stu-id="4b29e-120">This means that many of the changes in the later version don't affect the binary.</span></span>

<span data-ttu-id="4b29e-121">La versión de .NET Framework a la que se destina una aplicación se determina por la versión de destino del ensamblado de entrada para el dominio de aplicación en el que se ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="4b29e-121">The version of the .NET Framework that an application targets is determined by the target version of the entry assembly for the application domain that the code runs in.</span></span> <span data-ttu-id="4b29e-122">Todos los ensamblados adicionales que se cargan en ese dominio de aplicación tienen como destino esa versión.</span><span class="sxs-lookup"><span data-stu-id="4b29e-122">All additional assemblies loaded in that application domain target that version.</span></span> <span data-ttu-id="4b29e-123">Por ejemplo, en el caso de un archivo ejecutable, la versión de destino del archivo ejecutable es el modo de compatibilidad en el que se ejecutan todos los ensamblados de ese dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b29e-123">For example, in the case of an executable, the version that the executable targets is the compatibility mode all assemblies in that application domain run under.</span></span>

<span data-ttu-id="4b29e-124">Para ver una lista de los cambios en tiempo de ejecución que se aplican al entorno, seleccione la versión de .NET Framework que tenga actualmente como destino y, después, la versión a la que quiera migrar:</span><span class="sxs-lookup"><span data-stu-id="4b29e-124">To see a list of runtime changes that apply to your environment, select the .NET Framework version you're currently targeting and then the version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](../../../includes/migration-guide/runtime/versionselector.md)]

## <a name="retargeting-changes"></a><span data-ttu-id="4b29e-125">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="4b29e-125">Retargeting changes</span></span>

<span data-ttu-id="4b29e-126">Los cambios de redestinación son los que surgen cuando se vuelve a compilar un ensamblado para destinarlo a una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="4b29e-126">Retargeting changes are those that arise when an assembly is recompiled to target a newer version.</span></span> <span data-ttu-id="4b29e-127">Destinarlo a una versión más reciente significa que el ensamblado participa en las características nuevas así como en los problemas de compatibilidad potenciales de las características antiguas.</span><span class="sxs-lookup"><span data-stu-id="4b29e-127">Targeting a newer version means the assembly opts into the new features as well as potential compatibility issues for old features.</span></span>

<span data-ttu-id="4b29e-128">Para ver una lista de los cambios de redestinación que se aplican al entorno, seleccione la versión de .NET Framework que tenga actualmente como destino y, después, la versión a la que quiera migrar:</span><span class="sxs-lookup"><span data-stu-id="4b29e-128">To see a list of retargeting changes that apply to your environment, select the .NET Framework version you're currently targeting and then the version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](../../../includes/migration-guide/retargeting/versionselector.md)]

## <a name="impact-classification"></a><span data-ttu-id="4b29e-129">Clasificación de impacto</span><span class="sxs-lookup"><span data-stu-id="4b29e-129">Impact classification</span></span>

<span data-ttu-id="4b29e-130">En los temas en los que se describen los cambios en tiempo de ejecución y de redestinación, por ejemplo [Cambios de redestinación para migrar de 4.7.2 a 4.8](retargeting/4.7.2-4.8.md), los elementos individuales se clasifican por su impacto esperado, como sigue:</span><span class="sxs-lookup"><span data-stu-id="4b29e-130">In the topics that describe runtime and retargeting changes, for example, [Retargeting changes for migrating from 4.7.2 to 4.8](retargeting/4.7.2-4.8.md), individual items are classified by their expected impact as follows:</span></span>

<span data-ttu-id="4b29e-131">**Major**</span><span class="sxs-lookup"><span data-stu-id="4b29e-131">**Major**</span></span>\
<span data-ttu-id="4b29e-132">Cambio significativo que afecta a un gran número de aplicaciones o que requiere una modificación sustancial del código.</span><span class="sxs-lookup"><span data-stu-id="4b29e-132">A significant change that affects a large number of apps or that requires substantial modification of code.</span></span>

<span data-ttu-id="4b29e-133">**Minor**</span><span class="sxs-lookup"><span data-stu-id="4b29e-133">**Minor**</span></span>\
<span data-ttu-id="4b29e-134">Un cambio que afecta a un pequeño número de aplicaciones o que requiere una leve modificación del código.</span><span class="sxs-lookup"><span data-stu-id="4b29e-134">A change that affects a small number of apps or that requires minor modification of code.</span></span>

<span data-ttu-id="4b29e-135">**Caso avanzado**</span><span class="sxs-lookup"><span data-stu-id="4b29e-135">**Edge case**</span></span>\
<span data-ttu-id="4b29e-136">Cambio que afecta a aplicaciones de escenarios muy concretos que no son frecuentes.</span><span class="sxs-lookup"><span data-stu-id="4b29e-136">A change that affects apps under very specific scenarios that are not common.</span></span>

<span data-ttu-id="4b29e-137">**Transparente**</span><span class="sxs-lookup"><span data-stu-id="4b29e-137">**Transparent**</span></span>\
<span data-ttu-id="4b29e-138">Cambio que no tiene ningún efecto apreciable en el programador o el usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b29e-138">A change that has no noticeable effect on the app's developer or user.</span></span> <span data-ttu-id="4b29e-139">No es necesario modificar la aplicación debido a este cambio.</span><span class="sxs-lookup"><span data-stu-id="4b29e-139">The app should not require modification because of this change.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b29e-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4b29e-140">See also</span></span>

- [<span data-ttu-id="4b29e-141">Versiones y dependencias</span><span class="sxs-lookup"><span data-stu-id="4b29e-141">Versions and dependencies</span></span>](versions-and-dependencies.md)
- [<span data-ttu-id="4b29e-142">Novedades</span><span class="sxs-lookup"><span data-stu-id="4b29e-142">What's new</span></span>](../whats-new/index.md)
- [<span data-ttu-id="4b29e-143">Lo obsoleto</span><span class="sxs-lookup"><span data-stu-id="4b29e-143">What's obsolete</span></span>](../whats-new/whats-obsolete.md)
