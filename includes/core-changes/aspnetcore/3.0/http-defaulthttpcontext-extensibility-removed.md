---
ms.openlocfilehash: 1b4b0aba3ea24682ae972bf283ac387692c83781
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901885"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a><span data-ttu-id="d3144-101">HTTP: se ha quitado la extensibilidad de DefaultHttpContext</span><span class="sxs-lookup"><span data-stu-id="d3144-101">HTTP: DefaultHttpContext extensibility removed</span></span>

<span data-ttu-id="d3144-102">Como parte de las mejoras de rendimiento de ASP.NET Core 3.0, se ha quitado la extensibilidad de `DefaultHttpContext`.</span><span class="sxs-lookup"><span data-stu-id="d3144-102">As part of ASP.NET Core 3.0 performance improvements, the extensibility of `DefaultHttpContext` was removed.</span></span> <span data-ttu-id="d3144-103">La clase ahora es `sealed`.</span><span class="sxs-lookup"><span data-stu-id="d3144-103">The class is now `sealed`.</span></span> <span data-ttu-id="d3144-104">Para obtener más información, consulte [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504).</span><span class="sxs-lookup"><span data-stu-id="d3144-104">For more information, see [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504).</span></span>

<span data-ttu-id="d3144-105">Si las pruebas unitarias usan `Mock<DefaultHttpContext>`, utilice `Mock<HttpContext>` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d3144-105">If your unit tests use `Mock<DefaultHttpContext>`, use `Mock<HttpContext>` instead.</span></span>

<span data-ttu-id="d3144-106">Para obtener información, vea [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534).</span><span class="sxs-lookup"><span data-stu-id="d3144-106">For discussion, see [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d3144-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d3144-107">Version introduced</span></span>

<span data-ttu-id="d3144-108">3.0</span><span class="sxs-lookup"><span data-stu-id="d3144-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d3144-109">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="d3144-109">Old behavior</span></span>

<span data-ttu-id="d3144-110">Las clases se pueden derivar de `DefaultHttpContext`.</span><span class="sxs-lookup"><span data-stu-id="d3144-110">Classes can derive from `DefaultHttpContext`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d3144-111">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="d3144-111">New behavior</span></span>

<span data-ttu-id="d3144-112">Las clases se pueden derivar de `DefaultHttpContext`.</span><span class="sxs-lookup"><span data-stu-id="d3144-112">Classes can't derive from `DefaultHttpContext`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d3144-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="d3144-113">Reason for change</span></span>

<span data-ttu-id="d3144-114">La extensibilidad se proporcionó inicialmente para permitir la agrupación de `HttpContext`, pero incorporaba una complejidad innecesaria e impedía otras optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="d3144-114">The extensibility was provided initially to allow pooling of the `HttpContext`, but it introduced unnecessary complexity and impeded other optimizations.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d3144-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d3144-115">Recommended action</span></span>

<span data-ttu-id="d3144-116">Si usa `Mock<DefaultHttpContext>` en las pruebas unitarias, empiece a usar `Mock<HttpContext>` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d3144-116">If you're using `Mock<DefaultHttpContext>` in your unit tests, begin using `Mock<HttpContext>` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="d3144-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="d3144-117">Category</span></span>

<span data-ttu-id="d3144-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d3144-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d3144-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d3144-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
