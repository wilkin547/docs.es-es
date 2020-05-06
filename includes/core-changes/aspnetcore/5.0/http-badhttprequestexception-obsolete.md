---
ms.openlocfilehash: c4e7864262a11aafa4b7f1f4bdf632fbf084c560
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507106"
---
### <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a><span data-ttu-id="cb8fb-101">HTTP: los tipos BadHttpRequestException de Kestrel e IIS se han marcado como obsoletos y se han reemplazado</span><span class="sxs-lookup"><span data-stu-id="cb8fb-101">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>

<span data-ttu-id="cb8fb-102">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` y `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` se han marcado como obsoletos y se han cambiado para que deriven de `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span><span class="sxs-lookup"><span data-stu-id="cb8fb-102">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` have been marked obsolete and changed to derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span> <span data-ttu-id="cb8fb-103">Los servidores de Kestrel e IIS siguen produciendo los tipos de excepción antiguos para garantizar la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="cb8fb-103">The Kestrel and IIS servers still throw their old exception types for backwards compatibility.</span></span> <span data-ttu-id="cb8fb-104">Los tipos obsoletos se quitarán en una versión futura.</span><span class="sxs-lookup"><span data-stu-id="cb8fb-104">The obsolete types will be removed in a future release.</span></span>

<span data-ttu-id="cb8fb-105">Para obtener información, vea [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).</span><span class="sxs-lookup"><span data-stu-id="cb8fb-105">For discussion, see [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cb8fb-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="cb8fb-106">Version introduced</span></span>

<span data-ttu-id="cb8fb-107">5.0 (versión preliminar 4)</span><span class="sxs-lookup"><span data-stu-id="cb8fb-107">5.0 Preview 4</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="cb8fb-108">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="cb8fb-108">Old behavior</span></span>

<span data-ttu-id="cb8fb-109">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` y `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derivaban de <xref:System.IO.IOException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cb8fb-109">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derived from <xref:System.IO.IOException?displayProperty=nameWithType>.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="cb8fb-110">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="cb8fb-110">New behavior</span></span>

<span data-ttu-id="cb8fb-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` y `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` están obsoletos.</span><span class="sxs-lookup"><span data-stu-id="cb8fb-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` are obsolete.</span></span> <span data-ttu-id="cb8fb-112">Los tipos también derivan de `Microsoft.AspNetCore.Http.BadHttpRequestException`, que deriva de `System.IO.IOException`.</span><span class="sxs-lookup"><span data-stu-id="cb8fb-112">The types also derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`, which derives from `System.IO.IOException`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="cb8fb-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="cb8fb-113">Reason for change</span></span>

<span data-ttu-id="cb8fb-114">El cambio se ha realizado para:</span><span class="sxs-lookup"><span data-stu-id="cb8fb-114">The change was made to:</span></span>

* <span data-ttu-id="cb8fb-115">Consolidar los tipos duplicados.</span><span class="sxs-lookup"><span data-stu-id="cb8fb-115">Consolidate duplicate types.</span></span>
* <span data-ttu-id="cb8fb-116">Unificar el comportamiento en las implementaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="cb8fb-116">Unify behavior across server implementations.</span></span>

<span data-ttu-id="cb8fb-117">Ahora, una aplicación puede detectar la excepción base `Microsoft.AspNetCore.Http.BadHttpRequestException` cuando se usa Kestrel o IIS.</span><span class="sxs-lookup"><span data-stu-id="cb8fb-117">An app can now catch the base exception `Microsoft.AspNetCore.Http.BadHttpRequestException` when using either Kestrel or IIS.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cb8fb-118">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="cb8fb-118">Recommended action</span></span>

<span data-ttu-id="cb8fb-119">Reemplace los usos de `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` y `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` por `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span><span class="sxs-lookup"><span data-stu-id="cb8fb-119">Replace usages of `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` with `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span>

#### <a name="category"></a><span data-ttu-id="cb8fb-120">Categoría</span><span class="sxs-lookup"><span data-stu-id="cb8fb-120">Category</span></span>

<span data-ttu-id="cb8fb-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cb8fb-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cb8fb-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="cb8fb-122">Affected APIs</span></span>

- [<span data-ttu-id="cb8fb-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="cb8fb-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [<span data-ttu-id="cb8fb-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="cb8fb-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
