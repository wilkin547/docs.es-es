---
ms.openlocfilehash: 203d75f5858c8ff039cf579c0539efda0c5c9f02
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474388"
---
### <a name="kestrel-libuv-transport-marked-as-obsolete"></a><span data-ttu-id="34487-101">Kestrel: transporte de libuv marcado como obsoleto</span><span class="sxs-lookup"><span data-stu-id="34487-101">Kestrel: Libuv transport marked as obsolete</span></span>

<span data-ttu-id="34487-102">Las versiones anteriores de ASP.NET Core usaban Libuv como un detalle de implementación de cómo se realizaba la entrada y salida asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="34487-102">Earlier versions of ASP.NET Core used Libuv as an implementation detail of how asynchronous input and output was performed.</span></span> <span data-ttu-id="34487-103">En ASP.NET Core 2.0 se desarrolló un transporte alternativo basado en <xref:System.Net.Sockets.Socket>.</span><span class="sxs-lookup"><span data-stu-id="34487-103">In ASP.NET Core 2.0, an alternative, <xref:System.Net.Sockets.Socket>-based transport was developed.</span></span> <span data-ttu-id="34487-104">En ASP.NET Core 2.1, Kestrel pasó a usar el transporte basado en `Socket`de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="34487-104">In ASP.NET Core 2.1, Kestrel switched to using the `Socket`-based transport by default.</span></span> <span data-ttu-id="34487-105">La compatibilidad de Libuv se mantuvo por motivos de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="34487-105">Libuv support was maintained for compatibility reasons.</span></span>

<span data-ttu-id="34487-106">En este momento, el uso del transporte basado en `Socket` es mucho más común que el transporte de Libuv.</span><span class="sxs-lookup"><span data-stu-id="34487-106">At this point, use of the `Socket`-based transport is far more common than the Libuv transport.</span></span> <span data-ttu-id="34487-107">Por lo tanto, la compatibilidad de Libuv se ha marcado como obsoleta en .NET 5.0 y se va a quitar por completo en .NET 6.0.</span><span class="sxs-lookup"><span data-stu-id="34487-107">Consequently, Libuv support is marked as obsolete in .NET 5.0 and will be removed entirely in .NET 6.0.</span></span>

<span data-ttu-id="34487-108">Como parte de este cambio, la compatibilidad de Libuv con las nuevas plataformas de sistema operativo (como Windows ARM64) no se va a agregar en el período de tiempo de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="34487-108">As part of this change, Libuv support for new operating system platforms (like Windows ARM64) won't be added in the .NET 5.0 timeframe.</span></span>

<span data-ttu-id="34487-109">Para obtener información sobre los problemas de bloqueo que requieren el uso del transporte de Libuv, vea el problema de GitHub en [dotnet/aspnetcore # 23409](https://github.com/dotnet/aspnetcore/issues/23409).</span><span class="sxs-lookup"><span data-stu-id="34487-109">For discussion on blocking issues that require the use of the Libuv transport, see the GitHub issue at [dotnet/aspnetcore#23409](https://github.com/dotnet/aspnetcore/issues/23409).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="34487-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="34487-110">Version introduced</span></span>

<span data-ttu-id="34487-111">5.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="34487-111">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="34487-112">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="34487-112">Old behavior</span></span>

<span data-ttu-id="34487-113">Las API de Libuv no están marcadas como obsoletas.</span><span class="sxs-lookup"><span data-stu-id="34487-113">The Libuv APIs aren't marked as obsolete.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="34487-114">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="34487-114">New behavior</span></span>

<span data-ttu-id="34487-115">Las API de Libuv están marcadas como obsoletas.</span><span class="sxs-lookup"><span data-stu-id="34487-115">The Libuv APIs are marked as obsolete.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="34487-116">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="34487-116">Reason for change</span></span>

<span data-ttu-id="34487-117">El transporte basado en `Socket` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="34487-117">The `Socket`-based transport is the default.</span></span> <span data-ttu-id="34487-118">No hay ningún motivo acuciante para seguir usando el transporte de Libuv.</span><span class="sxs-lookup"><span data-stu-id="34487-118">There aren't any compelling reasons to continue using the Libuv transport.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="34487-119">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="34487-119">Recommended action</span></span>

<span data-ttu-id="34487-120">Dejar de usar el [paquete Libuv](https://www.nuget.org/packages/Libuv) y los métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="34487-120">Discontinue use of the [Libuv package](https://www.nuget.org/packages/Libuv) and extension methods.</span></span>

#### <a name="category"></a><span data-ttu-id="34487-121">Categoría</span><span class="sxs-lookup"><span data-stu-id="34487-121">Category</span></span>

<span data-ttu-id="34487-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="34487-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="34487-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="34487-123">Affected APIs</span></span>

- [<span data-ttu-id="34487-124">WebHostBuilderLibuvExtensions</span><span class="sxs-lookup"><span data-stu-id="34487-124">WebHostBuilderLibuvExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions?view=aspnetcore-3.0)
- [<span data-ttu-id="34487-125">WebHostBuilderLibuvExtensions.UseLibuv</span><span class="sxs-lookup"><span data-stu-id="34487-125">WebHostBuilderLibuvExtensions.UseLibuv</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions.uselibuv?view=aspnetcore-3.0)
- [<span data-ttu-id="34487-126">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions</span><span class="sxs-lookup"><span data-stu-id="34487-126">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions?view=aspnetcore-3.0)
- [<span data-ttu-id="34487-127">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount</span><span class="sxs-lookup"><span data-stu-id="34487-127">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.threadcount?view=aspnetcore-3.0)
- [<span data-ttu-id="34487-128">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay</span><span class="sxs-lookup"><span data-stu-id="34487-128">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.nodelay?view=aspnetcore-3.0)
- [<span data-ttu-id="34487-129">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize</span><span class="sxs-lookup"><span data-stu-id="34487-129">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxwritebuffersize?view=aspnetcore-3.0)
- [<span data-ttu-id="34487-130">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize</span><span class="sxs-lookup"><span data-stu-id="34487-130">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxreadbuffersize?view=aspnetcore-3.0)
- `Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions`
- `Overload:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions.UseLibuv`
- `T:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

-->
