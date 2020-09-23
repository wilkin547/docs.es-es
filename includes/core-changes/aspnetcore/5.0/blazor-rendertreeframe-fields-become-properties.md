---
ms.openlocfilehash: edff55d540f08e8a9fd4d0687aaf6bd963ee3a84
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539529"
---
### <a name="blazor-rendertreeframe-readonly-public-fields-have-become-properties"></a><span data-ttu-id="503bf-101">Blazor: Los campos públicos RenderTreeFrame de solo lectura se han convertido en propiedades</span><span class="sxs-lookup"><span data-stu-id="503bf-101">Blazor: RenderTreeFrame readonly public fields have become properties</span></span>

<span data-ttu-id="503bf-102">En ASP.NET Core 3.0 y 3.1, la estructura <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> expone varios campos de `readonly public`, como <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType>, <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence> y otros.</span><span class="sxs-lookup"><span data-stu-id="503bf-102">In ASP.NET Core 3.0 and 3.1, the <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> struct exposed various `readonly public` fields, including <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType>, <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence>, and others.</span></span> <span data-ttu-id="503bf-103">En ASP.NET Core 5.0 RC1 y versiones posteriores, todos los campos de `readonly public` se han cambiado por propiedades `readonly public`.</span><span class="sxs-lookup"><span data-stu-id="503bf-103">In ASP.NET Core 5.0 RC1 and later versions, all the `readonly public` fields changed to `readonly public` properties.</span></span>

<span data-ttu-id="503bf-104">Este cambio no afectará a muchos desarrolladores porque:</span><span class="sxs-lookup"><span data-stu-id="503bf-104">This change won't affect many developers because:</span></span>

* <span data-ttu-id="503bf-105">Cualquier aplicación o biblioteca que simplemente use archivos `.razor` (o incluso llamadas a <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> manuales) para definir sus componentes no hará referencia directamente a este tipo.</span><span class="sxs-lookup"><span data-stu-id="503bf-105">Any app or library that simply uses `.razor` files (or even manual <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> calls) to define its components wouldn't be referencing this type directly.</span></span>
* <span data-ttu-id="503bf-106">El propio tipo `RenderTreeFrame` se considera un detalle de implementación; no está diseñado para usarlo fuera del marco.</span><span class="sxs-lookup"><span data-stu-id="503bf-106">The `RenderTreeFrame` type itself is regarded as an implementation detail, not intended for use outside of the framework.</span></span> <span data-ttu-id="503bf-107">En ASP.NET Core 3.0 y versiones posteriores se incluye un analizador que emite advertencias del compilador si el tipo se usa de forma directa.</span><span class="sxs-lookup"><span data-stu-id="503bf-107">ASP.NET Core 3.0 and later includes an analyzer that issues compiler warnings if the type is being used directly.</span></span>
* <span data-ttu-id="503bf-108">Incluso si hace referencia a `RenderTreeFrame` de forma directa, este cambio afectará a los binarios, no al código fuente.</span><span class="sxs-lookup"><span data-stu-id="503bf-108">Even if you reference `RenderTreeFrame` directly, this change is binary-breaking but not source-breaking.</span></span> <span data-ttu-id="503bf-109">Es decir, el código fuente existente se compilará y se comportará de manera correcta.</span><span class="sxs-lookup"><span data-stu-id="503bf-109">That is, your existing source code will compile and behave properly.</span></span> <span data-ttu-id="503bf-110">Solo se producirá una incidencia si se compila en un marco de trabajo de .NET Core 3.x y luego esos archivos binarios se ejecutan en .NET 5.0 RC1 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="503bf-110">You'll only encounter an issue if compiling against a .NET Core 3.x framework and then running those binaries against the .NET 5.0 RC1 and later framework.</span></span>

