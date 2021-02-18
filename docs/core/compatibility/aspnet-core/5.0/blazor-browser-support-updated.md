---
title: 'Cambio importante: Blazor: compatibilidad con exploradores actualizada'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Blazor: compatibilidad con exploradores actualizada'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
no-loc:
- Blazor
- Blazor WebAssembly
- Blazor Server
ms.openlocfilehash: a14ab8d1afd4b662f61e30136d23e28ffbe2d496
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100431482"
---
# <a name="blazor-updated-browser-support"></a><span data-ttu-id="cb46d-103">Blazor; compatibilidad con exploradores actualizada</span><span class="sxs-lookup"><span data-stu-id="cb46d-103">Blazor: Updated browser support</span></span>

<span data-ttu-id="cb46d-104">En ASP.NET Core 5.0 se presentan [nuevas características de Blazor](https://github.com/dotnet/aspnetcore/issues/21514), y algunas son incompatibles con los exploradores más antiguos.</span><span class="sxs-lookup"><span data-stu-id="cb46d-104">ASP.NET Core 5.0 introduces [new Blazor features](https://github.com/dotnet/aspnetcore/issues/21514), some of which are incompatible with older browsers.</span></span> <span data-ttu-id="cb46d-105">La lista de exploradores admitidos por Blazor en ASP.NET Core 5.0 se ha actualizado en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="cb46d-105">The list of browsers supported by Blazor in ASP.NET Core 5.0 has been updated accordingly.</span></span>

<span data-ttu-id="cb46d-106">Para obtener información, vea la incidencia de GitHub [n.º 26475 (dotnet/aspnetcore)](https://github.com/dotnet/aspnetcore/issues/26475).</span><span class="sxs-lookup"><span data-stu-id="cb46d-106">For discussion, see GitHub issue [dotnet/aspnetcore#26475](https://github.com/dotnet/aspnetcore/issues/26475).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="cb46d-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="cb46d-107">Version introduced</span></span>

<span data-ttu-id="cb46d-108">5.0</span><span class="sxs-lookup"><span data-stu-id="cb46d-108">5.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="cb46d-109">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="cb46d-109">Old behavior</span></span>

<span data-ttu-id="cb46d-110">Blazor Server es compatible con Microsoft Internet Explorer 11 con elementos polyfill suficientes.</span><span class="sxs-lookup"><span data-stu-id="cb46d-110">Blazor Server supports Microsoft Internet Explorer 11 with sufficient polyfills.</span></span> <span data-ttu-id="cb46d-111">Blazor Server y Blazor WebAssembly también funcionan en [Microsoft Edge (versión anterior)](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy).</span><span class="sxs-lookup"><span data-stu-id="cb46d-111">Blazor Server and Blazor WebAssembly are also functional in [Microsoft Edge Legacy](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy).</span></span>

## <a name="new-behavior"></a><span data-ttu-id="cb46d-112">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="cb46d-112">New behavior</span></span>

<span data-ttu-id="cb46d-113">Blazor Server en ASP.NET Core 5.0 no es compatible con Microsoft Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="cb46d-113">Blazor Server in ASP.NET Core 5.0 isn't supported with Microsoft Internet Explorer 11.</span></span> <span data-ttu-id="cb46d-114">Blazor Server y Blazor WebAssembly no funcionan de forma completa en Microsoft Edge (versión anterior).</span><span class="sxs-lookup"><span data-stu-id="cb46d-114">Blazor Server and Blazor WebAssembly aren't fully functional in Microsoft Edge Legacy.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="cb46d-115">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="cb46d-115">Reason for change</span></span>

<span data-ttu-id="cb46d-116">Las nuevas características de Blazor en ASP.NET Core 5.0 no son compatibles con estos exploradores más antiguos, cuyo uso está disminuyendo.</span><span class="sxs-lookup"><span data-stu-id="cb46d-116">New Blazor features in ASP.NET Core 5.0 are incompatible with these older browsers, and use of these older browsers is diminishing.</span></span> <span data-ttu-id="cb46d-117">Para obtener más información, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="cb46d-117">For more information, see the following resources:</span></span>

* [<span data-ttu-id="cb46d-118">La compatibilidad de Windows con Microsoft Edge (versión anterior) también finaliza el 9 de marzo de 2021</span><span class="sxs-lookup"><span data-stu-id="cb46d-118">Windows support for Microsoft Edge Legacy is also ending on March 9, 2021</span></span>](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy)
* [<span data-ttu-id="cb46d-119">Las aplicaciones y servicios de Microsoft 365 finalizarán la compatibilidad con Microsoft Internet Explorer 11 el 17 de agosto de 2021</span><span class="sxs-lookup"><span data-stu-id="cb46d-119">Microsoft 365 apps and services will end support for Microsoft Internet Explorer 11 by August 17, 2021</span></span>](/lifecycle/announcements/m365-ie11-microsoft-edge-legacy)

## <a name="recommended-action"></a><span data-ttu-id="cb46d-120">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="cb46d-120">Recommended action</span></span>

<span data-ttu-id="cb46d-121">Actualice estos exploradores antiguos al [nuevo Microsoft Edge basado en Chromium](https://www.microsoft.com/edge).</span><span class="sxs-lookup"><span data-stu-id="cb46d-121">Upgrade from these older browsers to the [new, Chromium-based Microsoft Edge](https://www.microsoft.com/edge).</span></span> <span data-ttu-id="cb46d-122">En el caso de las aplicaciones de Blazor que necesiten admitir estos exploradores antiguos, use ASP.NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="cb46d-122">For Blazor apps that need to support these older browsers, use ASP.NET Core 3.1.</span></span> <span data-ttu-id="cb46d-123">La lista de exploradores admitidos para Blazor en ASP.NET Core 3.1 no ha cambiado y está documentada en [Plataformas admitidas](/aspnet/core/blazor/supported-platforms?view=aspnetcore-3.1).</span><span class="sxs-lookup"><span data-stu-id="cb46d-123">The supported browsers list for Blazor in ASP.NET Core 3.1 hasn't changed and is documented at [Supported platforms](/aspnet/core/blazor/supported-platforms?view=aspnetcore-3.1).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="cb46d-124">API afectadas</span><span class="sxs-lookup"><span data-stu-id="cb46d-124">Affected APIs</span></span>

<span data-ttu-id="cb46d-125">None</span><span class="sxs-lookup"><span data-stu-id="cb46d-125">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
