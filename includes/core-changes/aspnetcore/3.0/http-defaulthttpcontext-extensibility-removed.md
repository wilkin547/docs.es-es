---
ms.openlocfilehash: 177617569a93e09f4c2a05acc21dce362edd58bc
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394037"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a><span data-ttu-id="cc23c-101">HTTP: se ha quitado la extensibilidad de DefaultHttpContext</span><span class="sxs-lookup"><span data-stu-id="cc23c-101">HTTP: DefaultHttpContext extensibility removed</span></span>

<span data-ttu-id="cc23c-102">Como parte de las mejoras de rendimiento de ASP.NET Core 3.0, se ha quitado la extensibilidad de `DefaultHttpContext`.</span><span class="sxs-lookup"><span data-stu-id="cc23c-102">As part of ASP.NET Core 3.0 performance improvements, the extensibility of `DefaultHttpContext` was removed.</span></span> <span data-ttu-id="cc23c-103">La clase ahora es `sealed`.</span><span class="sxs-lookup"><span data-stu-id="cc23c-103">The class is now `sealed`.</span></span> <span data-ttu-id="cc23c-104">Para obtener más información, consulte [aspnet/AspNetCore#6504](https://github.com/aspnet/AspNetCore/pull/6504).</span><span class="sxs-lookup"><span data-stu-id="cc23c-104">For more information, see [aspnet/AspNetCore#6504](https://github.com/aspnet/AspNetCore/pull/6504).</span></span>

<span data-ttu-id="cc23c-105">Si las pruebas unitarias usan `Mock<DefaultHttpContext>`, utilice `Mock<HttpContext>` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="cc23c-105">If your unit tests use `Mock<DefaultHttpContext>`, use `Mock<HttpContext>` instead.</span></span> 

<span data-ttu-id="cc23c-106">Para obtener información, consulte [aspnet/AspNetCore#6534](https://github.com/aspnet/AspNetCore/issues/6534).</span><span class="sxs-lookup"><span data-stu-id="cc23c-106">For discussion, see [aspnet/AspNetCore#6534](https://github.com/aspnet/AspNetCore/issues/6534).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cc23c-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="cc23c-107">Version introduced</span></span>

<span data-ttu-id="cc23c-108">3.0</span><span class="sxs-lookup"><span data-stu-id="cc23c-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="cc23c-109">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="cc23c-109">Old behavior</span></span>

<span data-ttu-id="cc23c-110">Las clases se pueden derivar de `DefaultHttpContext`.</span><span class="sxs-lookup"><span data-stu-id="cc23c-110">Classes can derive from `DefaultHttpContext`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="cc23c-111">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="cc23c-111">New behavior</span></span>

<span data-ttu-id="cc23c-112">Las clases se pueden derivar de `DefaultHttpContext`.</span><span class="sxs-lookup"><span data-stu-id="cc23c-112">Classes can't derive from `DefaultHttpContext`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="cc23c-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="cc23c-113">Reason for change</span></span>

<span data-ttu-id="cc23c-114">La extensibilidad se proporcionó inicialmente para permitir la agrupación de `HttpContext`, pero incorporaba una complejidad innecesaria e impedía otras optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="cc23c-114">The extensibility was provided initially to allow pooling of the `HttpContext`, but it introduced unnecessary complexity and impeded other optimizations.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cc23c-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="cc23c-115">Recommended action</span></span>

<span data-ttu-id="cc23c-116">Si usa `Mock<DefaultHttpContext>` en las pruebas unitarias, empiece a usar `Mock<HttpContext>` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="cc23c-116">If you're using `Mock<DefaultHttpContext>` in your unit tests, begin using `Mock<HttpContext>` instead.</span></span> 

#### <a name="category"></a><span data-ttu-id="cc23c-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="cc23c-117">Category</span></span>

<span data-ttu-id="cc23c-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cc23c-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cc23c-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="cc23c-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
