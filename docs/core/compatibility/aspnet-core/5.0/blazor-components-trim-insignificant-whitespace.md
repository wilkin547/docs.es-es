---
title: 'Cambio importante: Blazor: Espacio en blanco no significativo recortado de componentes en el tiempo de compilación'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Blazor: Espacio en blanco no significativo recortado de componentes en el tiempo de compilación'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 92a961bb377bedd27b793c77d4be31ce52179ee2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760254"
---
# <a name="blazor-insignificant-whitespace-trimmed-from-components-at-compile-time"></a><span data-ttu-id="1b23b-103">Blazor: Espacio en blanco no significativo recortado de componentes en el tiempo de compilación</span><span class="sxs-lookup"><span data-stu-id="1b23b-103">Blazor: Insignificant whitespace trimmed from components at compile time</span></span>

<span data-ttu-id="1b23b-104">A partir de ASP.NET Core 5.0, versión preliminar 7, el compilador de Razor omite el espacio en blanco no significativo de los componentes de Blazor (archivos de *.razor*) en el tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="1b23b-104">Starting with ASP.NET Core 5.0 Preview 7, the Razor compiler omits insignificant whitespace in Blazor components (*.razor* files) at compile time.</span></span> <span data-ttu-id="1b23b-105">Para obtener información, consulte el tema [dotnet/aspnetcore#23568](https://github.com/dotnet/aspnetcore/issues/23568).</span><span class="sxs-lookup"><span data-stu-id="1b23b-105">For discussion, see issue [dotnet/aspnetcore#23568](https://github.com/dotnet/aspnetcore/issues/23568).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="1b23b-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1b23b-106">Version introduced</span></span>

<span data-ttu-id="1b23b-107">5.0 (versión preliminar 7)</span><span class="sxs-lookup"><span data-stu-id="1b23b-107">5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="1b23b-108">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="1b23b-108">Old behavior</span></span>

<span data-ttu-id="1b23b-109">En las versiones 3.x de Blazor Server y Blazor WebAssembly, se respeta el espacio en blanco en el código fuente de un componente.</span><span class="sxs-lookup"><span data-stu-id="1b23b-109">In 3.x versions of Blazor Server and Blazor WebAssembly, whitespace is honored in a component's source code.</span></span> <span data-ttu-id="1b23b-110">Los nodos de texto de espacio en blanco solo se representan en el Document Object Model (DOM) del explorador aunque no haya ningún efecto visual.</span><span class="sxs-lookup"><span data-stu-id="1b23b-110">Whitespace-only text nodes render in the browser's Document Object Model (DOM) even when there's no visual effect.</span></span>

<span data-ttu-id="1b23b-111">Considere el siguiente código de componente Blazor:</span><span class="sxs-lookup"><span data-stu-id="1b23b-111">Consider the following Blazor component code:</span></span>

```razor
<ul>
    @foreach (var item in Items)
    {
        <li>
            @item.Text
        </li>
    }
</ul>
```

<span data-ttu-id="1b23b-112">En el ejemplo anterior se representan dos nodos de espacios en blanco:</span><span class="sxs-lookup"><span data-stu-id="1b23b-112">The preceding example renders two whitespace nodes:</span></span>

* <span data-ttu-id="1b23b-113">Fuera del bloque de código `@foreach`.</span><span class="sxs-lookup"><span data-stu-id="1b23b-113">Outside of the `@foreach` code block.</span></span>
* <span data-ttu-id="1b23b-114">Alrededor del elemento `<li>`.</span><span class="sxs-lookup"><span data-stu-id="1b23b-114">Around the `<li>` element.</span></span>
* <span data-ttu-id="1b23b-115">Alrededor de la salida de `@item.Text`.</span><span class="sxs-lookup"><span data-stu-id="1b23b-115">Around the `@item.Text` output.</span></span>

<span data-ttu-id="1b23b-116">Una lista que contiene 100 elementos da como resultado 402 nodos de espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="1b23b-116">A list containing 100 items results in 402 whitespace nodes.</span></span> <span data-ttu-id="1b23b-117">Esta cantidad es más de la mitad de todos los nodos representados, aunque ninguno de los nodos de espacios en blanco afecte visualmente a la salida representada.</span><span class="sxs-lookup"><span data-stu-id="1b23b-117">That's over half of all nodes rendered, even though none of the whitespace nodes visually affect the rendered output.</span></span>

<span data-ttu-id="1b23b-118">Al representar HTML estático para componentes, no se conservaba el espacio en blanco dentro de una etiqueta.</span><span class="sxs-lookup"><span data-stu-id="1b23b-118">When rendering static HTML for components, whitespace inside a tag wasn't preserved.</span></span> <span data-ttu-id="1b23b-119">Por ejemplo, vea el origen del siguiente componente:</span><span class="sxs-lookup"><span data-stu-id="1b23b-119">For example, view the source of the following component:</span></span>

```razor
<foo        bar="baz"     />
```

<span data-ttu-id="1b23b-120">No se conserva el espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="1b23b-120">Whitespace isn't preserved.</span></span> <span data-ttu-id="1b23b-121">La salida representada previamente es:</span><span class="sxs-lookup"><span data-stu-id="1b23b-121">The pre-rendered output is:</span></span>

```razor
<foo bar="baz" />
```

## <a name="new-behavior"></a><span data-ttu-id="1b23b-122">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="1b23b-122">New behavior</span></span>

<span data-ttu-id="1b23b-123">A menos que se use la Directiva de `@preservewhitespace` con `true` de valor, se quitan los nodos de espacios en blanco si:</span><span class="sxs-lookup"><span data-stu-id="1b23b-123">Unless the `@preservewhitespace` directive is used with value `true`, whitespace nodes are removed if they:</span></span>

* <span data-ttu-id="1b23b-124">Están delante o detrás de un elemento.</span><span class="sxs-lookup"><span data-stu-id="1b23b-124">Are leading or trailing within an element.</span></span>
* <span data-ttu-id="1b23b-125">Están delante o detrás de un parámetro `RenderFragment`.</span><span class="sxs-lookup"><span data-stu-id="1b23b-125">Are leading or trailing within a `RenderFragment` parameter.</span></span> <span data-ttu-id="1b23b-126">Por ejemplo, el contenido secundario se pasa a otro componente.</span><span class="sxs-lookup"><span data-stu-id="1b23b-126">For example, child content being passed to another component.</span></span>
* <span data-ttu-id="1b23b-127">Precede o sigue a un bloque de código de C#, como `@if` y `@foreach`.</span><span class="sxs-lookup"><span data-stu-id="1b23b-127">Precede or follow a C# code block such as `@if` and `@foreach`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="1b23b-128">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="1b23b-128">Reason for change</span></span>

<span data-ttu-id="1b23b-129">Un objetivo para Blazor en ASP.NET Core 5,0 es mejorar el rendimiento de la representación y la diferenciación.</span><span class="sxs-lookup"><span data-stu-id="1b23b-129">A goal for Blazor in ASP.NET Core 5.0 is to improve the performance of rendering and diffing.</span></span> <span data-ttu-id="1b23b-130">Los nodos de árbol de espacios en blanco no significativos consumieron hasta un 40 % del tiempo de representación en las pruebas comparativas.</span><span class="sxs-lookup"><span data-stu-id="1b23b-130">Insignificant whitespace tree nodes consumed up to 40 percent of the rendering time in benchmarks.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="1b23b-131">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="1b23b-131">Recommended action</span></span>

<span data-ttu-id="1b23b-132">En la mayoría de los casos, el diseño visual del componente representado no se ve afectado.</span><span class="sxs-lookup"><span data-stu-id="1b23b-132">In most cases, the visual layout of the rendered component is unaffected.</span></span> <span data-ttu-id="1b23b-133">Sin embargo, la eliminación de espacios en blanco puede afectar a la salida representada cuando se usa una regla de CSS como `white-space: pre`.</span><span class="sxs-lookup"><span data-stu-id="1b23b-133">However, the whitespace removal might affect the rendered output when using a CSS rule like `white-space: pre`.</span></span> <span data-ttu-id="1b23b-134">Para deshabilitar esta optimización de rendimiento y conservar el espacio en blanco, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="1b23b-134">To disable this performance optimization and preserve the whitespace, take one of the following actions:</span></span>

* <span data-ttu-id="1b23b-135">Agregue la directiva `@preservewhitespace true` en la parte superior del archivo *.razor* para aplicar las preferencias a un componente específico.</span><span class="sxs-lookup"><span data-stu-id="1b23b-135">Add the `@preservewhitespace true` directive at the top of the *.razor* file to apply the preference to a specific component.</span></span>
* <span data-ttu-id="1b23b-136">Agregue la directiva `@preservewhitespace true` dentro de un archivo *_Imports.razor* para aplicar la preferencia a un subdirectorio completo o a todo el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1b23b-136">Add the `@preservewhitespace true` directive inside an *_Imports.razor* file to apply the preference to an entire subdirectory or the entire project.</span></span>

<span data-ttu-id="1b23b-137">En la mayoría de los casos, no se requiere ninguna acción, ya que las aplicaciones normalmente seguirán funcionando con normalidad (pero más rápido).</span><span class="sxs-lookup"><span data-stu-id="1b23b-137">In most cases, no action is required, as applications will typically continue to behave normally (but faster).</span></span> <span data-ttu-id="1b23b-138">Si la eliminación de espacios en blanco provoca problemas en un componente determinado, use `@preservewhitespace true` de ese componente para deshabilitar esta optimización.</span><span class="sxs-lookup"><span data-stu-id="1b23b-138">If the whitespace stripping causes any problems for a particular component, use `@preservewhitespace true` in that component to disable this optimization.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="1b23b-139">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1b23b-139">Affected APIs</span></span>

<span data-ttu-id="1b23b-140">None</span><span class="sxs-lookup"><span data-stu-id="1b23b-140">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
