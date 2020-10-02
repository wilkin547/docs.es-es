---
ms.openlocfilehash: a9545c66d3873b5114fe66e13c77ddc28e20020e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077610"
---
### <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a><span data-ttu-id="5fc79-101">Blazor: Migración de la característica ProtectedBrowserStorage a una plataforma compartida</span><span class="sxs-lookup"><span data-stu-id="5fc79-101">Blazor: ProtectedBrowserStorage feature moved to shared framework</span></span>

<span data-ttu-id="5fc79-102">Como parte de la versión ASP.NET Core 5.0 RC2, la característica `ProtectedBrowserStorage` ha migrado a la plataforma compartida de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="5fc79-102">As part of the ASP.NET Core 5.0 RC2 release, the `ProtectedBrowserStorage` feature moved to the ASP.NET Core shared framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5fc79-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="5fc79-103">Version introduced</span></span>

<span data-ttu-id="5fc79-104">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="5fc79-104">5.0 RC2</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="5fc79-105">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="5fc79-105">Old behavior</span></span>

<span data-ttu-id="5fc79-106">En la versión preliminar 8 de ASP.NET Core 5.0, la característica está disponible como parte del paquete [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions), pero solo se puede usar en Blazor WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="5fc79-106">In ASP.NET Core 5.0 Preview 8, the feature is available as a part of the [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) package but was only usable in Blazor WebAssembly.</span></span>

<span data-ttu-id="5fc79-107">En ASP.NET Core 5.0 RC1, la característica está disponible como parte del paquete [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage), que hace referencia a la plataforma compartida de `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="5fc79-107">In ASP.NET Core 5.0 RC1, the feature is available as part of the [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) package, which references the `Microsoft.AspNetCore.App` shared framework.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="5fc79-108">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="5fc79-108">New behavior</span></span>

<span data-ttu-id="5fc79-109">En ASP.NET Core 5.0 RC2, ya no se necesita una referencia de paquete NuGet para hacer referencia a la característica y usarla.</span><span class="sxs-lookup"><span data-stu-id="5fc79-109">In ASP.NET Core 5.0 RC2, a NuGet package reference is no longer needed to reference and use the feature.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="5fc79-110">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="5fc79-110">Reason for change</span></span>

<span data-ttu-id="5fc79-111">La migración a la plataforma compartida es más adecuada para la experiencia de usuario que esperan los clientes.</span><span class="sxs-lookup"><span data-stu-id="5fc79-111">The move to the shared framework is a better fit for the user experience customers expect.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5fc79-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="5fc79-112">Recommended action</span></span>

<span data-ttu-id="5fc79-113">Si va a realizar la actualización desde ASP.NET Core 5.0 RC1, complete estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5fc79-113">If upgrading from ASP.NET Core 5.0 RC1, complete the following steps:</span></span>

1. <span data-ttu-id="5fc79-114">Quite la referencia al paquete `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="5fc79-114">Remove the `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` package reference from the project.</span></span>
1. <span data-ttu-id="5fc79-115">Reemplace `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` por `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span><span class="sxs-lookup"><span data-stu-id="5fc79-115">Replace `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="5fc79-116">Quite la llamada a `AddProtectedBrowserStorage` de la clase `Startup`.</span><span class="sxs-lookup"><span data-stu-id="5fc79-116">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

<span data-ttu-id="5fc79-117">Si va a actualizar desde la versión preliminar 8 de ASP.NET Core 5.0, complete estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5fc79-117">If upgrading from ASP.NET Core 5.0 Preview 8, complete the following steps:</span></span>

1. <span data-ttu-id="5fc79-118">Quite la referencia al paquete `Microsoft.AspNetCore.Components.Web.Extensions` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="5fc79-118">Remove the `Microsoft.AspNetCore.Components.Web.Extensions` package reference from the project.</span></span>
1. <span data-ttu-id="5fc79-119">Reemplace `using Microsoft.AspNetCore.Components.Web.Extensions;` por `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span><span class="sxs-lookup"><span data-stu-id="5fc79-119">Replace `using Microsoft.AspNetCore.Components.Web.Extensions;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="5fc79-120">Quite la llamada a `AddProtectedBrowserStorage` de la clase `Startup`.</span><span class="sxs-lookup"><span data-stu-id="5fc79-120">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

#### <a name="category"></a><span data-ttu-id="5fc79-121">Categoría</span><span class="sxs-lookup"><span data-stu-id="5fc79-121">Category</span></span>

<span data-ttu-id="5fc79-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5fc79-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5fc79-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5fc79-123">Affected APIs</span></span>

<span data-ttu-id="5fc79-124">None</span><span class="sxs-lookup"><span data-stu-id="5fc79-124">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
