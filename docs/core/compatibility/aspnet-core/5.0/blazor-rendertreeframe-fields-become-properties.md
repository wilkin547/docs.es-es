---
title: 'Cambio importante: Blazor: Los campos públicos RenderTreeFrame de solo lectura se han convertido en propiedades'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Blazor: Los campos públicos RenderTreeFrame de solo lectura se han convertido en propiedades'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: e9da9c538cc0a8ed4f138ef64ece0c7d144f28d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760101"
---
# <a name="blazor-rendertreeframe-readonly-public-fields-have-become-properties"></a><span data-ttu-id="4993c-103">Blazor: Los campos públicos RenderTreeFrame de solo lectura se han convertido en propiedades</span><span class="sxs-lookup"><span data-stu-id="4993c-103">Blazor: RenderTreeFrame readonly public fields have become properties</span></span>

<span data-ttu-id="4993c-104">En ASP.NET Core 3.0 y 3.1, la estructura <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> expone varios campos de `readonly public`, como <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType>, <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence> y otros.</span><span class="sxs-lookup"><span data-stu-id="4993c-104">In ASP.NET Core 3.0 and 3.1, the <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> struct exposed various `readonly public` fields, including <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType>, <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence>, and others.</span></span> <span data-ttu-id="4993c-105">En ASP.NET Core 5.0 RC1 y versiones posteriores, todos los campos de `readonly public` se han cambiado por propiedades `readonly public`.</span><span class="sxs-lookup"><span data-stu-id="4993c-105">In ASP.NET Core 5.0 RC1 and later versions, all the `readonly public` fields changed to `readonly public` properties.</span></span>

<span data-ttu-id="4993c-106">Este cambio no afectará a muchos desarrolladores porque:</span><span class="sxs-lookup"><span data-stu-id="4993c-106">This change won't affect many developers because:</span></span>

* <span data-ttu-id="4993c-107">Cualquier aplicación o biblioteca que simplemente use archivos `.razor` (o incluso llamadas a <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> manuales) para definir sus componentes no hará referencia directamente a este tipo.</span><span class="sxs-lookup"><span data-stu-id="4993c-107">Any app or library that simply uses `.razor` files (or even manual <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> calls) to define its components wouldn't be referencing this type directly.</span></span>
* <span data-ttu-id="4993c-108">El propio tipo `RenderTreeFrame` se considera un detalle de implementación; no está diseñado para usarlo fuera del marco.</span><span class="sxs-lookup"><span data-stu-id="4993c-108">The `RenderTreeFrame` type itself is regarded as an implementation detail, not intended for use outside of the framework.</span></span> <span data-ttu-id="4993c-109">En ASP.NET Core 3.0 y versiones posteriores se incluye un analizador que emite advertencias del compilador si el tipo se usa de forma directa.</span><span class="sxs-lookup"><span data-stu-id="4993c-109">ASP.NET Core 3.0 and later includes an analyzer that issues compiler warnings if the type is being used directly.</span></span>
* <span data-ttu-id="4993c-110">Incluso si hace referencia a `RenderTreeFrame` de forma directa, este cambio afectará a los binarios, no al código fuente.</span><span class="sxs-lookup"><span data-stu-id="4993c-110">Even if you reference `RenderTreeFrame` directly, this change is binary-breaking but not source-breaking.</span></span> <span data-ttu-id="4993c-111">Es decir, el código fuente existente se compilará y se comportará de manera correcta.</span><span class="sxs-lookup"><span data-stu-id="4993c-111">That is, your existing source code will compile and behave properly.</span></span> <span data-ttu-id="4993c-112">Solo se producirá una incidencia si se compila en un marco de trabajo de .NET Core 3.x y luego esos archivos binarios se ejecutan en .NET 5.0 RC1 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="4993c-112">You'll only encounter an issue if compiling against a .NET Core 3.x framework and then running those binaries against the .NET 5.0 RC1 and later framework.</span></span>

