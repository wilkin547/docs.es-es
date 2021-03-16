---
title: 'Cambio importante: Atributos de OSPlatform que se han cambiado de nombre o se han quitado'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde los atributos de la plataforma del sistema operativo que se introdujeron en una versión preliminar se han quitado o se les ha cambiado el nombre.
ms.date: 11/01/2020
ms.openlocfilehash: 118c5360eb02c1b4d57fccbd3b2cfdeff0b9fe12
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257263"
---
# <a name="osplatform-attributes-renamed-or-removed"></a><span data-ttu-id="8c042-103">Atributos de OSPlatform que se han cambiado de nombre o se han quitado</span><span class="sxs-lookup"><span data-stu-id="8c042-103">OSPlatform attributes renamed or removed</span></span>

<span data-ttu-id="8c042-104">Los atributos siguientes que se presentaron en .NET 5 Preview 8 se han quitado o se les ha cambiado el nombre: `MinimumOSPlatformAttribute`, `RemovedInOSPlatformAttribute` y `ObsoletedInOSPlatformAttribute`.</span><span class="sxs-lookup"><span data-stu-id="8c042-104">The following attributes that were introduced in .NET 5 Preview 8 have been removed or renamed: `MinimumOSPlatformAttribute`, `RemovedInOSPlatformAttribute`, and `ObsoletedInOSPlatformAttribute`.</span></span>

## <a name="change-description"></a><span data-ttu-id="8c042-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="8c042-105">Change description</span></span>

<span data-ttu-id="8c042-106">En .NET 5 Preview 8 se han presentado los siguientes atributos en el espacio de nombres <xref:System.Runtime.Versioning>:</span><span class="sxs-lookup"><span data-stu-id="8c042-106">.NET 5 Preview 8 introduced the following attributes in the <xref:System.Runtime.Versioning> namespace:</span></span>

- `MinimumOSPlatformAttribute`
- `RemovedInOSPlatformAttribute`
- `ObsoletedInOSPlatformAttribute`

<span data-ttu-id="8c042-107">En .NET 5 Preview 8, cuando un proyecto tiene como destino un tipo específico del sistema operativo de .NET 5 mediante un [moniker de la plataforma de destino](../../../../standard/frameworks.md) como `net5.0-windows`, la compilación agrega un atributo `System.Runtime.Versioning.MinimumOSPlatformAttribute` de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8c042-107">In .NET 5 Preview 8, when a project targets an OS-specific flavor of .NET 5 by using a [target framework moniker](../../../../standard/frameworks.md) such as `net5.0-windows`, the build adds an assembly-level `System.Runtime.Versioning.MinimumOSPlatformAttribute` attribute.</span></span>

<span data-ttu-id="8c042-108">En .NET 5 RC1, se ha quitado `ObsoletedInOSPlatformAttribute`, y se ha cambiado el nombre de `MinimumOSPlatformAttribute` y `RemovedInOSPlatformAttribute` de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8c042-108">In .NET 5 RC1, the `ObsoletedInOSPlatformAttribute` has been removed, and `MinimumOSPlatformAttribute` and `RemovedInOSPlatformAttribute` have been renamed as follows:</span></span>

| <span data-ttu-id="8c042-109">Nombre en Preview 8</span><span class="sxs-lookup"><span data-stu-id="8c042-109">Preview 8 name</span></span> | <span data-ttu-id="8c042-110">Nombre en RC1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="8c042-110">RC1 and later name</span></span> |
| - | - |
| `MinimumOSPlatformAttribute` | <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> |
| `RemovedInOSPlatformAttribute` | <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> |

<span data-ttu-id="8c042-111">En .NET 5 RC1 y versiones posteriores, cuando un proyecto tiene como destino un tipo específico del sistema operativo de .NET 5 mediante un [moniker de la plataforma de destino](../../../../standard/frameworks.md) como `net5.0-windows`, la compilación agrega un atributo <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8c042-111">In .NET 5 RC1 and later, when a project targets an OS-specific flavor of .NET 5 by using a [target framework moniker](../../../../standard/frameworks.md) such as `net5.0-windows`, the build adds an assembly-level <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> attribute.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="8c042-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="8c042-112">Reason for change</span></span>

<span data-ttu-id="8c042-113">En .NET 5 Preview 8 se han presentado atributos en <xref:System.Runtime.Versioning> para especificar las plataformas admitidas para las API.</span><span class="sxs-lookup"><span data-stu-id="8c042-113">.NET 5 Preview 8 introduced attributes in <xref:System.Runtime.Versioning> to specify supported platforms for APIs.</span></span> <span data-ttu-id="8c042-114">El [analizador de compatibilidad de la plataforma](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) consume los atributos para generar advertencias de compilación cuando se consumen API específicas de la plataforma en plataformas que no admiten esas API.</span><span class="sxs-lookup"><span data-stu-id="8c042-114">The attributes are consumed by the [Platform compatibility analyzer](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) to produce build warnings when platform-specific APIs are consumed on platforms that don't support those APIs.</span></span>

