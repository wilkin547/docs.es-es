---
ms.openlocfilehash: c861d61cbbe8075db4b17a702e863336ea621f2b
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198567"
---
### <a name="http-synchronous-io-disabled-in-all-servers"></a><span data-ttu-id="a3895-101">HTTP: se ha deshabilitado la E/S sincrónica en todos los servidores</span><span class="sxs-lookup"><span data-stu-id="a3895-101">HTTP: Synchronous IO disabled in all servers</span></span>

<span data-ttu-id="a3895-102">A partir de ASP.NET Core 3.0, las operaciones de servidor sincrónicas están deshabilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a3895-102">Starting with ASP.NET Core 3.0, synchronous server operations are disabled by default.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a3895-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="a3895-103">Change description</span></span>

<span data-ttu-id="a3895-104">`AllowSynchronousIO` es una opción en cada servidor que habilita o deshabilita las API de E/S sincrónicas, como `HttpRequest.Body.Read`, `HttpResponse.Body.Write` y `Stream.Flush`.</span><span class="sxs-lookup"><span data-stu-id="a3895-104">`AllowSynchronousIO` is an option in each server that enables or disables synchronous IO APIs like `HttpRequest.Body.Read`, `HttpResponse.Body.Write`, and `Stream.Flush`.</span></span> <span data-ttu-id="a3895-105">Estas API han sido durante mucho tiempo una fuente de colapsos de subprocesos y de bloqueos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3895-105">These APIs have long been a source of thread starvation and app hangs.</span></span> <span data-ttu-id="a3895-106">A partir de ASP.NET Core 3.0, versión preliminar 3, estas operaciones sincrónicas están deshabilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a3895-106">Starting in ASP.NET Core 3.0 Preview 3, these synchronous operations are disabled by default.</span></span>

<span data-ttu-id="a3895-107">Servidores afectados:</span><span class="sxs-lookup"><span data-stu-id="a3895-107">Affected servers:</span></span>

- <span data-ttu-id="a3895-108">Kestrel</span><span class="sxs-lookup"><span data-stu-id="a3895-108">Kestrel</span></span>
- <span data-ttu-id="a3895-109">HttpSys</span><span class="sxs-lookup"><span data-stu-id="a3895-109">HttpSys</span></span>
- <span data-ttu-id="a3895-110">IIS en proceso</span><span class="sxs-lookup"><span data-stu-id="a3895-110">IIS in-process</span></span>
- <span data-ttu-id="a3895-111">TestServer</span><span class="sxs-lookup"><span data-stu-id="a3895-111">TestServer</span></span>

<span data-ttu-id="a3895-112">Se esperan errores parecidos a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a3895-112">Expect errors similar to:</span></span>

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

<span data-ttu-id="a3895-113">Cada servidor tiene una opción `AllowSynchronousIO` que controla este comportamiento y el valor predeterminado para todos ellos ahora es `false`.</span><span class="sxs-lookup"><span data-stu-id="a3895-113">Each server has an `AllowSynchronousIO` option that controls this behavior and the default for all of them is now `false`.</span></span>

<span data-ttu-id="a3895-114">El comportamiento también se puede invalidar en función de cada solicitud como una mitigación temporal.</span><span class="sxs-lookup"><span data-stu-id="a3895-114">The behavior can also be overridden on a per-request basis as a temporary mitigation.</span></span> <span data-ttu-id="a3895-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a3895-115">For example:</span></span>

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

<span data-ttu-id="a3895-116">Si tiene problemas con una elemento `TextWriter` u otra secuencia que llama a una API sincrónica en `Dispose`, llame a la nueva API de `DisposeAsync` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="a3895-116">If you have trouble with a `TextWriter` or another stream calling a synchronous API in `Dispose`, call the new `DisposeAsync` API instead.</span></span>

<span data-ttu-id="a3895-117">Para obtener información, vea [aspnet/AspNetCore#7644](https://github.com/aspnet/AspNetCore/issues/7644).</span><span class="sxs-lookup"><span data-stu-id="a3895-117">For discussion, see [aspnet/AspNetCore#7644](https://github.com/aspnet/AspNetCore/issues/7644).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a3895-118">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="a3895-118">Version introduced</span></span>

<span data-ttu-id="a3895-119">3.0</span><span class="sxs-lookup"><span data-stu-id="a3895-119">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a3895-120">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="a3895-120">Old behavior</span></span>

<span data-ttu-id="a3895-121">De manera predeterminada, solo se permitían `HttpRequest.Body.Read`, `HttpResponse.Body.Write` y `Stream.Flush`.</span><span class="sxs-lookup"><span data-stu-id="a3895-121">`HttpRequest.Body.Read`, `HttpResponse.Body.Write`, and `Stream.Flush` were allowed by default.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a3895-122">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="a3895-122">New behavior</span></span>

<span data-ttu-id="a3895-123">Estas API sincrónicas no están permitidas de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="a3895-123">These synchronous APIs are disallowed by default:</span></span>

<span data-ttu-id="a3895-124">Se esperan errores parecidos a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a3895-124">Expect errors similar to:</span></span>

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

#### <a name="reason-for-change"></a><span data-ttu-id="a3895-125">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="a3895-125">Reason for change</span></span>

<span data-ttu-id="a3895-126">Estas API sincrónicas han sido durante mucho tiempo una fuente de colapsos de subprocesos y de bloqueos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3895-126">These synchronous APIs have long been a source of thread starvation and app hangs.</span></span> <span data-ttu-id="a3895-127">A partir de ASP.NET Core 3.0, versión preliminar 3, las operaciones sincrónicas están deshabilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a3895-127">Starting in ASP.NET Core 3.0 Preview 3, the synchronous operations are disabled by default.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a3895-128">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="a3895-128">Recommended action</span></span>

<span data-ttu-id="a3895-129">Use las versiones asincrónicas de los métodos.</span><span class="sxs-lookup"><span data-stu-id="a3895-129">Use the asynchronous versions of the methods.</span></span> <span data-ttu-id="a3895-130">El comportamiento también se puede invalidar en función de cada solicitud como una mitigación temporal.</span><span class="sxs-lookup"><span data-stu-id="a3895-130">The behavior can also be overridden on a per-request basis as a temporary mitigation.</span></span>

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

#### <a name="category"></a><span data-ttu-id="a3895-131">Categoría</span><span class="sxs-lookup"><span data-stu-id="a3895-131">Category</span></span>

<span data-ttu-id="a3895-132">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a3895-132">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a3895-133">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a3895-133">Affected APIs</span></span>

- <xref:System.IO.Stream.Flush%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.IO.Stream.Flush`
- `Overload:System.IO.Stream.Read`
- `Overload:System.IO.Stream.Write`

-->
