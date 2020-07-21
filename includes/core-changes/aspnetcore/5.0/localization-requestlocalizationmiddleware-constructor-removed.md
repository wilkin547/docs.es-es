---
ms.openlocfilehash: db941229e02064ee856829417d6762aa17b0b926
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309171"
---
### <a name="localization-obsolete-constructor-removed-in-request-localization-middleware"></a><span data-ttu-id="7ec12-101">Localización: Se ha quitado el constructor obsoleto en el middleware de localización de solicitudes</span><span class="sxs-lookup"><span data-stu-id="7ec12-101">Localization: Obsolete constructor removed in request localization middleware</span></span>

<span data-ttu-id="7ec12-102">El constructor <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> que carece de un parámetro <xref:Microsoft.Extensions.Logging.ILoggerFactory> se ha marcado como obsoleto [en esta confirmación](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0).</span><span class="sxs-lookup"><span data-stu-id="7ec12-102">The <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> constructor that lacks an <xref:Microsoft.Extensions.Logging.ILoggerFactory> parameter was marked as obsolete [in this commit](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0).</span></span> <span data-ttu-id="7ec12-103">En ASP.NET Core 5.0 se ha quitado el constructor obsoleto.</span><span class="sxs-lookup"><span data-stu-id="7ec12-103">In ASP.NET Core 5.0, the obsolete constructor was removed.</span></span> <span data-ttu-id="7ec12-104">Para obtener información, vea [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).</span><span class="sxs-lookup"><span data-stu-id="7ec12-104">For discussion, see [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7ec12-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="7ec12-105">Version introduced</span></span>

<span data-ttu-id="7ec12-106">5.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="7ec12-106">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="7ec12-107">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="7ec12-107">Old behavior</span></span>

<span data-ttu-id="7ec12-108">El constructor obsoleto `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` existe.</span><span class="sxs-lookup"><span data-stu-id="7ec12-108">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor exists.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="7ec12-109">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="7ec12-109">New behavior</span></span>

<span data-ttu-id="7ec12-110">El constructor obsoleto `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` no existe.</span><span class="sxs-lookup"><span data-stu-id="7ec12-110">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor doesn't exist.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7ec12-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="7ec12-111">Reason for change</span></span>

<span data-ttu-id="7ec12-112">Este cambio garantiza que el middleware de localización de solicitudes siempre tenga acceso a un registrador.</span><span class="sxs-lookup"><span data-stu-id="7ec12-112">This change ensures that the request localization middleware always has access to a logger.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7ec12-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="7ec12-113">Recommended action</span></span>

<span data-ttu-id="7ec12-114">Cuando se construye manualmente una instancia de `RequestLocalizationMiddleware`, se pasa una instancia de `ILoggerFactory` en el constructor.</span><span class="sxs-lookup"><span data-stu-id="7ec12-114">When manually constructing an instance of `RequestLocalizationMiddleware`, pass an `ILoggerFactory` instance in the constructor.</span></span> <span data-ttu-id="7ec12-115">Si en ese contexto no hay una instancia de `ILoggerFactory` válida disponible, considere la posibilidad de pasar una instancia de <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> al constructor de middleware.</span><span class="sxs-lookup"><span data-stu-id="7ec12-115">If a valid `ILoggerFactory` instance isn't available in that context, consider passing the middleware constructor a <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> instance.</span></span>

#### <a name="category"></a><span data-ttu-id="7ec12-116">Categoría</span><span class="sxs-lookup"><span data-stu-id="7ec12-116">Category</span></span>

<span data-ttu-id="7ec12-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7ec12-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7ec12-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7ec12-118">Affected APIs</span></span>

[<span data-ttu-id="7ec12-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span><span class="sxs-lookup"><span data-stu-id="7ec12-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span></span>](/dotnet/api/microsoft.aspnetcore.localization.requestlocalizationmiddleware.-ctor?view=aspnetcore-3.1#Microsoft_AspNetCore_Localization_RequestLocalizationMiddleware__ctor_Microsoft_AspNetCore_Http_RequestDelegate_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Builder_RequestLocalizationOptions__)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Builder.RequestLocalizationOptions})`

-->
