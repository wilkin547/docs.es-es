---
title: 'Cambio importante: Extensiones: cambios en las referencias de paquetes que afectan a algunos paquetes NuGet'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Extensiones: cambios en las referencias de paquetes que afectan a algunos paquetes NuGet'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 4a525d9f7aad4409fd507fcf80c00968ff4b63d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760161"
---
# <a name="extensions-package-reference-changes-affecting-some-nuget-packages"></a><span data-ttu-id="5a7ca-103">Extensiones: cambios en las referencias de paquetes que afectan a algunos paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="5a7ca-103">Extensions: Package reference changes affecting some NuGet packages</span></span>

<span data-ttu-id="5a7ca-104">Con la migración de algunos paquetes NuGet de `Microsoft.Extensions.*` del repositorio [dotnet/extensions](https://github.com/dotnet/extensions) a [dotnet/runtime](https://github.com/dotnet/runtime), como se describe en [aspnet/Announcements#411](https://github.com/aspnet/Announcements/issues/411), se están aplicando cambios en el empaquetado a algunos de los paquetes migrados.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-104">With the migration of some `Microsoft.Extensions.*` NuGet packages from the [dotnet/extensions](https://github.com/dotnet/extensions) repository to [dotnet/runtime](https://github.com/dotnet/runtime), as described in [aspnet/Announcements#411](https://github.com/aspnet/Announcements/issues/411), packaging changes are being applied to some of the migrated packages.</span></span> <span data-ttu-id="5a7ca-105">Para obtener información sobre esta incidencia, vea [dotnet/aspnetcore#21033](https://github.com/dotnet/aspnetcore/issues/21033).</span><span class="sxs-lookup"><span data-stu-id="5a7ca-105">For discussion on this issue, see [dotnet/aspnetcore#21033](https://github.com/dotnet/aspnetcore/issues/21033).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5a7ca-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="5a7ca-106">Version introduced</span></span>

<span data-ttu-id="5a7ca-107">5.0 (versión preliminar 4)</span><span class="sxs-lookup"><span data-stu-id="5a7ca-107">5.0 Preview 4</span></span>

## <a name="old-behavior"></a><span data-ttu-id="5a7ca-108">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="5a7ca-108">Old behavior</span></span>

<span data-ttu-id="5a7ca-109">Algunos paquetes de `Microsoft.Extensions.*` incluían referencias de paquete para las API en las que se basaba la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-109">Some `Microsoft.Extensions.*` packages included package references for APIs on which your app relied.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="5a7ca-110">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="5a7ca-110">New behavior</span></span>

<span data-ttu-id="5a7ca-111">Es posible que la aplicación tenga que agregar dependencias de paquete de `Microsoft.Extensions.*`.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-111">Your app may have to add `Microsoft.Extensions.*` package dependencies.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="5a7ca-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="5a7ca-112">Reason for change</span></span>

<span data-ttu-id="5a7ca-113">Las directivas de empaquetado se actualizaron para alinearse mejor con el repositorio *dotnet/runtime*.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-113">Packaging policies were updated to better align with the *dotnet/runtime* repository.</span></span> <span data-ttu-id="5a7ca-114">Según la nueva directiva, las referencias de paquete sin usar se quitan de los archivos *.nupkg* durante el empaquetado.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-114">Under the new policy, unused package references are removed from *.nupkg* files during packaging.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5a7ca-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="5a7ca-115">Recommended action</span></span>

<span data-ttu-id="5a7ca-116">Los consumidores de los paquetes afectados deben agregar en su proyecto una dependencia directa en la dependencia de paquete quitado si se usan las API de la dependencia de paquete quitada.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-116">Consumers of the affected packages should add a direct dependency on the removed package dependency in their project if APIs from removed package dependency are used.</span></span> <span data-ttu-id="5a7ca-117">En la tabla siguiente se enumeran los paquetes afectados y los cambios correspondientes.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-117">The following table lists the affected packages and the corresponding changes.</span></span>

|<span data-ttu-id="5a7ca-118">Nombre del paquete</span><span class="sxs-lookup"><span data-stu-id="5a7ca-118">Package name</span></span>|<span data-ttu-id="5a7ca-119">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="5a7ca-119">Change description</span></span>|
|------------|------------------|
|[<span data-ttu-id="5a7ca-120">Microsoft.Extensions.Configuration.Binder</span><span class="sxs-lookup"><span data-stu-id="5a7ca-120">Microsoft.Extensions.Configuration.Binder</span></span>](https://nuget.org/packages/Microsoft.Extensions.Configuration.Binder)|<span data-ttu-id="5a7ca-121">Se ha quitado la referencia a `Microsoft.Extensions.Configuration`.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-121">Removed reference to `Microsoft.Extensions.Configuration`</span></span>|
|[<span data-ttu-id="5a7ca-122">Microsoft.Extensions.Configuration.Json</span><span class="sxs-lookup"><span data-stu-id="5a7ca-122">Microsoft.Extensions.Configuration.Json</span></span>](https://nuget.org/packages/Microsoft.Extensions.Configuration.Json)    |<span data-ttu-id="5a7ca-123">Se ha quitado la referencia a `System.Threading.Tasks.Extensions`.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-123">Removed reference to `System.Threading.Tasks.Extensions`</span></span>|
|[<span data-ttu-id="5a7ca-124">Microsoft.Extensions.Hosting.Abstractions</span><span class="sxs-lookup"><span data-stu-id="5a7ca-124">Microsoft.Extensions.Hosting.Abstractions</span></span>](https://nuget.org/packages/Microsoft.Extensions.Hosting.Abstractions)|<span data-ttu-id="5a7ca-125">Se ha quitado la referencia a `Microsoft.Extensions.Logging.Abstractions`.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-125">Removed reference to `Microsoft.Extensions.Logging.Abstractions`</span></span>|
|[<span data-ttu-id="5a7ca-126">Microsoft.Extensions.Logging</span><span class="sxs-lookup"><span data-stu-id="5a7ca-126">Microsoft.Extensions.Logging</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging)                          |<span data-ttu-id="5a7ca-127">Se ha quitado la referencia a `Microsoft.Extensions.Configuration.Binder`.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-127">Removed reference to `Microsoft.Extensions.Configuration.Binder`</span></span>|
|[<span data-ttu-id="5a7ca-128">Microsoft.Extensions.Logging.Console</span><span class="sxs-lookup"><span data-stu-id="5a7ca-128">Microsoft.Extensions.Logging.Console</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.Console)          |<span data-ttu-id="5a7ca-129">Se ha quitado la referencia a `Microsoft.Extensions.Configuration.Abstractions`.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-129">Removed reference to `Microsoft.Extensions.Configuration.Abstractions`</span></span>|
|[<span data-ttu-id="5a7ca-130">Microsoft.Extensions.Logging.EventLog</span><span class="sxs-lookup"><span data-stu-id="5a7ca-130">Microsoft.Extensions.Logging.EventLog</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.EventLog)        |<span data-ttu-id="5a7ca-131">Se ha quitado la referencia a `System.Diagnostics.EventLog` para el moniker de la plataforma de destino de .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-131">Removed reference to `System.Diagnostics.EventLog` for the .NET Framework 4.6.1 target framework moniker</span></span>|
|[<span data-ttu-id="5a7ca-132">Microsoft.Extensions.Logging.EventSource</span><span class="sxs-lookup"><span data-stu-id="5a7ca-132">Microsoft.Extensions.Logging.EventSource</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.EventSource)  |<span data-ttu-id="5a7ca-133">Se ha quitado la referencia a `System.Threading.Tasks.Extensions`.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-133">Removed reference to `System.Threading.Tasks.Extensions`</span></span>|
|[<span data-ttu-id="5a7ca-134">Microsoft.Extensions.Options</span><span class="sxs-lookup"><span data-stu-id="5a7ca-134">Microsoft.Extensions.Options</span></span>](https://nuget.org/packages/Microsoft.Extensions.Options)                          |<span data-ttu-id="5a7ca-135">Se ha quitado la referencia a `System.ComponentModel.Annotations`.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-135">Removed reference to `System.ComponentModel.Annotations`</span></span>|

<span data-ttu-id="5a7ca-136">Por ejemplo, la referencia de paquete a `Microsoft.Extensions.Configuration` se ha quitado de `Microsoft.Extensions.Configuration.Binder`.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-136">For example, the package reference to `Microsoft.Extensions.Configuration` was removed from `Microsoft.Extensions.Configuration.Binder`.</span></span> <span data-ttu-id="5a7ca-137">No se ha usado en el paquete ninguna API de la dependencia.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-137">No API from the dependency was used in the package.</span></span> <span data-ttu-id="5a7ca-138">Los usuarios de `Microsoft.Extensions.Configuration.Binder` que dependen de las API de `Microsoft.Extensions.Configuration` deben agregar una referencia directa a ella en su proyecto.</span><span class="sxs-lookup"><span data-stu-id="5a7ca-138">Users of `Microsoft.Extensions.Configuration.Binder` who depend on APIs from `Microsoft.Extensions.Configuration` should add a direct reference to it in their project.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5a7ca-139">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5a7ca-139">Affected APIs</span></span>

<span data-ttu-id="5a7ca-140">None</span><span class="sxs-lookup"><span data-stu-id="5a7ca-140">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