<span data-ttu-id="4993c-113">Para obtener información, vea la incidencia de GitHub [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727).</span><span class="sxs-lookup"><span data-stu-id="4993c-113">For discussion, see GitHub issue [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="4993c-114">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="4993c-114">Version introduced</span></span>

<span data-ttu-id="4993c-115">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="4993c-115">5.0 RC1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="4993c-116">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="4993c-116">Old behavior</span></span>

<span data-ttu-id="4993c-117">Los miembros públicos de `RenderTreeFrame` se definen como campos.</span><span class="sxs-lookup"><span data-stu-id="4993c-117">Public members on `RenderTreeFrame` are defined as fields.</span></span> <span data-ttu-id="4993c-118">Por ejemplo, `renderTreeFrame.Sequence` y `renderTreeFrame.ElementName`.</span><span class="sxs-lookup"><span data-stu-id="4993c-118">For example, `renderTreeFrame.Sequence` and `renderTreeFrame.ElementName`.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="4993c-119">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="4993c-119">New behavior</span></span>

<span data-ttu-id="4993c-120">Los miembros públicos de `RenderTreeFrame` se definen como propiedades con los mismos nombres que antes.</span><span class="sxs-lookup"><span data-stu-id="4993c-120">Public members on `RenderTreeFrame` are defined as properties with the same names as before.</span></span> <span data-ttu-id="4993c-121">Por ejemplo, `renderTreeFrame.Sequence` y `renderTreeFrame.ElementName`.</span><span class="sxs-lookup"><span data-stu-id="4993c-121">For example, `renderTreeFrame.Sequence` and `renderTreeFrame.ElementName`.</span></span>

<span data-ttu-id="4993c-122">Si el código precompilado anterior no se ha vuelto a compilar desde este cambio, es posible que inicie una excepción similar a *MissingFieldException: Campo no encontrado: "Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType"* .</span><span class="sxs-lookup"><span data-stu-id="4993c-122">If older precompiled code hasn't been recompiled since this change, it may throw an exception similar to *MissingFieldException: Field not found: 'Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType'*.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="4993c-123">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="4993c-123">Reason for change</span></span>

<span data-ttu-id="4993c-124">Este cambio era necesario para implementar mejoras de rendimiento de alto impacto en la representación de componentes de Blazor en ASP.NET Core 5.0.</span><span class="sxs-lookup"><span data-stu-id="4993c-124">This change was necessary to implement high-impact performance improvements in Blazor component rendering in ASP.NET Core 5.0.</span></span> <span data-ttu-id="4993c-125">Se mantienen los mismos niveles de seguridad y encapsulación.</span><span class="sxs-lookup"><span data-stu-id="4993c-125">The same levels of safety and encapsulation are maintained.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="4993c-126">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="4993c-126">Recommended action</span></span>

<span data-ttu-id="4993c-127">A la mayoría de los desarrolladores de Blazor no les afectará este cambio.</span><span class="sxs-lookup"><span data-stu-id="4993c-127">Most Blazor developers are unaffected by this change.</span></span> <span data-ttu-id="4993c-128">Es más probable que el cambio afecte a los creadores de bibliotecas y paquetes, pero solo en determinadas ocasiones.</span><span class="sxs-lookup"><span data-stu-id="4993c-128">The change is more likely to affect library and package authors, but only in rare cases.</span></span> <span data-ttu-id="4993c-129">En concreto, si se desarrolla:</span><span class="sxs-lookup"><span data-stu-id="4993c-129">Specifically, if you're developing:</span></span>

* <span data-ttu-id="4993c-130">Una aplicación y se usa ASP.NET Core 3.x o se actualiza a 5.0 RC1 o una versión posterior, no es necesario cambiar el código propio.</span><span class="sxs-lookup"><span data-stu-id="4993c-130">An app and using ASP.NET Core 3.x or upgrading to 5.0 RC1 or later, you don't need to change your own code.</span></span> <span data-ttu-id="4993c-131">Pero si depende de una biblioteca actualizada para tener en cuenta este cambio, tendrá que actualizar a una versión más reciente de esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="4993c-131">However, if you depend on a library that upgraded to account for this change, then you need to update to a newer version of that library.</span></span>
* <span data-ttu-id="4993c-132">Una biblioteca y solo quiere admitir ASP.NET Core 5.0 RC1 o posterior, no es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="4993c-132">A library and want to support only ASP.NET Core 5.0 RC1 or later, no action is needed.</span></span> <span data-ttu-id="4993c-133">Solo tiene que asegurarse de que el archivo del proyecto declara un valor `<TargetFramework>` de `net5.0` o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="4993c-133">Just ensure that your project file declares a `<TargetFramework>` value of `net5.0` or a later version.</span></span>
* <span data-ttu-id="4993c-134">Una biblioteca y quiere admitir ASP.NET Core 3.x *y* 5.0, determine si el código lee miembros de `RenderTreeFrame`.</span><span class="sxs-lookup"><span data-stu-id="4993c-134">A library and want to support both ASP.NET Core 3.x *and* 5.0, determine whether your code reads any `RenderTreeFrame` members.</span></span> <span data-ttu-id="4993c-135">Por ejemplo, la evaluación de `someRenderTreeFrame.FrameType`.</span><span class="sxs-lookup"><span data-stu-id="4993c-135">For example, evaluating `someRenderTreeFrame.FrameType`.</span></span>
  * <span data-ttu-id="4993c-136">La mayoría de las bibliotecas no leerán miembros `RenderTreeFrame`, incluidas las que contienen componentes de `.razor`.</span><span class="sxs-lookup"><span data-stu-id="4993c-136">Most libraries won't read `RenderTreeFrame` members, including libraries that contain `.razor` components.</span></span> <span data-ttu-id="4993c-137">En este caso, no es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="4993c-137">In this case, no action is needed.</span></span>
  * <span data-ttu-id="4993c-138">Pero si la biblioteca lo hace, necesitará varios destinos para admitir `netstandard2.1` y `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="4993c-138">However, if your library does that, you'll need to multi-target to support both `netstandard2.1` and `net5.0`.</span></span> <span data-ttu-id="4993c-139">Aplique los cambios siguientes en el archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="4993c-139">Apply the following changes in your project file:</span></span>
    * <span data-ttu-id="4993c-140">Reemplace el elemento `<TargetFramework>` existente por `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>`.</span><span class="sxs-lookup"><span data-stu-id="4993c-140">Replace the existing `<TargetFramework>` element with `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>`.</span></span>
    * <span data-ttu-id="4993c-141">Use una referencia de paquete `Microsoft.AspNetCore.Components` condicional para tener en cuenta las dos versiones que quiera admitir.</span><span class="sxs-lookup"><span data-stu-id="4993c-141">Use a conditional `Microsoft.AspNetCore.Components` package reference to account for both versions you wish to support.</span></span> <span data-ttu-id="4993c-142">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4993c-142">For example:</span></span>

        ```xml
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="3.0.0" Condition="'$(TargetFramework)' == 'netstandard2.0'" />
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="5.0.0-rc.1.*" Condition="'$(TargetFramework)' != 'netstandard2.0'" />
        ```

<span data-ttu-id="4993c-143">Para una mayor aclaración, vea estas [diferencias en las que se muestra cómo @jsakamoto ya ha actualizado la biblioteca `Toolbelt.Blazor.HeadElement`](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51).</span><span class="sxs-lookup"><span data-stu-id="4993c-143">For further clarification, see this [diff showing how @jsakamoto already upgraded the `Toolbelt.Blazor.HeadElement` library](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="4993c-144">API afectadas</span><span class="sxs-lookup"><span data-stu-id="4993c-144">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame`

-->
