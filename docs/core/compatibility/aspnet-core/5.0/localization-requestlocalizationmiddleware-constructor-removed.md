---
title: 'Cambio importante: Localización: Se ha quitado el constructor obsoleto en el middleware de localización de solicitudes'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Localización: Se ha quitado el constructor obsoleto en el middleware de localización de solicitudes'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 53dd0f25078dae140d34d6d21d66983f78b8bdb0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760245"
---
# <a name="localization-obsolete-constructor-removed-in-request-localization-middleware"></a><span data-ttu-id="e5f08-103">Localización: Se ha quitado el constructor obsoleto en el middleware de localización de solicitudes</span><span class="sxs-lookup"><span data-stu-id="e5f08-103">Localization: Obsolete constructor removed in request localization middleware</span></span>

<span data-ttu-id="e5f08-104">El constructor <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> que carece de un parámetro <xref:Microsoft.Extensions.Logging.ILoggerFactory> se ha marcado como obsoleto [en esta confirmación](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0).</span><span class="sxs-lookup"><span data-stu-id="e5f08-104">The <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> constructor that lacks an <xref:Microsoft.Extensions.Logging.ILoggerFactory> parameter was marked as obsolete [in this commit](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0).</span></span> <span data-ttu-id="e5f08-105">En ASP.NET Core 5.0 se ha quitado el constructor obsoleto.</span><span class="sxs-lookup"><span data-stu-id="e5f08-105">In ASP.NET Core 5.0, the obsolete constructor was removed.</span></span> <span data-ttu-id="e5f08-106">Para obtener información, vea [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).</span><span class="sxs-lookup"><span data-stu-id="e5f08-106">For discussion, see [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="e5f08-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="e5f08-107">Version introduced</span></span>

<span data-ttu-id="e5f08-108">5.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="e5f08-108">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="e5f08-109">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="e5f08-109">Old behavior</span></span>

<span data-ttu-id="e5f08-110">El constructor obsoleto `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` existe.</span><span class="sxs-lookup"><span data-stu-id="e5f08-110">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor exists.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="e5f08-111">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="e5f08-111">New behavior</span></span>

<span data-ttu-id="e5f08-112">El constructor obsoleto `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` no existe.</span><span class="sxs-lookup"><span data-stu-id="e5f08-112">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor doesn't exist.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="e5f08-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="e5f08-113">Reason for change</span></span>

<span data-ttu-id="e5f08-114">Este cambio garantiza que el middleware de localización de solicitudes siempre tenga acceso a un registrador.</span><span class="sxs-lookup"><span data-stu-id="e5f08-114">This change ensures that the request localization middleware always has access to a logger.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="e5f08-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="e5f08-115">Recommended action</span></span>

<span data-ttu-id="e5f08-116">Cuando se construye manualmente una instancia de `RequestLocalizationMiddleware`, se pasa una instancia de `ILoggerFactory` en el constructor.</span><span class="sxs-lookup"><span data-stu-id="e5f08-116">When manually constructing an instance of `RequestLocalizationMiddleware`, pass an `ILoggerFactory` instance in the constructor.</span></span> <span data-ttu-id="e5f08-117">Si en ese contexto no hay una instancia de `ILoggerFactory` válida disponible, considere la posibilidad de pasar una instancia de <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> al constructor de middleware.</span><span class="sxs-lookup"><span data-stu-id="e5f08-117">If a valid `ILoggerFactory` instance isn't available in that context, consider passing the middleware constructor a <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> instance.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="e5f08-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e5f08-118">Affected APIs</span></span>

[<span data-ttu-id="e5f08-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span><span class="sxs-lookup"><span data-stu-id="e5f08-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span></span>](/dotnet/api/microsoft.aspnetcore.localization.requestlocalizationmiddleware.-ctor?view=aspnetcore-3.1#Microsoft_AspNetCore_Localization_RequestLocalizationMiddleware__ctor_Microsoft_AspNetCore_Http_RequestDelegate_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Builder_RequestLocalizationOptions__)

<!--

### Category

ASP.NET Core

### Affected APIs

`M:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Builder.RequestLocalizationOptions})`

-->
