---
title: 'Cambio importante: HTTP: los tipos BadHttpRequestException de Kestrel e IIS se han marcado como obsoletos y se han reemplazado'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado HTTP: los tipos BadHttpRequestException de Kestrel e IIS se han marcado como obsoletos y se han reemplazado'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c51b1dd9d708c04bc1bbcfb65ea2e9daea5330b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760160"
---
# <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a><span data-ttu-id="ea662-103">HTTP: los tipos BadHttpRequestException de Kestrel e IIS se han marcado como obsoletos y se han reemplazado</span><span class="sxs-lookup"><span data-stu-id="ea662-103">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>

<span data-ttu-id="ea662-104">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` y `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` se han marcado como obsoletos y se han cambiado para que deriven de `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span><span class="sxs-lookup"><span data-stu-id="ea662-104">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` have been marked obsolete and changed to derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span> <span data-ttu-id="ea662-105">Los servidores de Kestrel e IIS siguen produciendo los tipos de excepción antiguos para garantizar la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="ea662-105">The Kestrel and IIS servers still throw their old exception types for backwards compatibility.</span></span> <span data-ttu-id="ea662-106">Los tipos obsoletos se quitarán en una versión futura.</span><span class="sxs-lookup"><span data-stu-id="ea662-106">The obsolete types will be removed in a future release.</span></span>

<span data-ttu-id="ea662-107">Para obtener información, vea [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).</span><span class="sxs-lookup"><span data-stu-id="ea662-107">For discussion, see [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ea662-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ea662-108">Version introduced</span></span>

<span data-ttu-id="ea662-109">5.0 (versión preliminar 4)</span><span class="sxs-lookup"><span data-stu-id="ea662-109">5.0 Preview 4</span></span>

## <a name="old-behavior"></a><span data-ttu-id="ea662-110">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="ea662-110">Old behavior</span></span>

<span data-ttu-id="ea662-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` y `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derivaban de <xref:System.IO.IOException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ea662-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derived from <xref:System.IO.IOException?displayProperty=nameWithType>.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="ea662-112">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="ea662-112">New behavior</span></span>

<span data-ttu-id="ea662-113">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` y `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` están obsoletos.</span><span class="sxs-lookup"><span data-stu-id="ea662-113">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` are obsolete.</span></span> <span data-ttu-id="ea662-114">Los tipos también derivan de `Microsoft.AspNetCore.Http.BadHttpRequestException`, que deriva de `System.IO.IOException`.</span><span class="sxs-lookup"><span data-stu-id="ea662-114">The types also derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`, which derives from `System.IO.IOException`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ea662-115">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="ea662-115">Reason for change</span></span>

<span data-ttu-id="ea662-116">El cambio se ha realizado para:</span><span class="sxs-lookup"><span data-stu-id="ea662-116">The change was made to:</span></span>

* <span data-ttu-id="ea662-117">Consolidar los tipos duplicados.</span><span class="sxs-lookup"><span data-stu-id="ea662-117">Consolidate duplicate types.</span></span>
* <span data-ttu-id="ea662-118">Unificar el comportamiento en las implementaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="ea662-118">Unify behavior across server implementations.</span></span>

<span data-ttu-id="ea662-119">Ahora, una aplicación puede detectar la excepción base `Microsoft.AspNetCore.Http.BadHttpRequestException` cuando se usa Kestrel o IIS.</span><span class="sxs-lookup"><span data-stu-id="ea662-119">An app can now catch the base exception `Microsoft.AspNetCore.Http.BadHttpRequestException` when using either Kestrel or IIS.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ea662-120">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="ea662-120">Recommended action</span></span>

<span data-ttu-id="ea662-121">Reemplace los usos de `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` y `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` por `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span><span class="sxs-lookup"><span data-stu-id="ea662-121">Replace usages of `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` with `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ea662-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ea662-122">Affected APIs</span></span>

- [<span data-ttu-id="ea662-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="ea662-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [<span data-ttu-id="ea662-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="ea662-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
