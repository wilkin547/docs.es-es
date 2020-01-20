---
ms.openlocfilehash: 58b1190e3e6a3168d35700eed655f6756e076a29
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901779"
---
### <a name="mvc-async-suffix-trimmed-from-controller-action-names"></a><span data-ttu-id="ff90d-101">MVC: se ha recortado el sufijo Async de los nombres de acción de controlador</span><span class="sxs-lookup"><span data-stu-id="ff90d-101">MVC: Async suffix trimmed from controller action names</span></span>

<span data-ttu-id="ff90d-102">Como parte de la solución de [dotnet/aspnetcore#4849](https://github.com/dotnet/aspnetcore/issues/4849), en ASP.NET Core MVC se recorta el sufijo `Async` de los nombres de acción de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ff90d-102">As part of addressing [dotnet/aspnetcore#4849](https://github.com/dotnet/aspnetcore/issues/4849), ASP.NET Core MVC trims the suffix `Async` from action names by default.</span></span> <span data-ttu-id="ff90d-103">A partir de ASP.NET Core 3.0, este cambio afecta tanto al enrutamiento como a la generación de vínculos.</span><span class="sxs-lookup"><span data-stu-id="ff90d-103">Starting with ASP.NET Core 3.0, this change affects both routing and link generation.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ff90d-104">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ff90d-104">Version introduced</span></span>

<span data-ttu-id="ff90d-105">3.0</span><span class="sxs-lookup"><span data-stu-id="ff90d-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ff90d-106">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="ff90d-106">Old behavior</span></span>

<span data-ttu-id="ff90d-107">Tenga en cuenta el siguiente controlador de ASP.NET Core MVC:</span><span class="sxs-lookup"><span data-stu-id="ff90d-107">Consider the following ASP.NET Core MVC controller:</span></span>

```csharp
public class ProductController : Controller
{
    public async IActionResult ListAsync()
    {
        var model = await DbContext.Products.ToListAsync();
        return View(model);
    }
}
```

<span data-ttu-id="ff90d-108">La acción es enrutable mediante `Product/ListAsync`.</span><span class="sxs-lookup"><span data-stu-id="ff90d-108">The action is routable via `Product/ListAsync`.</span></span> <span data-ttu-id="ff90d-109">La generación de vínculos requiere que se especifique el sufijo `Async`.</span><span class="sxs-lookup"><span data-stu-id="ff90d-109">Link generation requires specifying the `Async` suffix.</span></span> <span data-ttu-id="ff90d-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ff90d-110">For example:</span></span>

```cshtml
<a asp-controller="Product" asp-action="ListAsync">List</a>
```

#### <a name="new-behavior"></a><span data-ttu-id="ff90d-111">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="ff90d-111">New behavior</span></span>

<span data-ttu-id="ff90d-112">En ASP.NET Core 3.0, la acción es enrutable mediante `Product/List`.</span><span class="sxs-lookup"><span data-stu-id="ff90d-112">In ASP.NET Core 3.0, the action is routable via `Product/List`.</span></span> <span data-ttu-id="ff90d-113">El código de generación de vínculos debe omitir el sufijo `Async`.</span><span class="sxs-lookup"><span data-stu-id="ff90d-113">Link generation code should omit the `Async` suffix.</span></span> <span data-ttu-id="ff90d-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ff90d-114">For example:</span></span>

```cshtml
<a asp-controller="Product" asp-action="List">List</a>
```

<span data-ttu-id="ff90d-115">Este cambio no afecta a los nombres especificados mediante el atributo `[ActionName]`.</span><span class="sxs-lookup"><span data-stu-id="ff90d-115">This change doesn't affect names specified using the `[ActionName]` attribute.</span></span> <span data-ttu-id="ff90d-116">El nuevo comportamiento se puede deshabilitar si se establece `MvcOptions.SuppressAsyncSuffixInActionNames` en `false` en `Startup.ConfigureServices`:</span><span class="sxs-lookup"><span data-stu-id="ff90d-116">The new behavior can be disabled by setting `MvcOptions.SuppressAsyncSuffixInActionNames` to `false` in `Startup.ConfigureServices`:</span></span>

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="reason-for-change"></a><span data-ttu-id="ff90d-117">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="ff90d-117">Reason for change</span></span>

<span data-ttu-id="ff90d-118">Por convención, los métodos asincrónicos de .NET tienen el sufijo `Async`.</span><span class="sxs-lookup"><span data-stu-id="ff90d-118">By convention, asynchronous .NET methods are suffixed with `Async`.</span></span> <span data-ttu-id="ff90d-119">Pero cuando un método define una acción de MVC, no es recomendable usar el sufijo `Async`.</span><span class="sxs-lookup"><span data-stu-id="ff90d-119">However, when a method defines an MVC action, it's undesirable to use the `Async` suffix.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ff90d-120">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="ff90d-120">Recommended action</span></span>

<span data-ttu-id="ff90d-121">Si la aplicación depende de que las acciones de MVC conserven el sufijo `Async` del nombre, elija una de las mitigaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff90d-121">If your app depends on MVC actions preserving the name's `Async` suffix, choose one of the following mitigations:</span></span>

- <span data-ttu-id="ff90d-122">Use el atributo `[ActionName]` para conservar el nombre original.</span><span class="sxs-lookup"><span data-stu-id="ff90d-122">Use the `[ActionName]` attribute to preserve the original name.</span></span>
- <span data-ttu-id="ff90d-123">Establezca `MvcOptions.SuppressAsyncSuffixInActionNames` en `false` en `Startup.ConfigureServices` para deshabilitar totalmente el cambio de nombre:</span><span class="sxs-lookup"><span data-stu-id="ff90d-123">Disable the renaming entirely by setting `MvcOptions.SuppressAsyncSuffixInActionNames` to `false` in `Startup.ConfigureServices`:</span></span>

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="category"></a><span data-ttu-id="ff90d-124">Categoría</span><span class="sxs-lookup"><span data-stu-id="ff90d-124">Category</span></span>

<span data-ttu-id="ff90d-125">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ff90d-125">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ff90d-126">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ff90d-126">Affected APIs</span></span>

<span data-ttu-id="ff90d-127">None</span><span class="sxs-lookup"><span data-stu-id="ff90d-127">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
