---
ms.openlocfilehash: ca369c4e3f78648c6e8e0bcb5d54711d3009a769
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174273"
---
### <a name="blazor-insignificant-whitespace-trimmed-from-components-at-compile-time"></a><span data-ttu-id="e1095-101">Blazor: Espacio en blanco no significativo recortado de componentes en el tiempo de compilación</span><span class="sxs-lookup"><span data-stu-id="e1095-101">Blazor: Insignificant whitespace trimmed from components at compile time</span></span>

<span data-ttu-id="e1095-102">A partir de ASP.NET Core 5.0, versión preliminar 7, el compilador de Razor omite el espacio en blanco no significativo de los componentes de Blazor (archivos de *.razor*) en el tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="e1095-102">Starting with ASP.NET Core 5.0 Preview 7, the Razor compiler omits insignificant whitespace in Blazor components (*.razor* files) at compile time.</span></span> <span data-ttu-id="e1095-103">Para obtener información, consulte el tema [dotnet/aspnetcore#23568](https://github.com/dotnet/aspnetcore/issues/23568).</span><span class="sxs-lookup"><span data-stu-id="e1095-103">For discussion, see issue [dotnet/aspnetcore#23568](https://github.com/dotnet/aspnetcore/issues/23568).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e1095-104">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="e1095-104">Version introduced</span></span>

<span data-ttu-id="e1095-105">5.0 (versión preliminar 7)</span><span class="sxs-lookup"><span data-stu-id="e1095-105">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e1095-106">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="e1095-106">Old behavior</span></span>

<span data-ttu-id="e1095-107">En las versiones 3.x de Blazor Server y Blazor WebAssembly, se respeta el espacio en blanco en el código fuente de un componente.</span><span class="sxs-lookup"><span data-stu-id="e1095-107">In 3.x versions of Blazor Server and Blazor WebAssembly, whitespace is honored in a component's source code.</span></span> <span data-ttu-id="e1095-108">Los nodos de texto de espacio en blanco solo se representan en el Document Object Model (DOM) del explorador aunque no haya ningún efecto visual.</span><span class="sxs-lookup"><span data-stu-id="e1095-108">Whitespace-only text nodes render in the browser's Document Object Model (DOM) even when there's no visual effect.</span></span>

<span data-ttu-id="e1095-109">Considere el siguiente código de componente Blazor:</span><span class="sxs-lookup"><span data-stu-id="e1095-109">Consider the following Blazor component code:</span></span>

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

<span data-ttu-id="e1095-110">En el ejemplo anterior se representan dos nodos de espacios en blanco:</span><span class="sxs-lookup"><span data-stu-id="e1095-110">The preceding example renders two whitespace nodes:</span></span>

* <span data-ttu-id="e1095-111">Fuera del bloque de código `@foreach`.</span><span class="sxs-lookup"><span data-stu-id="e1095-111">Outside of the `@foreach` code block.</span></span>
* <span data-ttu-id="e1095-112">Alrededor del elemento `<li>`.</span><span class="sxs-lookup"><span data-stu-id="e1095-112">Around the `<li>` element.</span></span>
* <span data-ttu-id="e1095-113">Alrededor de la salida de `@item.Text`.</span><span class="sxs-lookup"><span data-stu-id="e1095-113">Around the `@item.Text` output.</span></span>

<span data-ttu-id="e1095-114">Una lista que contiene 100 elementos da como resultado 402 nodos de espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="e1095-114">A list containing 100 items results in 402 whitespace nodes.</span></span> <span data-ttu-id="e1095-115">Esta cantidad es más de la mitad de todos los nodos representados, aunque ninguno de los nodos de espacios en blanco afecte visualmente a la salida representada.</span><span class="sxs-lookup"><span data-stu-id="e1095-115">That's over half of all nodes rendered, even though none of the whitespace nodes visually affect the rendered output.</span></span>

<span data-ttu-id="e1095-116">Al representar HTML estático para componentes, no se conservaba el espacio en blanco dentro de una etiqueta.</span><span class="sxs-lookup"><span data-stu-id="e1095-116">When rendering static HTML for components, whitespace inside a tag wasn't preserved.</span></span> <span data-ttu-id="e1095-117">Por ejemplo, vea el origen del siguiente componente:</span><span class="sxs-lookup"><span data-stu-id="e1095-117">For example, view the source of the following component:</span></span>

```razor
<foo        bar="baz"     />
```

<span data-ttu-id="e1095-118">No se conserva el espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="e1095-118">Whitespace isn't preserved.</span></span> <span data-ttu-id="e1095-119">La salida representada previamente es:</span><span class="sxs-lookup"><span data-stu-id="e1095-119">The pre-rendered output is:</span></span>

```razor
<foo bar="baz" />
```

#### <a name="new-behavior"></a><span data-ttu-id="e1095-120">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="e1095-120">New behavior</span></span>

<span data-ttu-id="e1095-121">A menos que se use la Directiva de `@preservewhitespace` con `true` de valor, se quitan los nodos de espacios en blanco si:</span><span class="sxs-lookup"><span data-stu-id="e1095-121">Unless the `@preservewhitespace` directive is used with value `true`, whitespace nodes are removed if they:</span></span>

* <span data-ttu-id="e1095-122">Están delante o detrás de un elemento.</span><span class="sxs-lookup"><span data-stu-id="e1095-122">Are leading or trailing within an element.</span></span>
* <span data-ttu-id="e1095-123">Están delante o detrás de un parámetro `RenderFragment`.</span><span class="sxs-lookup"><span data-stu-id="e1095-123">Are leading or trailing within a `RenderFragment` parameter.</span></span> <span data-ttu-id="e1095-124">Por ejemplo, el contenido secundario se pasa a otro componente.</span><span class="sxs-lookup"><span data-stu-id="e1095-124">For example, child content being passed to another component.</span></span>
* <span data-ttu-id="e1095-125">Precede o sigue a un bloque de código de C#, como `@if` y `@foreach`.</span><span class="sxs-lookup"><span data-stu-id="e1095-125">Precede or follow a C# code block such as `@if` and `@foreach`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e1095-126">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="e1095-126">Reason for change</span></span>

<span data-ttu-id="e1095-127">Un objetivo para Blazor en ASP.NET Core 5,0 es mejorar el rendimiento de la representación y la diferenciación.</span><span class="sxs-lookup"><span data-stu-id="e1095-127">A goal for Blazor in ASP.NET Core 5.0 is to improve the performance of rendering and diffing.</span></span> <span data-ttu-id="e1095-128">Los nodos de árbol de espacios en blanco no significativos consumieron hasta un 40 % del tiempo de representación en las pruebas comparativas.</span><span class="sxs-lookup"><span data-stu-id="e1095-128">Insignificant whitespace tree nodes consumed up to 40 percent of the rendering time in benchmarks.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e1095-129">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="e1095-129">Recommended action</span></span>

<span data-ttu-id="e1095-130">En la mayoría de los casos, el diseño visual del componente representado no se ve afectado.</span><span class="sxs-lookup"><span data-stu-id="e1095-130">In most cases, the visual layout of the rendered component is unaffected.</span></span> <span data-ttu-id="e1095-131">Sin embargo, la eliminación de espacios en blanco puede afectar a la salida representada cuando se usa una regla de CSS como `white-space: pre`.</span><span class="sxs-lookup"><span data-stu-id="e1095-131">However, the whitespace removal might affect the rendered output when using a CSS rule like `white-space: pre`.</span></span> <span data-ttu-id="e1095-132">Para deshabilitar esta optimización de rendimiento y conservar el espacio en blanco, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="e1095-132">To disable this performance optimization and preserve the whitespace, take one of the following actions:</span></span>

* <span data-ttu-id="e1095-133">Agregue la directiva `@preservewhitespace true` en la parte superior del archivo *.razor* para aplicar las preferencias a un componente específico.</span><span class="sxs-lookup"><span data-stu-id="e1095-133">Add the `@preservewhitespace true` directive at the top of the *.razor* file to apply the preference to a specific component.</span></span>
* <span data-ttu-id="e1095-134">Agregue la directiva `@preservewhitespace true` dentro de un archivo *_Imports.razor* para aplicar la preferencia a un subdirectorio completo o a todo el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e1095-134">Add the `@preservewhitespace true` directive inside an *_Imports.razor* file to apply the preference to an entire subdirectory or the entire project.</span></span>

<span data-ttu-id="e1095-135">En la mayoría de los casos, no se requiere ninguna acción, ya que las aplicaciones normalmente seguirán funcionando con normalidad (pero más rápido).</span><span class="sxs-lookup"><span data-stu-id="e1095-135">In most cases, no action is required, as applications will typically continue to behave normally (but faster).</span></span> <span data-ttu-id="e1095-136">Si la eliminación de espacios en blanco provoca problemas en un componente determinado, use `@preservewhitespace true` de ese componente para deshabilitar esta optimización.</span><span class="sxs-lookup"><span data-stu-id="e1095-136">If the whitespace stripping causes any problems for a particular component, use `@preservewhitespace true` in that component to disable this optimization.</span></span>

#### <a name="category"></a><span data-ttu-id="e1095-137">Categoría</span><span class="sxs-lookup"><span data-stu-id="e1095-137">Category</span></span>

<span data-ttu-id="e1095-138">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e1095-138">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e1095-139">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e1095-139">Affected APIs</span></span>

<span data-ttu-id="e1095-140">None</span><span class="sxs-lookup"><span data-stu-id="e1095-140">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
