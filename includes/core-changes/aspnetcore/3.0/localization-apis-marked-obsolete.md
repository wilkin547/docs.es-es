---
ms.openlocfilehash: d70a8d2a3031a5b3d47ab3fb7f40193dce6e311e
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728329"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete"></a><span data-ttu-id="9ddf5-101">Localización: ResourceManagerWithCultureStringLocalizer y WithCulture se han marcado como obsoletos</span><span class="sxs-lookup"><span data-stu-id="9ddf5-101">Localization: ResourceManagerWithCultureStringLocalizer and WithCulture marked obsolete</span></span>

<span data-ttu-id="9ddf5-102">La clase [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) y el miembro de interfaz [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) suelen ser fuentes de confusión para los usuarios de localización, en particular al crear su propia implementación de `IStringLocalizer`.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-102">The [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) class and [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) interface member are often sources of confusion for users of localization, especially when creating their own `IStringLocalizer` implementation.</span></span> <span data-ttu-id="9ddf5-103">Estos elementos proporcionan al usuario la impresión de que una instancia de `IStringLocalizer` es "por lenguaje y por recurso".</span><span class="sxs-lookup"><span data-stu-id="9ddf5-103">These items give the user the impression that an `IStringLocalizer` instance is "per-language, per-resource".</span></span> <span data-ttu-id="9ddf5-104">En realidad, las instancias solo deben ser "por recurso".</span><span class="sxs-lookup"><span data-stu-id="9ddf5-104">In reality, the instances should only be "per-resource".</span></span> <span data-ttu-id="9ddf5-105">El lenguaje que se busca lo determina el `CultureInfo.CurrentUICulture` en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-105">The language searched for is determined by the `CultureInfo.CurrentUICulture` at execution time.</span></span> <span data-ttu-id="9ddf5-106">Para eliminar el origen de la confusión, las API se han marcado como obsoletas en ASP.NET Core 3.0, versión preliminar 3.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-106">To eliminate the source of confusion, the APIs were marked as obsolete in ASP.NET Core 3.0 Preview 3.</span></span> <span data-ttu-id="9ddf5-107">Las API se quitarán en una versión futura.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-107">The APIs will be removed in a future release.</span></span>

<span data-ttu-id="9ddf5-108">Para obtener el contexto, consulte [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span><span class="sxs-lookup"><span data-stu-id="9ddf5-108">For context, see [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span></span> <span data-ttu-id="9ddf5-109">Para obtener información, vea [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span><span class="sxs-lookup"><span data-stu-id="9ddf5-109">For discussion, see [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9ddf5-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="9ddf5-110">Version introduced</span></span>

<span data-ttu-id="9ddf5-111">3.0</span><span class="sxs-lookup"><span data-stu-id="9ddf5-111">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="9ddf5-112">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="9ddf5-112">Old behavior</span></span>

<span data-ttu-id="9ddf5-113">Los métodos no se marcaban como `Obsolete`.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-113">Methods weren't marked as `Obsolete`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="9ddf5-114">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="9ddf5-114">New behavior</span></span>

<span data-ttu-id="9ddf5-115">Los métodos se marcan como `Obsolete`.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-115">Methods are marked `Obsolete`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9ddf5-116">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="9ddf5-116">Reason for change</span></span>

<span data-ttu-id="9ddf5-117">Las API representan un caso de uso que no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-117">The APIs represented a use case that isn't recommended.</span></span> <span data-ttu-id="9ddf5-118">Ha habido confusión sobre el diseño de la localización.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-118">There was confusion about the design of localization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9ddf5-119">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="9ddf5-119">Recommended action</span></span>

<span data-ttu-id="9ddf5-120">La recomendación es usar `ResourceManagerStringLocalizer` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-120">The recommendation is to use `ResourceManagerStringLocalizer` instead.</span></span> <span data-ttu-id="9ddf5-121">Permita que `CurrentCulture` establezca la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-121">Let the culture be set by the `CurrentCulture`.</span></span> <span data-ttu-id="9ddf5-122">Si no es una opción, cree y use una copia de [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18).</span><span class="sxs-lookup"><span data-stu-id="9ddf5-122">If that isn't an option, create and use a copy of [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18).</span></span>

#### <a name="category"></a><span data-ttu-id="9ddf5-123">Categoría</span><span class="sxs-lookup"><span data-stu-id="9ddf5-123">Category</span></span>

<span data-ttu-id="9ddf5-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9ddf5-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9ddf5-125">API afectadas</span><span class="sxs-lookup"><span data-stu-id="9ddf5-125">Affected APIs</span></span>

- [<span data-ttu-id="9ddf5-126">ResourceManagerWithCultureStringLocalizer</span><span class="sxs-lookup"><span data-stu-id="9ddf5-126">ResourceManagerWithCultureStringLocalizer</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.0)
- [<span data-ttu-id="9ddf5-127">ResourceManagerStringLocalizer.WithCulture</span><span class="sxs-lookup"><span data-stu-id="9ddf5-127">ResourceManagerStringLocalizer.WithCulture</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.0)

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
