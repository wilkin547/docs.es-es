---
ms.openlocfilehash: 6deeb7debce9b731f3871b7de0ad8df8a8cdafea
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728295"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed"></a><span data-ttu-id="8dadb-101">Localización: se han eliminado la clase ResourceManagerWithCultureStringLocalizer y el miembro de interfaz WithCulture</span><span class="sxs-lookup"><span data-stu-id="8dadb-101">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>

<span data-ttu-id="8dadb-102">Se han eliminado la clase [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) y el método [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) en .NET 5.0 (versión preliminar 1).</span><span class="sxs-lookup"><span data-stu-id="8dadb-102">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were removed in .NET 5.0 Preview 1.</span></span>

<span data-ttu-id="8dadb-103">Para obtener el contexto, consulte [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) y [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span><span class="sxs-lookup"><span data-stu-id="8dadb-103">For context, see [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) and [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span></span> <span data-ttu-id="8dadb-104">Para obtener información sobre este cambio, vea [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span><span class="sxs-lookup"><span data-stu-id="8dadb-104">For discussion on this change, see [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8dadb-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="8dadb-105">Version introduced</span></span>

<span data-ttu-id="8dadb-106">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="8dadb-106">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="8dadb-107">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="8dadb-107">Old behavior</span></span>

<span data-ttu-id="8dadb-108">La clase `ResourceManagerWithCultureStringLocalizer` y el método `ResourceManagerStringLocalizer.WithCulture` están [obsoletos en .NET Core 3.0 (versión preliminar 3 y posteriores)](/dotnet/core/compatibility/2.2-3.0#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).</span><span class="sxs-lookup"><span data-stu-id="8dadb-108">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method are [obsolete in .NET Core 3.0 Preview 3 and later](/dotnet/core/compatibility/2.2-3.0#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="8dadb-109">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="8dadb-109">New behavior</span></span>

<span data-ttu-id="8dadb-110">La clase `ResourceManagerWithCultureStringLocalizer` y el método `ResourceManagerStringLocalizer.WithCulture` se han quitado de .NET 5.0 (versión preliminar 1).</span><span class="sxs-lookup"><span data-stu-id="8dadb-110">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method have been removed in .NET 5.0 Preview 1.</span></span> <span data-ttu-id="8dadb-111">Para ver un inventario de los cambios realizados, consulte la solicitud de incorporación de cambios en [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).</span><span class="sxs-lookup"><span data-stu-id="8dadb-111">For an inventory of the changes made, see the pull request at [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="8dadb-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="8dadb-112">Reason for change</span></span>

<span data-ttu-id="8dadb-113">La clase [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) y el método [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) solían causar confusión a los usuarios de localización.</span><span class="sxs-lookup"><span data-stu-id="8dadb-113">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were often sources of confusion for users of localization.</span></span> <span data-ttu-id="8dadb-114">La confusión era más marcada cuando se creaba una implementación de <xref:Microsoft.Extensions.Localization.IStringLocalizer> personalizada.</span><span class="sxs-lookup"><span data-stu-id="8dadb-114">The confusion was especially high when creating a custom <xref:Microsoft.Extensions.Localization.IStringLocalizer> implementation.</span></span> <span data-ttu-id="8dadb-115">Esta clase y método dan a los consumidores la impresión de que se espera que una instancia de `IStringLocalizer` sea "por idioma y por recurso".</span><span class="sxs-lookup"><span data-stu-id="8dadb-115">This class and method give consumers the impression that an `IStringLocalizer` instance is expected to be "per-language, per-resource".</span></span> <span data-ttu-id="8dadb-116">En realidad, la instancia solo debe ser "por recurso".</span><span class="sxs-lookup"><span data-stu-id="8dadb-116">In reality, the instance should only be "per-resource".</span></span> <span data-ttu-id="8dadb-117">En tiempo de ejecución, la propiedad <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> determina el idioma que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="8dadb-117">At run time, the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> property determines the language to be used.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8dadb-118">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="8dadb-118">Recommended action</span></span>

<span data-ttu-id="8dadb-119">Deje de usar la clase `ResourceManagerWithCultureStringLocalizer` y el método `ResourceManagerStringLocalizer.WithCulture`.</span><span class="sxs-lookup"><span data-stu-id="8dadb-119">Stop using the `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method.</span></span>

#### <a name="category"></a><span data-ttu-id="8dadb-120">Categoría</span><span class="sxs-lookup"><span data-stu-id="8dadb-120">Category</span></span>

<span data-ttu-id="8dadb-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8dadb-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8dadb-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8dadb-122">Affected APIs</span></span>

- [<span data-ttu-id="8dadb-123">ResourceManagerWithCultureStringLocalizer</span><span class="sxs-lookup"><span data-stu-id="8dadb-123">ResourceManagerWithCultureStringLocalizer</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)
- [<span data-ttu-id="8dadb-124">ResourceManagerStringLocalizer.WithCulture</span><span class="sxs-lookup"><span data-stu-id="8dadb-124">ResourceManagerStringLocalizer.WithCulture</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