<span data-ttu-id="503bf-111">Para obtener información, vea la incidencia de GitHub [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727).</span><span class="sxs-lookup"><span data-stu-id="503bf-111">For discussion, see GitHub issue [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="503bf-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="503bf-112">Version introduced</span></span>

<span data-ttu-id="503bf-113">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="503bf-113">5.0 RC1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="503bf-114">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="503bf-114">Old behavior</span></span>

<span data-ttu-id="503bf-115">Los miembros públicos de `RenderTreeFrame` se definen como campos.</span><span class="sxs-lookup"><span data-stu-id="503bf-115">Public members on `RenderTreeFrame` are defined as fields.</span></span> <span data-ttu-id="503bf-116">Por ejemplo, `renderTreeFrame.Sequence` y `renderTreeFrame.ElementName`.</span><span class="sxs-lookup"><span data-stu-id="503bf-116">For example, `renderTreeFrame.Sequence` and `renderTreeFrame.ElementName`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="503bf-117">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="503bf-117">New behavior</span></span>

<span data-ttu-id="503bf-118">Los miembros públicos de `RenderTreeFrame` se definen como propiedades con los mismos nombres que antes.</span><span class="sxs-lookup"><span data-stu-id="503bf-118">Public members on `RenderTreeFrame` are defined as properties with the same names as before.</span></span> <span data-ttu-id="503bf-119">Por ejemplo, `renderTreeFrame.Sequence` y `renderTreeFrame.ElementName`.</span><span class="sxs-lookup"><span data-stu-id="503bf-119">For example, `renderTreeFrame.Sequence` and `renderTreeFrame.ElementName`.</span></span>

<span data-ttu-id="503bf-120">Si el código precompilado anterior no se ha vuelto a compilar desde este cambio, es posible que inicie una excepción similar a *MissingFieldException: Campo no encontrado: "Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType"* .</span><span class="sxs-lookup"><span data-stu-id="503bf-120">If older precompiled code hasn't been recompiled since this change, it may throw an exception similar to *MissingFieldException: Field not found: 'Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType'*.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="503bf-121">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="503bf-121">Reason for change</span></span>

<span data-ttu-id="503bf-122">Este cambio era necesario para implementar mejoras de rendimiento de alto impacto en la representación de componentes de Blazor en ASP.NET Core 5.0.</span><span class="sxs-lookup"><span data-stu-id="503bf-122">This change was necessary to implement high-impact performance improvements in Blazor component rendering in ASP.NET Core 5.0.</span></span> <span data-ttu-id="503bf-123">Se mantienen los mismos niveles de seguridad y encapsulación.</span><span class="sxs-lookup"><span data-stu-id="503bf-123">The same levels of safety and encapsulation are maintained.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="503bf-124">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="503bf-124">Recommended action</span></span>

<span data-ttu-id="503bf-125">A la mayoría de los desarrolladores de Blazor no les afectará este cambio.</span><span class="sxs-lookup"><span data-stu-id="503bf-125">Most Blazor developers are unaffected by this change.</span></span> <span data-ttu-id="503bf-126">Es más probable que el cambio afecte a los creadores de bibliotecas y paquetes, pero solo en determinadas ocasiones.</span><span class="sxs-lookup"><span data-stu-id="503bf-126">The change is more likely to affect library and package authors, but only in rare cases.</span></span> <span data-ttu-id="503bf-127">En concreto, si se desarrolla:</span><span class="sxs-lookup"><span data-stu-id="503bf-127">Specifically, if you're developing:</span></span>

* <span data-ttu-id="503bf-128">Una aplicación y se usa ASP.NET Core 3.x o se actualiza a 5.0 RC1 o una versión posterior, no es necesario cambiar el código propio.</span><span class="sxs-lookup"><span data-stu-id="503bf-128">An app and using ASP.NET Core 3.x or upgrading to 5.0 RC1 or later, you don't need to change your own code.</span></span> <span data-ttu-id="503bf-129">Pero si depende de una biblioteca actualizada para tener en cuenta este cambio, tendrá que actualizar a una versión más reciente de esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="503bf-129">However, if you depend on a library that upgraded to account for this change, then you need to update to a newer version of that library.</span></span>
* <span data-ttu-id="503bf-130">Una biblioteca y solo quiere admitir ASP.NET Core 5.0 RC1 o posterior, no es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="503bf-130">A library and want to support only ASP.NET Core 5.0 RC1 or later, no action is needed.</span></span> <span data-ttu-id="503bf-131">Solo tiene que asegurarse de que el archivo del proyecto declara un valor `<TargetFramework>` de `net5.0` o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="503bf-131">Just ensure that your project file declares a `<TargetFramework>` value of `net5.0` or a later version.</span></span>
* <span data-ttu-id="503bf-132">Una biblioteca y quiere admitir ASP.NET Core 3.x *y* 5.0, determine si el código lee miembros de `RenderTreeFrame`.</span><span class="sxs-lookup"><span data-stu-id="503bf-132">A library and want to support both ASP.NET Core 3.x *and* 5.0, determine whether your code reads any `RenderTreeFrame` members.</span></span> <span data-ttu-id="503bf-133">Por ejemplo, la evaluación de `someRenderTreeFrame.FrameType`.</span><span class="sxs-lookup"><span data-stu-id="503bf-133">For example, evaluating `someRenderTreeFrame.FrameType`.</span></span>
  * <span data-ttu-id="503bf-134">La mayoría de las bibliotecas no leerán miembros `RenderTreeFrame`, incluidas las que contienen componentes de `.razor`.</span><span class="sxs-lookup"><span data-stu-id="503bf-134">Most libraries won't read `RenderTreeFrame` members, including libraries that contain `.razor` components.</span></span> <span data-ttu-id="503bf-135">En este caso, no es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="503bf-135">In this case, no action is needed.</span></span>
  * <span data-ttu-id="503bf-136">Pero si la biblioteca lo hace, necesitará varios destinos para admitir `netstandard2.1` y `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="503bf-136">However, if your library does that, you'll need to multi-target to support both `netstandard2.1` and `net5.0`.</span></span> <span data-ttu-id="503bf-137">Aplique los cambios siguientes en el archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="503bf-137">Apply the following changes in your project file:</span></span>
    * <span data-ttu-id="503bf-138">Reemplace el elemento `<TargetFramework>` existente por `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>`.</span><span class="sxs-lookup"><span data-stu-id="503bf-138">Replace the existing `<TargetFramework>` element with `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>`.</span></span>
    * <span data-ttu-id="503bf-139">Use una referencia de paquete `Microsoft.AspNetCore.Components` condicional para tener en cuenta las dos versiones que quiera admitir.</span><span class="sxs-lookup"><span data-stu-id="503bf-139">Use a conditional `Microsoft.AspNetCore.Components` package reference to account for both versions you wish to support.</span></span> <span data-ttu-id="503bf-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="503bf-140">For example:</span></span>

        ```xml
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="3.0.0" Condition="'$(TargetFramework)' == 'netstandard2.0'" />
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="5.0.0-rc.1.*" Condition="'$(TargetFramework)' != 'netstandard2.0'" />
        ```

<span data-ttu-id="503bf-141">Para una mayor aclaración, vea estas [diferencias en las que se muestra cómo @jsakamoto ya ha actualizado la biblioteca `Toolbelt.Blazor.HeadElement`](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51).</span><span class="sxs-lookup"><span data-stu-id="503bf-141">For further clarification, see this [diff showing how @jsakamoto already upgraded the `Toolbelt.Blazor.HeadElement` library](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51).</span></span>

#### <a name="category"></a><span data-ttu-id="503bf-142">Categoría</span><span class="sxs-lookup"><span data-stu-id="503bf-142">Category</span></span>

<span data-ttu-id="503bf-143">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="503bf-143">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="503bf-144">API afectadas</span><span class="sxs-lookup"><span data-stu-id="503bf-144">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame`

-->