<span data-ttu-id="8c042-115">Para .NET 5 RC1, se ha agregado una característica adicional al analizador de compatibilidad de la plataforma para la exclusión de plataformas.</span><span class="sxs-lookup"><span data-stu-id="8c042-115">For .NET 5 RC1, an additional feature was added to the platform compatibility analyzer for platform exclusion.</span></span> <span data-ttu-id="8c042-116">La característica permite que las API se marquen como totalmente no compatibles en plataformas de sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8c042-116">The feature allows APIs to be marked as entirely unsupported on OS platforms.</span></span> <span data-ttu-id="8c042-117">Esta característica ha solicitado cambios en los atributos, incluido el uso de nombres más adecuados.</span><span class="sxs-lookup"><span data-stu-id="8c042-117">That feature prompted changes to the attributes, including using more suitable names.</span></span> <span data-ttu-id="8c042-118">Se ha quitado `ObsoletedInOSPlatformAttribute` porque ya no era necesario.</span><span class="sxs-lookup"><span data-stu-id="8c042-118">The `ObsoletedInOSPlatformAttribute` was removed because it was no longer needed.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="8c042-119">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="8c042-119">Version introduced</span></span>

<span data-ttu-id="8c042-120">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="8c042-120">5.0 RC1</span></span>

## <a name="recommended-action"></a><span data-ttu-id="8c042-121">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="8c042-121">Recommended action</span></span>

<span data-ttu-id="8c042-122">Al redestinar el proyecto de .NET 5 Preview 8 a .NET 5 RC1, se pueden producir errores en tiempo de compilación o ejecución debido a estos cambios.</span><span class="sxs-lookup"><span data-stu-id="8c042-122">When you retarget your project from .NET 5 Preview 8 to .NET 5 RC1, you might encounter build or run-time errors due to these changes.</span></span> <span data-ttu-id="8c042-123">Por ejemplo, es probable que el cambio de nombre de `MinimumOSPlatformAttribute` produzca errores, porque el atributo se aplica a ensamblados específicos de la plataforma en tiempo de compilación y los artefactos de compilación antiguos seguirán haciendo referencia al antiguo nombre de API.</span><span class="sxs-lookup"><span data-stu-id="8c042-123">For example, the renaming of `MinimumOSPlatformAttribute` is likely to produce errors, because the attribute is applied to platform-specific assemblies at build time, and old build artifacts will still reference the old API name.</span></span>

<span data-ttu-id="8c042-124">Ejemplo de errores en tiempo de compilación:</span><span class="sxs-lookup"><span data-stu-id="8c042-124">Example build-time errors:</span></span>

- <span data-ttu-id="8c042-125">**Error CS0246: No se ha encontrado el tipo o el nombre del espacio de nombres "MinimumOSPlatformAttribute" (¿falta una directiva "using" o una referencia de ensamblado?)**</span><span class="sxs-lookup"><span data-stu-id="8c042-125">**error CS0246: The type or namespace name 'MinimumOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>
- <span data-ttu-id="8c042-126">**Error CS0246: No se ha encontrado el tipo o el nombre del espacio de nombres "RemovedInOSPlatformAttribute" (¿falta una directiva "using" o una referencia de ensamblado?)**</span><span class="sxs-lookup"><span data-stu-id="8c042-126">**error CS0246: The type or namespace name 'RemovedInOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>
- <span data-ttu-id="8c042-127">**Error CS0246: No se ha encontrado el tipo o el nombre del espacio de nombres "ObsoletedInOSPlatformAttribute" (¿falta una directiva "using" o una referencia de ensamblado?)**</span><span class="sxs-lookup"><span data-stu-id="8c042-127">**error CS0246: The type or namespace name 'ObsoletedInOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>

<span data-ttu-id="8c042-128">Ejemplo de error en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="8c042-128">Example run-time error:</span></span>

<span data-ttu-id="8c042-129">**Excepción no controlada. System.TypeLoadException: No se pudo cargar el tipo "System.Runtime.Versioning.MinimumOSPlatformAttribute" desde el ensamblado "System.Runtime, Version=5.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a".**</span><span class="sxs-lookup"><span data-stu-id="8c042-129">**Unhandled exception. System.TypeLoadException: Could not load type 'System.Runtime.Versioning.MinimumOSPlatformAttribute' from assembly 'System.Runtime, Version=5.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a'.**</span></span>

<span data-ttu-id="8c042-130">Para resolver estos errores:</span><span class="sxs-lookup"><span data-stu-id="8c042-130">To resolve these errors:</span></span>

- <span data-ttu-id="8c042-131">Actualice todas las referencias de `MinimumOSPlatformAttribute` a <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8c042-131">Update any references of `MinimumOSPlatformAttribute` to <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>.</span></span>
- <span data-ttu-id="8c042-132">Actualice todas las referencias de `RemovedInOSPlatformAttribute` a <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8c042-132">Update any references of `RemovedInOSPlatformAttribute` to <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>.</span></span>
- <span data-ttu-id="8c042-133">Quite todas las referencias a `ObsoletedInOSPlatformAttribute`.</span><span class="sxs-lookup"><span data-stu-id="8c042-133">Remove any references to `ObsoletedInOSPlatformAttribute`.</span></span>
- <span data-ttu-id="8c042-134">Recompile el proyecto (o realice una operación de limpieza y compilación) para eliminar los artefactos de compilación anteriores.</span><span class="sxs-lookup"><span data-stu-id="8c042-134">Rebuild your project (or perform clean + build) to delete old build artifacts.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="8c042-135">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8c042-135">Affected APIs</span></span>

- `System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `System.Runtime.Versioning.RemovedInOSPlatformAttribute`

<!--

### Category

Core .NET libraries

### Affected APIs

- `T:System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `T:System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `T:System.Runtime.Versioning.RemovedInOSPlatformAttribute`

-->
