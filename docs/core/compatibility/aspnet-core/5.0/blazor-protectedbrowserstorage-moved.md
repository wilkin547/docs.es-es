---
title: 'Cambio importante: Blazor: Migración de la característica ProtectedBrowserStorage a una plataforma compartida'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Blazor: Migración de la característica ProtectedBrowserStorage a una plataforma compartida'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c8058adf8b66aef8dd011ea672cd306ae4de60a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760163"
---
# <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a><span data-ttu-id="5d0ed-103">Blazor: Migración de la característica ProtectedBrowserStorage a una plataforma compartida</span><span class="sxs-lookup"><span data-stu-id="5d0ed-103">Blazor: ProtectedBrowserStorage feature moved to shared framework</span></span>

<span data-ttu-id="5d0ed-104">Como parte de la versión ASP.NET Core 5.0 RC2, la característica `ProtectedBrowserStorage` ha migrado a la plataforma compartida de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="5d0ed-104">As part of the ASP.NET Core 5.0 RC2 release, the `ProtectedBrowserStorage` feature moved to the ASP.NET Core shared framework.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5d0ed-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="5d0ed-105">Version introduced</span></span>

<span data-ttu-id="5d0ed-106">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="5d0ed-106">5.0 RC2</span></span>

## <a name="old-behavior"></a><span data-ttu-id="5d0ed-107">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="5d0ed-107">Old behavior</span></span>

<span data-ttu-id="5d0ed-108">En la versión preliminar 8 de ASP.NET Core 5.0, la característica está disponible como parte del paquete [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions), pero solo se puede usar en Blazor WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="5d0ed-108">In ASP.NET Core 5.0 Preview 8, the feature is available as a part of the [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) package but was only usable in Blazor WebAssembly.</span></span>

<span data-ttu-id="5d0ed-109">En ASP.NET Core 5.0 RC1, la característica está disponible como parte del paquete [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage), que hace referencia a la plataforma compartida de `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="5d0ed-109">In ASP.NET Core 5.0 RC1, the feature is available as part of the [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) package, which references the `Microsoft.AspNetCore.App` shared framework.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="5d0ed-110">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="5d0ed-110">New behavior</span></span>

<span data-ttu-id="5d0ed-111">En ASP.NET Core 5.0 RC2, ya no se necesita una referencia de paquete NuGet para hacer referencia a la característica y usarla.</span><span class="sxs-lookup"><span data-stu-id="5d0ed-111">In ASP.NET Core 5.0 RC2, a NuGet package reference is no longer needed to reference and use the feature.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="5d0ed-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="5d0ed-112">Reason for change</span></span>

<span data-ttu-id="5d0ed-113">La migración a la plataforma compartida es más adecuada para la experiencia de usuario que esperan los clientes.</span><span class="sxs-lookup"><span data-stu-id="5d0ed-113">The move to the shared framework is a better fit for the user experience customers expect.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5d0ed-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="5d0ed-114">Recommended action</span></span>

<span data-ttu-id="5d0ed-115">Si va a realizar la actualización desde ASP.NET Core 5.0 RC1, complete estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5d0ed-115">If upgrading from ASP.NET Core 5.0 RC1, complete the following steps:</span></span>

1. <span data-ttu-id="5d0ed-116">Quite la referencia al paquete `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="5d0ed-116">Remove the `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` package reference from the project.</span></span>
1. <span data-ttu-id="5d0ed-117">Reemplace `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` por `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span><span class="sxs-lookup"><span data-stu-id="5d0ed-117">Replace `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="5d0ed-118">Quite la llamada a `AddProtectedBrowserStorage` de la clase `Startup`.</span><span class="sxs-lookup"><span data-stu-id="5d0ed-118">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

<span data-ttu-id="5d0ed-119">Si va a actualizar desde la versión preliminar 8 de ASP.NET Core 5.0, complete estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5d0ed-119">If upgrading from ASP.NET Core 5.0 Preview 8, complete the following steps:</span></span>

1. <span data-ttu-id="5d0ed-120">Quite la referencia al paquete `Microsoft.AspNetCore.Components.Web.Extensions` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="5d0ed-120">Remove the `Microsoft.AspNetCore.Components.Web.Extensions` package reference from the project.</span></span>
1. <span data-ttu-id="5d0ed-121">Reemplace `using Microsoft.AspNetCore.Components.Web.Extensions;` por `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span><span class="sxs-lookup"><span data-stu-id="5d0ed-121">Replace `using Microsoft.AspNetCore.Components.Web.Extensions;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="5d0ed-122">Quite la llamada a `AddProtectedBrowserStorage` de la clase `Startup`.</span><span class="sxs-lookup"><span data-stu-id="5d0ed-122">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5d0ed-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5d0ed-123">Affected APIs</span></span>

<span data-ttu-id="5d0ed-124">None</span><span class="sxs-lookup"><span data-stu-id="5d0ed-124">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
