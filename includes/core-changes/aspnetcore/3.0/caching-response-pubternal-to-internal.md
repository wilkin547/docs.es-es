---
ms.openlocfilehash: ae5a5fbf97ed4a03de7d35b9d5d5ca8de3aebc39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394146"
---
### <a name="caching-responsecaching-pubternal-types-changed-to-internal"></a><span data-ttu-id="c58e9-101">Almacenamiento en caché: los tipos de ResponseCaching "pubternal" se han cambiado a internal</span><span class="sxs-lookup"><span data-stu-id="c58e9-101">Caching: ResponseCaching "pubternal" types changed to internal</span></span>

<span data-ttu-id="c58e9-102">En ASP.NET Core 3.0, los tipos "pubternal" de `ResponseCaching` han cambiado a `internal`.</span><span class="sxs-lookup"><span data-stu-id="c58e9-102">In ASP.NET Core 3.0, "pubternal" types in `ResponseCaching` have been changed to `internal`.</span></span>

<span data-ttu-id="c58e9-103">Además, las implementaciones predeterminadas de `IResponseCachingPolicyProvider` y `IResponseCachingKeyProvider` ya no se agregan a los servicios como parte del método `AddResponseCaching`.</span><span class="sxs-lookup"><span data-stu-id="c58e9-103">In addition, default implementations of `IResponseCachingPolicyProvider` and `IResponseCachingKeyProvider` are no longer added to services as part of the `AddResponseCaching` method.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c58e9-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="c58e9-104">Change description</span></span>

<span data-ttu-id="c58e9-105">In ASP.NET Core, los tipos "pubternal" se declaran como `public` pero residen en un espacio de nombres con un sufijo `.Internal`.</span><span class="sxs-lookup"><span data-stu-id="c58e9-105">In ASP.NET Core, "pubternal" types are declared as `public` but reside in a namespace suffixed with `.Internal`.</span></span> <span data-ttu-id="c58e9-106">Aunque estos tipos son públicos, no tienen ninguna directiva compatible y están sujetos a cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="c58e9-106">While these types are public, they have no support policy and are subject to breaking changes.</span></span> <span data-ttu-id="c58e9-107">Desafortunadamente, el uso accidental de estos tipos es habitual, lo que da lugar a cambios importantes en estos proyectos y limita la capacidad de mantener el marco.</span><span class="sxs-lookup"><span data-stu-id="c58e9-107">Unfortunately, accidental use of these types has been common, resulting in breaking changes to these projects and limiting the ability to maintain the framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c58e9-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="c58e9-108">Version introduced</span></span>

<span data-ttu-id="c58e9-109">3.0</span><span class="sxs-lookup"><span data-stu-id="c58e9-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="c58e9-110">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="c58e9-110">Old behavior</span></span>

<span data-ttu-id="c58e9-111">Estos tipos eran visibles públicamente, pero no eran compatibles.</span><span class="sxs-lookup"><span data-stu-id="c58e9-111">These types were publicly visible, but unsupported.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="c58e9-112">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="c58e9-112">New behavior</span></span>

<span data-ttu-id="c58e9-113">Estos tipos ahora son `internal`.</span><span class="sxs-lookup"><span data-stu-id="c58e9-113">These types are now `internal`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c58e9-114">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="c58e9-114">Reason for change</span></span>

<span data-ttu-id="c58e9-115">El ámbito de `internal` refleja mejor la directiva no compatible.</span><span class="sxs-lookup"><span data-stu-id="c58e9-115">The `internal` scope better reflects the unsupported policy.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c58e9-116">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="c58e9-116">Recommended action</span></span>

<span data-ttu-id="c58e9-117">Copiar los tipos que usa la aplicación o biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c58e9-117">Copy types that are used by your app or library.</span></span>

#### <a name="category"></a><span data-ttu-id="c58e9-118">Categoría</span><span class="sxs-lookup"><span data-stu-id="c58e9-118">Category</span></span>

<span data-ttu-id="c58e9-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c58e9-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c58e9-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c58e9-120">Affected APIs</span></span>

- `Microsoft.AspNetCore.ResponseCaching.Internal.CachedResponse`
- `Microsoft.AspNetCore.ResponseCaching.Internal.CachedVaryByRules`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCacheEntry`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider`
- `Microsoft.AspNetCore.ResponseCaching.Internal.MemoryResponseCache`
- `Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingContext`
- `Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingKeyProvider`
- `Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingPolicyProvider`
- <xref:Microsoft.AspNetCore.ResponseCaching.ResponseCachingMiddleware.%23ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.ResponseCaching.ResponseCachingOptions},Microsoft.Extensions.Logging.ILoggerFactory,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.ResponseCaching.Internal.CachedResponse`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.CachedVaryByRules`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCacheEntry`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.MemoryResponseCache`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingContext`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingKeyProvider`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingPolicyProvider`
- `M:Microsoft.AspNetCore.ResponseCaching.ResponseCachingMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.ResponseCaching.ResponseCachingOptions},Microsoft.Extensions.Logging.ILoggerFactory,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider)",
"nameWithType": "ResponseCachingMiddleware.ResponseCachingMiddleware(RequestDelegate, IOptions<ResponseCachingOptions>, ILoggerFactory, IResponseCachingPolicyProvider, IResponseCache, IResponseCachingKeyProvider)`

-->
