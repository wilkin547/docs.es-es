---
title: 'Cambio importante: Localización: se han eliminado la clase ResourceManagerWithCultureStringLocalizer y el miembro de interfaz WithCulture'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Localización: se han eliminado la clase ResourceManagerWithCultureStringLocalizer y el miembro de interfaz WithCulture'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: cba8458f20bad77ad6c125448f192939387ba405
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760238"
---
# <a name="localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed"></a><span data-ttu-id="b96e9-103">Localización: se han eliminado la clase ResourceManagerWithCultureStringLocalizer y el miembro de interfaz WithCulture</span><span class="sxs-lookup"><span data-stu-id="b96e9-103">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>

<span data-ttu-id="b96e9-104">Se han eliminado la clase [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) y el método [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) en .NET 5.0 (versión preliminar 1).</span><span class="sxs-lookup"><span data-stu-id="b96e9-104">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were removed in .NET 5.0 Preview 1.</span></span>

<span data-ttu-id="b96e9-105">Para obtener el contexto, consulte [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) y [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span><span class="sxs-lookup"><span data-stu-id="b96e9-105">For context, see [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) and [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span></span> <span data-ttu-id="b96e9-106">Para obtener información sobre este cambio, vea [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span><span class="sxs-lookup"><span data-stu-id="b96e9-106">For discussion on this change, see [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="b96e9-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="b96e9-107">Version introduced</span></span>

<span data-ttu-id="b96e9-108">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="b96e9-108">5.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="b96e9-109">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="b96e9-109">Old behavior</span></span>

<span data-ttu-id="b96e9-110">La clase `ResourceManagerWithCultureStringLocalizer` y el método `ResourceManagerStringLocalizer.WithCulture` están [obsoletos en .NET Core 3.0 (versión preliminar 3 y posteriores)](../../../../core/compatibility/2.2-3.0.md#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).</span><span class="sxs-lookup"><span data-stu-id="b96e9-110">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method are [obsolete in .NET Core 3.0 Preview 3 and later](../../../../core/compatibility/2.2-3.0.md#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).</span></span>

## <a name="new-behavior"></a><span data-ttu-id="b96e9-111">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="b96e9-111">New behavior</span></span>

<span data-ttu-id="b96e9-112">La clase `ResourceManagerWithCultureStringLocalizer` y el método `ResourceManagerStringLocalizer.WithCulture` se han quitado de .NET 5.0 (versión preliminar 1).</span><span class="sxs-lookup"><span data-stu-id="b96e9-112">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method have been removed in .NET 5.0 Preview 1.</span></span> <span data-ttu-id="b96e9-113">Para ver un inventario de los cambios realizados, consulte la solicitud de incorporación de cambios en [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).</span><span class="sxs-lookup"><span data-stu-id="b96e9-113">For an inventory of the changes made, see the pull request at [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="b96e9-114">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="b96e9-114">Reason for change</span></span>

<span data-ttu-id="b96e9-115">La clase [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) y el método [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) solían causar confusión a los usuarios de localización.</span><span class="sxs-lookup"><span data-stu-id="b96e9-115">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were often sources of confusion for users of localization.</span></span> <span data-ttu-id="b96e9-116">La confusión era más marcada cuando se creaba una implementación de <xref:Microsoft.Extensions.Localization.IStringLocalizer> personalizada.</span><span class="sxs-lookup"><span data-stu-id="b96e9-116">The confusion was especially high when creating a custom <xref:Microsoft.Extensions.Localization.IStringLocalizer> implementation.</span></span> <span data-ttu-id="b96e9-117">Esta clase y método dan a los consumidores la impresión de que se espera que una instancia de `IStringLocalizer` sea "por idioma y por recurso".</span><span class="sxs-lookup"><span data-stu-id="b96e9-117">This class and method give consumers the impression that an `IStringLocalizer` instance is expected to be "per-language, per-resource".</span></span> <span data-ttu-id="b96e9-118">En realidad, la instancia solo debe ser "por recurso".</span><span class="sxs-lookup"><span data-stu-id="b96e9-118">In reality, the instance should only be "per-resource".</span></span> <span data-ttu-id="b96e9-119">En tiempo de ejecución, la propiedad <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> determina el idioma que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="b96e9-119">At run time, the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> property determines the language to be used.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b96e9-120">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="b96e9-120">Recommended action</span></span>

<span data-ttu-id="b96e9-121">Deje de usar la clase `ResourceManagerWithCultureStringLocalizer` y el método `ResourceManagerStringLocalizer.WithCulture`.</span><span class="sxs-lookup"><span data-stu-id="b96e9-121">Stop using the `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="b96e9-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b96e9-122">Affected APIs</span></span>

- [<span data-ttu-id="b96e9-123">ResourceManagerWithCultureStringLocalizer</span><span class="sxs-lookup"><span data-stu-id="b96e9-123">ResourceManagerWithCultureStringLocalizer</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)
- [<span data-ttu-id="b96e9-124">ResourceManagerStringLocalizer.WithCulture</span><span class="sxs-lookup"><span data-stu-id="b96e9-124">ResourceManagerStringLocalizer.WithCulture</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
