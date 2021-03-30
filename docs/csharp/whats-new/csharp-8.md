---
title: 'Novedades de C# 8.0: Guía de C#'
description: Obtenga información general sobre las nuevas características disponibles en C# 8.0.
ms.date: 04/07/2020
ms.openlocfilehash: 7e2e484b4eacf8fdbef61a600409fa561dd34cb3
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104876076"
---
# <a name="whats-new-in-c-80"></a><span data-ttu-id="be843-103">Novedades de C# 8.0</span><span class="sxs-lookup"><span data-stu-id="be843-103">What's new in C# 8.0</span></span>

<span data-ttu-id="be843-104">C# 8.0 agrega las siguientes características y mejoras al lenguaje C#:</span><span class="sxs-lookup"><span data-stu-id="be843-104">C# 8.0 adds the following features and enhancements to the C# language:</span></span>

- [<span data-ttu-id="be843-105">Miembros de solo lectura</span><span class="sxs-lookup"><span data-stu-id="be843-105">Readonly members</span></span>](#readonly-members)
- [<span data-ttu-id="be843-106">Métodos de interfaz predeterminados</span><span class="sxs-lookup"><span data-stu-id="be843-106">Default interface methods</span></span>](#default-interface-methods)
- <span data-ttu-id="be843-107">[Mejoras de coincidencia de patrones](#more-patterns-in-more-places):</span><span class="sxs-lookup"><span data-stu-id="be843-107">[Pattern matching enhancements](#more-patterns-in-more-places):</span></span>
  - [<span data-ttu-id="be843-108">Expresiones switch</span><span class="sxs-lookup"><span data-stu-id="be843-108">Switch expressions</span></span>](#switch-expressions)
  - [<span data-ttu-id="be843-109">Patrones de propiedades</span><span class="sxs-lookup"><span data-stu-id="be843-109">Property patterns</span></span>](#property-patterns)
  - [<span data-ttu-id="be843-110">Patrones de tupla</span><span class="sxs-lookup"><span data-stu-id="be843-110">Tuple patterns</span></span>](#tuple-patterns)
  - [<span data-ttu-id="be843-111">Patrones posicionales</span><span class="sxs-lookup"><span data-stu-id="be843-111">Positional patterns</span></span>](#positional-patterns)
- [<span data-ttu-id="be843-112">Declaraciones using</span><span class="sxs-lookup"><span data-stu-id="be843-112">Using declarations</span></span>](#using-declarations)
- [<span data-ttu-id="be843-113">Funciones locales estáticas</span><span class="sxs-lookup"><span data-stu-id="be843-113">Static local functions</span></span>](#static-local-functions)
- [<span data-ttu-id="be843-114">Estructuras ref descartables</span><span class="sxs-lookup"><span data-stu-id="be843-114">Disposable ref structs</span></span>](#disposable-ref-structs)
- [<span data-ttu-id="be843-115">Tipos de referencia que aceptan valores null</span><span class="sxs-lookup"><span data-stu-id="be843-115">Nullable reference types</span></span>](#nullable-reference-types)
- [<span data-ttu-id="be843-116">Secuencias asincrónicas</span><span class="sxs-lookup"><span data-stu-id="be843-116">Asynchronous streams</span></span>](#asynchronous-streams)
- [<span data-ttu-id="be843-117">Asincrónica descartable</span><span class="sxs-lookup"><span data-stu-id="be843-117">Asynchronous disposable</span></span>](#asynchronous-disposable)
- [<span data-ttu-id="be843-118">Índices y rangos</span><span class="sxs-lookup"><span data-stu-id="be843-118">Indices and ranges</span></span>](#indices-and-ranges)
- [<span data-ttu-id="be843-119">Asignación de uso combinado de NULL</span><span class="sxs-lookup"><span data-stu-id="be843-119">Null-coalescing assignment</span></span>](#null-coalescing-assignment)
- [<span data-ttu-id="be843-120">Tipos construidos no administrados</span><span class="sxs-lookup"><span data-stu-id="be843-120">Unmanaged constructed types</span></span>](#unmanaged-constructed-types)
- [<span data-ttu-id="be843-121">Stackalloc en expresiones anidadas</span><span class="sxs-lookup"><span data-stu-id="be843-121">Stackalloc in nested expressions</span></span>](#stackalloc-in-nested-expressions)
- [<span data-ttu-id="be843-122">Mejora de las cadenas textuales interpoladas</span><span class="sxs-lookup"><span data-stu-id="be843-122">Enhancement of interpolated verbatim strings</span></span>](#enhancement-of-interpolated-verbatim-strings)

<span data-ttu-id="be843-123">C# 8.0 se admite en **.NET Core 3.x** y **.NET Standard 2.1**.</span><span class="sxs-lookup"><span data-stu-id="be843-123">C# 8.0 is supported on **.NET Core 3.x** and **.NET Standard 2.1**.</span></span> <span data-ttu-id="be843-124">Para obtener más información, vea [Control de versiones del lenguaje C#](../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="be843-124">For more information, see [C# language versioning](../language-reference/configure-language-version.md).</span></span>

<span data-ttu-id="be843-125">En el resto de este artículo se describen brevemente estas características.</span><span class="sxs-lookup"><span data-stu-id="be843-125">The remainder of this article briefly describes these features.</span></span> <span data-ttu-id="be843-126">Cuando hay disponibles artículos detallados, se proporcionan vínculos a esos tutoriales e introducciones.</span><span class="sxs-lookup"><span data-stu-id="be843-126">Where in-depth articles are available, links to those tutorials and overviews are provided.</span></span> <span data-ttu-id="be843-127">Puede explorar estas características en su entorno mediante la herramienta global `dotnet try`:</span><span class="sxs-lookup"><span data-stu-id="be843-127">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="be843-128">Instale la herramienta global [dotnet-try](https://github.com/dotnet/try/blob/main/DotNetTryLocal.md).</span><span class="sxs-lookup"><span data-stu-id="be843-128">Install the [dotnet-try](https://github.com/dotnet/try/blob/main/DotNetTryLocal.md) global tool.</span></span>
1. <span data-ttu-id="be843-129">Clone el repositorio [dotnet/try-samples](https://github.com/dotnet/try-samples).</span><span class="sxs-lookup"><span data-stu-id="be843-129">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="be843-130">Establezca el directorio actual en el subdirectorio *csharp8* para el repositorio *try-samples*.</span><span class="sxs-lookup"><span data-stu-id="be843-130">Set the current directory to the *csharp8* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="be843-131">Ejecute `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="be843-131">Run `dotnet try`.</span></span>

## <a name="readonly-members"></a><span data-ttu-id="be843-132">Miembros de solo lectura</span><span class="sxs-lookup"><span data-stu-id="be843-132">Readonly members</span></span>

<span data-ttu-id="be843-133">Puede aplicar el modificador `readonly` a los miembros de una estructura.</span><span class="sxs-lookup"><span data-stu-id="be843-133">You can apply the `readonly` modifier to members of a struct.</span></span> <span data-ttu-id="be843-134">Indica que el miembro no modifica el estado.</span><span class="sxs-lookup"><span data-stu-id="be843-134">It indicates that the member doesn't modify state.</span></span> <span data-ttu-id="be843-135">Resulta más pormenorizado que aplicar el modificador `readonly` a una declaración `struct`.</span><span class="sxs-lookup"><span data-stu-id="be843-135">It's more granular than applying the `readonly` modifier to a `struct` declaration.</span></span>  <span data-ttu-id="be843-136">Tenga en cuenta el siguiente struct mutable:</span><span class="sxs-lookup"><span data-stu-id="be843-136">Consider the following mutable struct:</span></span>

```csharp
public struct Point
{
    public double X { get; set; }
    public double Y { get; set; }
    public double Distance => Math.Sqrt(X * X + Y * Y);

    public override string ToString() =>
        $"({X}, {Y}) is {Distance} from the origin";
}
```

<span data-ttu-id="be843-137">Al igual que la mayoría de las estructuras, el método `ToString()` no modifica el estado.</span><span class="sxs-lookup"><span data-stu-id="be843-137">Like most structs, the `ToString()` method doesn't modify state.</span></span> <span data-ttu-id="be843-138">Para indicar eso, podría agregar el modificador `readonly` a la declaración de `ToString()`:</span><span class="sxs-lookup"><span data-stu-id="be843-138">You could indicate that by adding the `readonly` modifier to the declaration of `ToString()`:</span></span>

```csharp
public readonly override string ToString() =>
    $"({X}, {Y}) is {Distance} from the origin";
```

<span data-ttu-id="be843-139">El cambio anterior genera una advertencia del compilador, porque `ToString` accede a la propiedad `Distance`, que no está marcada como `readonly`:</span><span class="sxs-lookup"><span data-stu-id="be843-139">The preceding change generates a compiler warning, because `ToString` accesses the `Distance` property, which isn't marked `readonly`:</span></span>

```console
warning CS8656: Call to non-readonly member 'Point.Distance.get' from a 'readonly' member results in an implicit copy of 'this'
```

<span data-ttu-id="be843-140">El compilador le advierte cuando es necesario crear una copia defensiva.</span><span class="sxs-lookup"><span data-stu-id="be843-140">The compiler warns you when it needs to create a defensive copy.</span></span>  <span data-ttu-id="be843-141">La propiedad `Distance` no cambia el estado, por lo que puede corregir esta advertencia si agrega el modificador `readonly` a la declaración:</span><span class="sxs-lookup"><span data-stu-id="be843-141">The `Distance` property doesn't change state, so you can fix this warning by adding the `readonly` modifier to the declaration:</span></span>

```csharp
public readonly double Distance => Math.Sqrt(X * X + Y * Y);
```

<span data-ttu-id="be843-142">Tenga en cuenta que el modificador `readonly` es necesario en una propiedad de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="be843-142">Notice that the `readonly` modifier is necessary on a read-only property.</span></span> <span data-ttu-id="be843-143">El compilador no presupone que los descriptores de acceso `get` no modifican el estado; debe declarar `readonly` explícitamente.</span><span class="sxs-lookup"><span data-stu-id="be843-143">The compiler doesn't assume `get` accessors don't modify state; you must declare `readonly` explicitly.</span></span> <span data-ttu-id="be843-144">Las propiedades implementadas automáticamente son una excepción; el compilador tratará todos los captadores implementados automáticamente como `readonly`, por lo que aquí no es necesario agregar el modificador `readonly` a las propiedades `X` e `Y`.</span><span class="sxs-lookup"><span data-stu-id="be843-144">Auto-implemented properties are an exception; the compiler will treat all auto-implemented getters as `readonly`, so here there's no need to add the `readonly` modifier to the `X` and `Y` properties.</span></span>

<span data-ttu-id="be843-145">El compilador aplica la regla por la que los miembros `readonly` no modifican el estado.</span><span class="sxs-lookup"><span data-stu-id="be843-145">The compiler does enforce the rule that `readonly` members don't modify state.</span></span> <span data-ttu-id="be843-146">El método siguiente no se compilará a menos que se quite el modificador `readonly`:</span><span class="sxs-lookup"><span data-stu-id="be843-146">The following method won't compile unless you remove the `readonly` modifier:</span></span>

```csharp
public readonly void Translate(int xOffset, int yOffset)
{
    X += xOffset;
    Y += yOffset;
}
```

<span data-ttu-id="be843-147">Esta característica permite especificar la intención del diseño para que el compilador pueda aplicarla, y realizar optimizaciones basadas en dicha intención.</span><span class="sxs-lookup"><span data-stu-id="be843-147">This feature lets you specify your design intent so the compiler can enforce it, and make optimizations based on that intent.</span></span>

<span data-ttu-id="be843-148">Para obtener más información, vea la sección [Miembros de instancia `readonly`](../language-reference/builtin-types/struct.md#readonly-instance-members) del artículo [Tipos de estructura](../language-reference/builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="be843-148">For more information, see the [`readonly` instance members](../language-reference/builtin-types/struct.md#readonly-instance-members) section of the [Structure types](../language-reference/builtin-types/struct.md) article.</span></span>

## <a name="default-interface-methods"></a><span data-ttu-id="be843-149">Métodos de interfaz predeterminados</span><span class="sxs-lookup"><span data-stu-id="be843-149">Default interface methods</span></span>

<span data-ttu-id="be843-150">Ahora puede agregar miembros a interfaces y proporcionar una implementación de esos miembros.</span><span class="sxs-lookup"><span data-stu-id="be843-150">You can now add members to interfaces and provide an implementation for those members.</span></span> <span data-ttu-id="be843-151">Esta característica del lenguaje permite que los creadores de API agreguen métodos a una interfaz en versiones posteriores sin interrumpir la compatibilidad binaria o de origen con implementaciones existentes de dicha interfaz.</span><span class="sxs-lookup"><span data-stu-id="be843-151">This language feature enables API authors to add methods to an interface in later versions without breaking source or binary compatibility with existing implementations of that interface.</span></span> <span data-ttu-id="be843-152">Las implementaciones existentes *heredan* la implementación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="be843-152">Existing implementations *inherit* the default implementation.</span></span> <span data-ttu-id="be843-153">Esta característica también permite que C# interopere con las API que tienen como destino Android o Swift, que admiten características similares.</span><span class="sxs-lookup"><span data-stu-id="be843-153">This feature also enables C# to interoperate with APIs that target Android or Swift, which support similar features.</span></span> <span data-ttu-id="be843-154">Los métodos de interfaz predeterminados también permiten escenarios similares a una característica del lenguaje de "rasgos".</span><span class="sxs-lookup"><span data-stu-id="be843-154">Default interface methods also enable scenarios similar to a "traits" language feature.</span></span>

<span data-ttu-id="be843-155">Los métodos de interfaz predeterminados afectan a muchos escenarios y elementos del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="be843-155">Default interface methods affect many scenarios and language elements.</span></span> <span data-ttu-id="be843-156">Nuestro primer tutorial abarca la [actualización de una interfaz con implementaciones predeterminadas](./tutorials/default-interface-methods-versions.md).</span><span class="sxs-lookup"><span data-stu-id="be843-156">Our first tutorial covers [updating an interface with default implementations](./tutorials/default-interface-methods-versions.md).</span></span>

## <a name="more-patterns-in-more-places"></a><span data-ttu-id="be843-157">Más patrones en más lugares</span><span class="sxs-lookup"><span data-stu-id="be843-157">More patterns in more places</span></span>

<span data-ttu-id="be843-158">La **coincidencia de patrones** ofrece herramientas que proporcionan funcionalidad dependiente de la forma entre tipos de datos relacionados pero diferentes.</span><span class="sxs-lookup"><span data-stu-id="be843-158">**Pattern matching** gives tools to provide shape-dependent functionality across related but different kinds of data.</span></span> <span data-ttu-id="be843-159">C# 7.0 introdujo la sintaxis de patrones de tipos y patrones de constantes mediante la expresión [`is`](../language-reference/keywords/is.md) y la instrucción [`switch`](../language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="be843-159">C# 7.0 introduced syntax for type patterns and constant patterns by using the [`is`](../language-reference/keywords/is.md) expression and the [`switch`](../language-reference/keywords/switch.md) statement.</span></span> <span data-ttu-id="be843-160">Estas características representaban los primeros pasos hacia el uso de paradigmas de programación donde los datos y la funcionalidad están separados.</span><span class="sxs-lookup"><span data-stu-id="be843-160">These features represented the first tentative steps toward supporting programming paradigms where data and functionality live apart.</span></span> <span data-ttu-id="be843-161">A medida que el sector se mueve hacia más microservicios y otras arquitecturas basadas en la nube, se necesitan otras herramientas de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="be843-161">As the industry moves toward more microservices and other cloud-based architectures, other language tools are needed.</span></span>

<span data-ttu-id="be843-162">C# 8.0 amplía este vocabulario para que pueda usar más expresiones de patrones en más lugares del código.</span><span class="sxs-lookup"><span data-stu-id="be843-162">C# 8.0 expands this vocabulary so you can use more pattern expressions in more places in your code.</span></span> <span data-ttu-id="be843-163">Cuando los datos y la funcionalidad estén separados, tenga en cuenta estas características.</span><span class="sxs-lookup"><span data-stu-id="be843-163">Consider these features when your data and functionality are separate.</span></span> <span data-ttu-id="be843-164">Cuando los algoritmos dependan de un hecho distinto del tipo de entorno de ejecución de un objeto, tenga en cuenta la coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="be843-164">Consider pattern matching when your algorithms depend on a fact other than the runtime type of an object.</span></span> <span data-ttu-id="be843-165">Estas técnicas ofrecen otra forma de expresar los diseños.</span><span class="sxs-lookup"><span data-stu-id="be843-165">These techniques provide another way to express designs.</span></span>

<span data-ttu-id="be843-166">Además de nuevos patrones en nuevos lugares C# 8.0 agrega **patrones recursivos**.</span><span class="sxs-lookup"><span data-stu-id="be843-166">In addition to new patterns in new places, C# 8.0 adds **recursive patterns**.</span></span> <span data-ttu-id="be843-167">El resultado de cualquier expresión de patrón es una expresión.</span><span class="sxs-lookup"><span data-stu-id="be843-167">The result of any pattern expression is an expression.</span></span> <span data-ttu-id="be843-168">Un patrón recursivo es simplemente una expresión de patrón aplicada a la salida de otra expresión de patrón.</span><span class="sxs-lookup"><span data-stu-id="be843-168">A recursive pattern is simply a pattern expression applied to the output of another pattern expression.</span></span>

### <a name="switch-expressions"></a><span data-ttu-id="be843-169">Expresiones switch</span><span class="sxs-lookup"><span data-stu-id="be843-169">Switch expressions</span></span>

<span data-ttu-id="be843-170">Con frecuencia, una instrucción [`switch`](../language-reference/keywords/switch.md) genera un valor en cada uno de sus bloques `case`.</span><span class="sxs-lookup"><span data-stu-id="be843-170">Often, a [`switch`](../language-reference/keywords/switch.md) statement produces a value in each of its `case` blocks.</span></span> <span data-ttu-id="be843-171">Las **expresiones switch** le permiten usar una sintaxis de expresiones más concisa.</span><span class="sxs-lookup"><span data-stu-id="be843-171">**Switch expressions** enable you to use more concise expression syntax.</span></span> <span data-ttu-id="be843-172">Hay menos palabras clave `case` y `break` repetitivas y menos llaves.</span><span class="sxs-lookup"><span data-stu-id="be843-172">There are fewer repetitive `case` and `break` keywords, and fewer curly braces.</span></span>  <span data-ttu-id="be843-173">Por ejemplo, considere la siguiente enumeración que muestra los colores del arco iris:</span><span class="sxs-lookup"><span data-stu-id="be843-173">As an example, consider the following enum that lists the colors of the rainbow:</span></span>

```csharp
public enum Rainbow
{
    Red,
    Orange,
    Yellow,
    Green,
    Blue,
    Indigo,
    Violet
}
```

<span data-ttu-id="be843-174">Si la aplicación definió un tipo `RGBColor` construido a partir de los componentes `R`, `G` y `B`, podría convertir un valor `Rainbow` a sus valores RGB con el método siguiente que contiene una expresión switch:</span><span class="sxs-lookup"><span data-stu-id="be843-174">If your application defined an `RGBColor` type that is constructed from the `R`, `G` and `B` components, you could convert a `Rainbow` value to its RGB values using the following method containing a switch expression:</span></span>

```csharp
public static RGBColor FromRainbow(Rainbow colorBand) =>
    colorBand switch
    {
        Rainbow.Red    => new RGBColor(0xFF, 0x00, 0x00),
        Rainbow.Orange => new RGBColor(0xFF, 0x7F, 0x00),
        Rainbow.Yellow => new RGBColor(0xFF, 0xFF, 0x00),
        Rainbow.Green  => new RGBColor(0x00, 0xFF, 0x00),
        Rainbow.Blue   => new RGBColor(0x00, 0x00, 0xFF),
        Rainbow.Indigo => new RGBColor(0x4B, 0x00, 0x82),
        Rainbow.Violet => new RGBColor(0x94, 0x00, 0xD3),
        _              => throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand)),
    };
```

<span data-ttu-id="be843-175">Aquí hay varias mejoras en la sintaxis:</span><span class="sxs-lookup"><span data-stu-id="be843-175">There are several syntax improvements here:</span></span>

- <span data-ttu-id="be843-176">La variable precede a la palabra clave `switch`.</span><span class="sxs-lookup"><span data-stu-id="be843-176">The variable comes before the `switch` keyword.</span></span> <span data-ttu-id="be843-177">El orden diferente permite distinguir fácilmente la expresión switch de la instrucción switch.</span><span class="sxs-lookup"><span data-stu-id="be843-177">The different order makes it visually easy to distinguish the switch expression from the switch statement.</span></span>
- <span data-ttu-id="be843-178">Los elementos `case` y `:` se reemplazan por `=>`.</span><span class="sxs-lookup"><span data-stu-id="be843-178">The `case` and `:` elements are replaced with `=>`.</span></span> <span data-ttu-id="be843-179">Es más concisa e intuitiva.</span><span class="sxs-lookup"><span data-stu-id="be843-179">It's more concise and intuitive.</span></span>
- <span data-ttu-id="be843-180">El caso `default` se reemplaza por un descarte `_`.</span><span class="sxs-lookup"><span data-stu-id="be843-180">The `default` case is replaced with a `_` discard.</span></span>
- <span data-ttu-id="be843-181">Los cuerpos son expresiones, no instrucciones.</span><span class="sxs-lookup"><span data-stu-id="be843-181">The bodies are expressions, not statements.</span></span>

<span data-ttu-id="be843-182">Compárelo con el código equivalente mediante la instrucción clásica `switch`:</span><span class="sxs-lookup"><span data-stu-id="be843-182">Contrast that with the equivalent code using the classic `switch` statement:</span></span>

```csharp
public static RGBColor FromRainbowClassic(Rainbow colorBand)
{
    switch (colorBand)
    {
        case Rainbow.Red:
            return new RGBColor(0xFF, 0x00, 0x00);
        case Rainbow.Orange:
            return new RGBColor(0xFF, 0x7F, 0x00);
        case Rainbow.Yellow:
            return new RGBColor(0xFF, 0xFF, 0x00);
        case Rainbow.Green:
            return new RGBColor(0x00, 0xFF, 0x00);
        case Rainbow.Blue:
            return new RGBColor(0x00, 0x00, 0xFF);
        case Rainbow.Indigo:
            return new RGBColor(0x4B, 0x00, 0x82);
        case Rainbow.Violet:
            return new RGBColor(0x94, 0x00, 0xD3);
        default:
            throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand));
    };
}
```

### <a name="property-patterns"></a><span data-ttu-id="be843-183">Patrones de propiedades</span><span class="sxs-lookup"><span data-stu-id="be843-183">Property patterns</span></span>

<span data-ttu-id="be843-184">El **patrón de propiedades** permite hallar la coincidencia con las propiedades del objeto examinado.</span><span class="sxs-lookup"><span data-stu-id="be843-184">The **property pattern** enables you to match on properties of the object examined.</span></span> <span data-ttu-id="be843-185">Considere un sitio de comercio electrónico que debe calcular los impuestos de ventas según la dirección del comprador.</span><span class="sxs-lookup"><span data-stu-id="be843-185">Consider an eCommerce site that must compute sales tax based on the buyer's address.</span></span> <span data-ttu-id="be843-186">Ese cálculo no es una responsabilidad fundamental de una clase `Address`.</span><span class="sxs-lookup"><span data-stu-id="be843-186">That computation isn't a core responsibility of an `Address` class.</span></span> <span data-ttu-id="be843-187">Cambiará con el tiempo, probablemente con más frecuencia que el formato de dirección.</span><span class="sxs-lookup"><span data-stu-id="be843-187">It will change over time, likely more often than address format changes.</span></span> <span data-ttu-id="be843-188">El importe de los impuestos de ventas depende de la propiedad `State` de la dirección.</span><span class="sxs-lookup"><span data-stu-id="be843-188">The amount of sales tax depends on the `State` property of the address.</span></span> <span data-ttu-id="be843-189">El método siguiente usa el patrón de propiedades para calcular los impuestos de ventas a partir de la dirección y el precio:</span><span class="sxs-lookup"><span data-stu-id="be843-189">The following method uses the property pattern to compute the sales tax from the address and the price:</span></span>

```csharp
public static decimal ComputeSalesTax(Address location, decimal salePrice) =>
    location switch
    {
        { State: "WA" } => salePrice * 0.06M,
        { State: "MN" } => salePrice * 0.075M,
        { State: "MI" } => salePrice * 0.05M,
        // other cases removed for brevity...
        _ => 0M
    };
```

<span data-ttu-id="be843-190">La coincidencia de patrones crea una sintaxis concisa para expresar este algoritmo.</span><span class="sxs-lookup"><span data-stu-id="be843-190">Pattern matching creates a concise syntax for expressing this algorithm.</span></span>

### <a name="tuple-patterns"></a><span data-ttu-id="be843-191">Patrones de tupla</span><span class="sxs-lookup"><span data-stu-id="be843-191">Tuple patterns</span></span>

<span data-ttu-id="be843-192">Algunos algoritmos dependen de varias entradas.</span><span class="sxs-lookup"><span data-stu-id="be843-192">Some algorithms depend on multiple inputs.</span></span> <span data-ttu-id="be843-193">Los **patrones de tupla** permiten hacer cambios en función de varios valores, expresados como una [tupla](../language-reference/builtin-types/value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="be843-193">**Tuple patterns** allow you to switch based on multiple values expressed as a [tuple](../language-reference/builtin-types/value-tuples.md).</span></span>  <span data-ttu-id="be843-194">El código siguiente muestra una expresión switch del juego *piedra, papel, tijeras*:</span><span class="sxs-lookup"><span data-stu-id="be843-194">The following code shows a switch expression for the game *rock, paper, scissors*:</span></span>

```csharp
public static string RockPaperScissors(string first, string second)
    => (first, second) switch
    {
        ("rock", "paper") => "rock is covered by paper. Paper wins.",
        ("rock", "scissors") => "rock breaks scissors. Rock wins.",
        ("paper", "rock") => "paper covers rock. Paper wins.",
        ("paper", "scissors") => "paper is cut by scissors. Scissors wins.",
        ("scissors", "rock") => "scissors is broken by rock. Rock wins.",
        ("scissors", "paper") => "scissors cuts paper. Scissors wins.",
        (_, _) => "tie"
    };
```

<span data-ttu-id="be843-195">Los mensajes indican el ganador.</span><span class="sxs-lookup"><span data-stu-id="be843-195">The messages indicate the winner.</span></span> <span data-ttu-id="be843-196">El caso de descarte representa las tres combinaciones de valores equivalentes, u otras entradas de texto.</span><span class="sxs-lookup"><span data-stu-id="be843-196">The discard case represents the three combinations for ties, or other text inputs.</span></span>

### <a name="positional-patterns"></a><span data-ttu-id="be843-197">Patrones posicionales</span><span class="sxs-lookup"><span data-stu-id="be843-197">Positional patterns</span></span>

<span data-ttu-id="be843-198">Algunos tipos incluyen un método `Deconstruct` que deconstruye sus propiedades en variables discretas.</span><span class="sxs-lookup"><span data-stu-id="be843-198">Some types include a `Deconstruct` method that deconstructs its properties into discrete variables.</span></span> <span data-ttu-id="be843-199">Cuando un método `Deconstruct` es accesible, puede usar **patrones posicionales** para inspeccionar las propiedades del objeto y usar esas propiedades en un patrón.</span><span class="sxs-lookup"><span data-stu-id="be843-199">When a `Deconstruct` method is accessible, you can use **positional patterns** to inspect properties of the object and use those properties for a pattern.</span></span>  <span data-ttu-id="be843-200">Tenga en cuenta la siguiente clase `Point` que incluye un método `Deconstruct` con el objetivo de crear variables discretas para `X` y `Y`:</span><span class="sxs-lookup"><span data-stu-id="be843-200">Consider the following `Point` class that includes a `Deconstruct` method to create discrete variables for `X` and `Y`:</span></span>

```csharp
public class Point
{
    public int X { get; }
    public int Y { get; }

    public Point(int x, int y) => (X, Y) = (x, y);

    public void Deconstruct(out int x, out int y) =>
        (x, y) = (X, Y);
}
```

<span data-ttu-id="be843-201">Además, tenga en cuenta la siguiente enumeración, que representa diversas posiciones de un cuadrante:</span><span class="sxs-lookup"><span data-stu-id="be843-201">Additionally, consider the following enum that represents various positions of a quadrant:</span></span>

```csharp
public enum Quadrant
{
    Unknown,
    Origin,
    One,
    Two,
    Three,
    Four,
    OnBorder
}
```

<span data-ttu-id="be843-202">El método siguiente usa el **patrón posicional** para extraer los valores de `x` y `y`.</span><span class="sxs-lookup"><span data-stu-id="be843-202">The following method uses the **positional pattern** to extract the values of `x` and `y`.</span></span> <span data-ttu-id="be843-203">A continuación, usa una cláusula `when` para determinar el valor `Quadrant` del punto:</span><span class="sxs-lookup"><span data-stu-id="be843-203">Then, it uses a `when` clause to determine the `Quadrant` of the point:</span></span>

```csharp
static Quadrant GetQuadrant(Point point) => point switch
{
    (0, 0) => Quadrant.Origin,
    var (x, y) when x > 0 && y > 0 => Quadrant.One,
    var (x, y) when x < 0 && y > 0 => Quadrant.Two,
    var (x, y) when x < 0 && y < 0 => Quadrant.Three,
    var (x, y) when x > 0 && y < 0 => Quadrant.Four,
    var (_, _) => Quadrant.OnBorder,
    _ => Quadrant.Unknown
};
```

<span data-ttu-id="be843-204">El patrón de descarte del modificador anterior coincide cuando `x` o `y` es 0, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="be843-204">The discard pattern in the preceding switch matches when either `x` or `y` is 0, but not both.</span></span> <span data-ttu-id="be843-205">Una expresión switch debe generar un valor o producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="be843-205">A switch expression must either produce a value or throw an exception.</span></span> <span data-ttu-id="be843-206">Si ninguno de los casos coincide, la expresión switch produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="be843-206">If none of the cases match, the switch expression throws an exception.</span></span> <span data-ttu-id="be843-207">El compilador genera una advertencia si no cubre todos los posibles casos en la expresión switch.</span><span class="sxs-lookup"><span data-stu-id="be843-207">The compiler generates a warning for you if you don't cover all possible cases in your switch expression.</span></span>

<span data-ttu-id="be843-208">Puede explorar las técnicas de coincidencia de patrones en este [tutorial avanzado sobre la coincidencia de patrones](../tutorials/pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="be843-208">You can explore pattern matching techniques in this [advanced tutorial on pattern matching](../tutorials/pattern-matching.md).</span></span>

## <a name="using-declarations"></a><span data-ttu-id="be843-209">Declaraciones using</span><span class="sxs-lookup"><span data-stu-id="be843-209">Using declarations</span></span>

<span data-ttu-id="be843-210">Una **declaración using** es una declaración de variable precedida por la palabra clave `using`.</span><span class="sxs-lookup"><span data-stu-id="be843-210">A **using declaration** is a variable declaration preceded by the `using` keyword.</span></span> <span data-ttu-id="be843-211">Indica al compilador que la variable que se declara debe eliminarse al final del ámbito de inclusión.</span><span class="sxs-lookup"><span data-stu-id="be843-211">It tells the compiler that the variable being declared should be disposed at the end of the enclosing scope.</span></span> <span data-ttu-id="be843-212">Por ejemplo, considere el siguiente código que escribe un archivo de texto:</span><span class="sxs-lookup"><span data-stu-id="be843-212">For example, consider the following code that writes a text file:</span></span>

```csharp
static int WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    int skippedLines = 0;
    foreach (string line in lines)
    {
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
        else
        {
            skippedLines++;
        }
    }
    // Notice how skippedLines is in scope here.
    return skippedLines;
    // file is disposed here
}
```

<span data-ttu-id="be843-213">En el ejemplo anterior, el archivo se elimina cuando se alcanza la llave de cierre del método.</span><span class="sxs-lookup"><span data-stu-id="be843-213">In the preceding example, the file is disposed when the closing brace for the method is reached.</span></span> <span data-ttu-id="be843-214">Ese es el final del ámbito en el que se declara `file`.</span><span class="sxs-lookup"><span data-stu-id="be843-214">That's the end of the scope in which `file` is declared.</span></span> <span data-ttu-id="be843-215">El código anterior es equivalente al siguiente código que usa las [instrucciones using](../language-reference/keywords/using-statement.md) clásicas:</span><span class="sxs-lookup"><span data-stu-id="be843-215">The preceding code is equivalent to the following code that uses the classic [using statement](../language-reference/keywords/using-statement.md):</span></span>

```csharp
static int WriteLinesToFile(IEnumerable<string> lines)
{
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        int skippedLines = 0;
        foreach (string line in lines)
        {
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
            else
            {
                skippedLines++;
            }
        }
        return skippedLines;
    } // file is disposed here
}
```

<span data-ttu-id="be843-216">En el ejemplo anterior, el archivo se elimina cuando se alcanza la llave de cierre asociada con la instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="be843-216">In the preceding example, the file is disposed when the closing brace associated with the `using` statement is reached.</span></span>

<span data-ttu-id="be843-217">En ambos casos, el compilador genera la llamada a `Dispose()`.</span><span class="sxs-lookup"><span data-stu-id="be843-217">In both cases, the compiler generates the call to `Dispose()`.</span></span> <span data-ttu-id="be843-218">El compilador genera un error si la expresión de la instrucción `using` no se puede eliminar.</span><span class="sxs-lookup"><span data-stu-id="be843-218">The compiler generates an error if the expression in the `using` statement isn't disposable.</span></span>

## <a name="static-local-functions"></a><span data-ttu-id="be843-219">Funciones locales estáticas</span><span class="sxs-lookup"><span data-stu-id="be843-219">Static local functions</span></span>

<span data-ttu-id="be843-220">Ahora puede agregar el modificador `static` a [funciones locales](../programming-guide/classes-and-structs/local-functions.md) para asegurarse de que la función local no captura las variables del ámbito de inclusión (esto es, no hace referencia a ellas).</span><span class="sxs-lookup"><span data-stu-id="be843-220">You can now add the `static` modifier to [local functions](../programming-guide/classes-and-structs/local-functions.md) to ensure that local function doesn't capture (reference) any variables from the enclosing scope.</span></span> <span data-ttu-id="be843-221">Si lo hace, se genera un error que dice que `CS8421`una función local estática no puede contener una referencia a \<variable>.</span><span class="sxs-lookup"><span data-stu-id="be843-221">Doing so generates `CS8421`, "A static local function can't contain a reference to \<variable>."</span></span>

<span data-ttu-id="be843-222">Observe el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="be843-222">Consider the following code.</span></span> <span data-ttu-id="be843-223">La función local `LocalFunction` accede a la variable `y`, declarada en el ámbito de inclusión (el método `M`).</span><span class="sxs-lookup"><span data-stu-id="be843-223">The local function `LocalFunction` accesses the variable `y`, declared in the enclosing scope (the method `M`).</span></span> <span data-ttu-id="be843-224">Por lo tanto, `LocalFunction` no se puede declarar con el modificador `static`:</span><span class="sxs-lookup"><span data-stu-id="be843-224">Therefore, `LocalFunction` can't be declared with the `static` modifier:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="be843-225">El código siguiente contiene una función local estática.</span><span class="sxs-lookup"><span data-stu-id="be843-225">The following code contains a static local function.</span></span> <span data-ttu-id="be843-226">Puede ser estática porque no accede a las variables del ámbito de inclusión:</span><span class="sxs-lookup"><span data-stu-id="be843-226">It can be static because it doesn't access any variables in the enclosing scope:</span></span>

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a><span data-ttu-id="be843-227">Estructuras ref descartables</span><span class="sxs-lookup"><span data-stu-id="be843-227">Disposable ref structs</span></span>

<span data-ttu-id="be843-228">Un elemento `struct` declarado con el modificador `ref` no puede implementar ninguna interfaz y, por tanto, no puede implementar <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="be843-228">A `struct` declared with the `ref` modifier may not implement any interfaces and so can't implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="be843-229">Por lo tanto, para permitir que se elimine un elemento `ref struct`, debe tener un método `void Dispose()` accesible.</span><span class="sxs-lookup"><span data-stu-id="be843-229">Therefore, to enable a `ref struct` to be disposed, it must have an accessible `void Dispose()` method.</span></span> <span data-ttu-id="be843-230">Esta característica también se aplica a las declaraciones `readonly ref struct`.</span><span class="sxs-lookup"><span data-stu-id="be843-230">This feature also applies to `readonly ref struct` declarations.</span></span>

## <a name="nullable-reference-types"></a><span data-ttu-id="be843-231">Tipos de referencia que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="be843-231">Nullable reference types</span></span>

<span data-ttu-id="be843-232">Dentro de un contexto de anotación que acepta valores NULL, cualquier variable de un tipo de referencia se considera un **tipo de referencia que no acepta valores NULL**.</span><span class="sxs-lookup"><span data-stu-id="be843-232">Inside a nullable annotation context, any variable of a reference type is considered to be a **nonnullable reference type**.</span></span> <span data-ttu-id="be843-233">Si quiere indicar que una variable puede ser NULL, debe anexar `?` al nombre del tipo para declarar la variable como un **tipo de referencia que acepta valores NULL**.</span><span class="sxs-lookup"><span data-stu-id="be843-233">If you want to indicate that a variable may be null, you must append the type name with the `?` to declare the variable as a **nullable reference type**.</span></span>

<span data-ttu-id="be843-234">En los tipos de referencia que no aceptan valores NULL, el compilador usa el análisis de flujo para garantizar que las variables locales se inicializan en un valor no NULL cuando se declaran.</span><span class="sxs-lookup"><span data-stu-id="be843-234">For nonnullable reference types, the compiler uses flow analysis to ensure that local variables are initialized to a non-null value when declared.</span></span> <span data-ttu-id="be843-235">Los campos se deben inicializar durante la construcción.</span><span class="sxs-lookup"><span data-stu-id="be843-235">Fields must be initialized during construction.</span></span> <span data-ttu-id="be843-236">Si la variable no se establece mediante una llamada a alguno de los constructores disponibles o por medio de un inicializador, el compilador genera una advertencia.</span><span class="sxs-lookup"><span data-stu-id="be843-236">The compiler generates a warning if the variable isn't set by a call to any of the available constructors or by an initializer.</span></span> <span data-ttu-id="be843-237">Además, los tipos de referencia que no aceptan valores NULL no pueden tener asignado un valor que podría ser NULL.</span><span class="sxs-lookup"><span data-stu-id="be843-237">Furthermore, nonnullable reference types can't be assigned a value that could be null.</span></span>

<span data-ttu-id="be843-238">Los tipos de referencia que aceptan valores NULL no se comprueban para garantizar que se asignan o inicializan como NULL.</span><span class="sxs-lookup"><span data-stu-id="be843-238">Nullable reference types aren't checked to ensure they aren't assigned or initialized to null.</span></span> <span data-ttu-id="be843-239">Sin embargo, el compilador usa el análisis de flujo para garantizar que cualquier variable de un tipo de referencia que acepta valores NULL se compara con NULL antes de acceder a ella o de asignarse a un tipo de referencia que no los acepta.</span><span class="sxs-lookup"><span data-stu-id="be843-239">However, the compiler uses flow analysis to ensure that any variable of a nullable reference type is checked against null before it's accessed or assigned to a nonnullable reference type.</span></span>

<span data-ttu-id="be843-240">Puede aprender más sobre la característica en la introducción a los [tipos de referencia que aceptan valores NULL](../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="be843-240">You can learn more about the feature in the overview of [nullable reference types](../nullable-references.md).</span></span> <span data-ttu-id="be843-241">Pruébela por su cuenta en una nueva aplicación en este [tutorial de tipos de referencia que aceptan valores NULL](tutorials/nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="be843-241">Try it yourself in a new application in this [nullable reference types tutorial](tutorials/nullable-reference-types.md).</span></span> <span data-ttu-id="be843-242">Puede encontrar más información sobre los pasos para migrar una base de código existente para hacer uso de los tipos de referencia que aceptan valores NULL en el [tutorial sobre la migración de una aplicación para usar tipos de referencia que aceptan valores NULL](tutorials/upgrade-to-nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="be843-242">Learn about the steps to migrate an existing codebase to make use of nullable reference types in the [migrating an application to use nullable reference types tutorial](tutorials/upgrade-to-nullable-references.md).</span></span>

## <a name="asynchronous-streams"></a><span data-ttu-id="be843-243">Secuencias asincrónicas</span><span class="sxs-lookup"><span data-stu-id="be843-243">Asynchronous streams</span></span>

<span data-ttu-id="be843-244">A partir de C# 8.0, puede crear y consumir secuencias de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="be843-244">Starting with C# 8.0, you can create and consume streams asynchronously.</span></span> <span data-ttu-id="be843-245">Un método que devuelve una secuencia asincrónica tiene tres propiedades:</span><span class="sxs-lookup"><span data-stu-id="be843-245">A method that returns an asynchronous stream has three properties:</span></span>

1. <span data-ttu-id="be843-246">Se declara con el modificador `async`.</span><span class="sxs-lookup"><span data-stu-id="be843-246">It's declared with the `async` modifier.</span></span>
1. <span data-ttu-id="be843-247">Devuelve <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="be843-247">It returns an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span>
1. <span data-ttu-id="be843-248">El método contiene instrucciones `yield return` que devuelven elementos sucesivos de la secuencia asincrónica.</span><span class="sxs-lookup"><span data-stu-id="be843-248">The method contains `yield return` statements to return successive elements in the asynchronous stream.</span></span>

<span data-ttu-id="be843-249">Para consumir una secuencia asincrónica es necesario agregar la palabra clave `await` delante de la palabra clave `foreach` al enumerar los elementos de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="be843-249">Consuming an asynchronous stream requires you to add the `await` keyword before the `foreach` keyword when you enumerate the elements of the stream.</span></span> <span data-ttu-id="be843-250">Para agregar la palabra clave `await` es necesario declarar el método que enumera la secuencia asincrónica con el modificador `async` y devolver un tipo permitido para un método `async`.</span><span class="sxs-lookup"><span data-stu-id="be843-250">Adding the `await` keyword requires the method that enumerates the asynchronous stream to be declared with the `async` modifier and to return a type allowed for an `async` method.</span></span> <span data-ttu-id="be843-251">Normalmente, esto significa devolver <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="be843-251">Typically that means returning a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="be843-252">También puede ser <xref:System.Threading.Tasks.ValueTask> o <xref:System.Threading.Tasks.ValueTask%601>.</span><span class="sxs-lookup"><span data-stu-id="be843-252">It can also be a <xref:System.Threading.Tasks.ValueTask> or <xref:System.Threading.Tasks.ValueTask%601>.</span></span> <span data-ttu-id="be843-253">Un método puede consumir y producir una secuencia asincrónica, lo que significa que devolvería <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="be843-253">A method can both consume and produce an asynchronous stream, which means it would return an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span> <span data-ttu-id="be843-254">El siguiente código genera una secuencia de 0 a 19, con una espera de 100 ms entre la generación de cada número:</span><span class="sxs-lookup"><span data-stu-id="be843-254">The following code generates a sequence from 0 to 19, waiting 100 ms between generating each number:</span></span>

```csharp
public static async System.Collections.Generic.IAsyncEnumerable<int> GenerateSequence()
{
    for (int i = 0; i < 20; i++)
    {
        await Task.Delay(100);
        yield return i;
    }
}
```

<span data-ttu-id="be843-255">Se enumeraría la secuencia mediante la instrucción `await foreach`:</span><span class="sxs-lookup"><span data-stu-id="be843-255">You would enumerate the sequence using the `await foreach` statement:</span></span>

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

<span data-ttu-id="be843-256">Puede probar secuencias asincrónicas por su cuenta en nuestro tutorial sobre la [creación y consumo de secuencias asincrónicas](tutorials/generate-consume-asynchronous-stream.md).</span><span class="sxs-lookup"><span data-stu-id="be843-256">You can try asynchronous streams yourself in our tutorial on [creating and consuming async streams](tutorials/generate-consume-asynchronous-stream.md).</span></span> <span data-ttu-id="be843-257">Los elementos de secuencia se procesan de forma predeterminada en el contexto capturado.</span><span class="sxs-lookup"><span data-stu-id="be843-257">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="be843-258">Si quiere deshabilitar la captura del contexto, use el método de extensión <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="be843-258">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="be843-259">Para obtener más información sobre los contextos de sincronización y la captura del contexto actual, vea el artículo sobre el [consumo del patrón asincrónico basado en tareas](../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="be843-259">For more information about synchronization contexts and capturing the current context, see the article on [consuming the Task-based asynchronous pattern](../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span>

## <a name="asynchronous-disposable"></a><span data-ttu-id="be843-260">Asincrónica descartable</span><span class="sxs-lookup"><span data-stu-id="be843-260">Asynchronous disposable</span></span>

<span data-ttu-id="be843-261">A partir C# 8.0, el lenguaje admite tipos descartables asincrónicos que implementan la interfaz <xref:System.IAsyncDisposable?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="be843-261">Starting with C# 8.0, the language supports asynchronous disposable types that implement the <xref:System.IAsyncDisposable?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="be843-262">Use la instrucción `await using` para trabajar con un objeto descartable de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="be843-262">You use the `await using` statement to work with an asynchronously disposable object.</span></span> <span data-ttu-id="be843-263">Para obtener más información, vea el artículo [Implementación de un método DisposeAsync](../../standard/garbage-collection/implementing-disposeasync.md).</span><span class="sxs-lookup"><span data-stu-id="be843-263">For more information, see the [Implement a DisposeAsync method](../../standard/garbage-collection/implementing-disposeasync.md) article.</span></span>

## <a name="indices-and-ranges"></a><span data-ttu-id="be843-264">Índices y rangos</span><span class="sxs-lookup"><span data-stu-id="be843-264">Indices and ranges</span></span>

<span data-ttu-id="be843-265">Los índices y rangos proporcionan una sintaxis concisa para acceder a elementos únicos o intervalos en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="be843-265">Indices and ranges provide a succinct syntax for accessing single elements or ranges in a sequence.</span></span>

<span data-ttu-id="be843-266">Esta compatibilidad con lenguajes se basa en dos nuevos tipos y dos nuevos operadores:</span><span class="sxs-lookup"><span data-stu-id="be843-266">This language support relies on two new types, and two new operators:</span></span>

- <span data-ttu-id="be843-267"><xref:System.Index?displayProperty=nameWithType> representa un índice en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="be843-267"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="be843-268">El índice desde el operador final `^`, que especifica que un índice es relativo al final de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="be843-268">The index from end operator `^`, which specifies that an index is relative to the end of the sequence.</span></span>
- <span data-ttu-id="be843-269"><xref:System.Range?displayProperty=nameWithType> representa un subrango de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="be843-269"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="be843-270">El operador de intervalo `..`, que especifica el inicio y el final de un intervalo como sus operandos.</span><span class="sxs-lookup"><span data-stu-id="be843-270">The range operator `..`, which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="be843-271">Comencemos con las reglas de índices.</span><span class="sxs-lookup"><span data-stu-id="be843-271">Let's start with the rules for indexes.</span></span> <span data-ttu-id="be843-272">Considere un elemento `sequence` de matriz.</span><span class="sxs-lookup"><span data-stu-id="be843-272">Consider an array `sequence`.</span></span> <span data-ttu-id="be843-273">El índice `0` es igual que `sequence[0]`.</span><span class="sxs-lookup"><span data-stu-id="be843-273">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="be843-274">El índice `^0` es igual que `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="be843-274">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="be843-275">Tenga en cuenta que `sequence[^0]` produce una excepción, al igual que `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="be843-275">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="be843-276">Para cualquier número `n`, el índice `^n` es igual que `sequence.Length - n`.</span><span class="sxs-lookup"><span data-stu-id="be843-276">For any number `n`, the index `^n` is the same as `sequence.Length - n`.</span></span>

<span data-ttu-id="be843-277">Un rango especifica el *inicio* y el *final* de un intervalo.</span><span class="sxs-lookup"><span data-stu-id="be843-277">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="be843-278">El inicio del rango es inclusivo, pero su final es exclusivo, lo que significa que el *inicio* se incluye en el rango, pero el *final* no.</span><span class="sxs-lookup"><span data-stu-id="be843-278">The start of the range is inclusive, but the end of the range is exclusive, meaning the *start* is included in the range but the *end* isn't included in the range.</span></span> <span data-ttu-id="be843-279">El rango `[0..^0]` representa todo el intervalo, al igual que `[0..sequence.Length]` representa todo el intervalo.</span><span class="sxs-lookup"><span data-stu-id="be843-279">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span>

<span data-ttu-id="be843-280">Veamos algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="be843-280">Let's look at a few examples.</span></span> <span data-ttu-id="be843-281">Tenga en cuenta la siguiente matriz, anotada con su índice desde el principio y desde el final:</span><span class="sxs-lookup"><span data-stu-id="be843-281">Consider the following array, annotated with its index from the start and from the end:</span></span>

```csharp
var words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};              // 9 (or words.Length) ^0
```

<span data-ttu-id="be843-282">Puede recuperar la última palabra con el índice `^1`:</span><span class="sxs-lookup"><span data-stu-id="be843-282">You can retrieve the last word with the `^1` index:</span></span>

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

<span data-ttu-id="be843-283">El siguiente código crea un subrango con las palabras "quick", "brown" y "fox".</span><span class="sxs-lookup"><span data-stu-id="be843-283">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="be843-284">Va de `words[1]` a `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="be843-284">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="be843-285">El elemento `words[4]` no se encuentra en el intervalo.</span><span class="sxs-lookup"><span data-stu-id="be843-285">The element `words[4]` isn't in the range.</span></span>

```csharp
var quickBrownFox = words[1..4];
```

<span data-ttu-id="be843-286">El siguiente código crea un subrango con "lazy" y "dog".</span><span class="sxs-lookup"><span data-stu-id="be843-286">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="be843-287">Incluye `words[^2]` y `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="be843-287">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="be843-288">El índice del final `words[^0]` no se incluye:</span><span class="sxs-lookup"><span data-stu-id="be843-288">The end index `words[^0]` isn't included:</span></span>

```csharp
var lazyDog = words[^2..^0];
```

<span data-ttu-id="be843-289">En los ejemplos siguientes se crean rangos con final abierto para el inicio, el final o ambos:</span><span class="sxs-lookup"><span data-stu-id="be843-289">The following examples create ranges that are open ended for the start, end, or both:</span></span>

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the", "lazy" and "dog"
```

<span data-ttu-id="be843-290">También puede declarar rangos como variables:</span><span class="sxs-lookup"><span data-stu-id="be843-290">You can also declare ranges as variables:</span></span>

```csharp
Range phrase = 1..4;
```

<span data-ttu-id="be843-291">El rango se puede usar luego dentro de los caracteres `[` y `]`:</span><span class="sxs-lookup"><span data-stu-id="be843-291">The range can then be used inside the `[` and `]` characters:</span></span>

```csharp
var text = words[phrase];
```

<span data-ttu-id="be843-292">No solo las matrices admiten índices y rangos.</span><span class="sxs-lookup"><span data-stu-id="be843-292">Not only arrays support indices and ranges.</span></span> <span data-ttu-id="be843-293">También puede usar índices y rangos con [string](../language-reference/builtin-types/reference-types.md#the-string-type), <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="be843-293">You can also use indices and ranges with [string](../language-reference/builtin-types/reference-types.md#the-string-type), <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="be843-294">Para más información, consulte [Compatibilidad con tipos para los índices y los rangos](tutorials/ranges-indexes.md#type-support-for-indices-and-ranges).</span><span class="sxs-lookup"><span data-stu-id="be843-294">For more information, see [Type support for indices and ranges](tutorials/ranges-indexes.md#type-support-for-indices-and-ranges).</span></span>

<span data-ttu-id="be843-295">Puede explorar más información acerca de los índices y los intervalos en el tutorial sobre [índices e intervalos](tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="be843-295">You can explore more about indices and ranges in the tutorial on [indices and ranges](tutorials/ranges-indexes.md).</span></span>

## <a name="null-coalescing-assignment"></a><span data-ttu-id="be843-296">Asignación de uso combinado de NULL</span><span class="sxs-lookup"><span data-stu-id="be843-296">Null-coalescing assignment</span></span>

<span data-ttu-id="be843-297">C# 8.0 presenta el operador de asignación de uso combinado de `??=`.</span><span class="sxs-lookup"><span data-stu-id="be843-297">C# 8.0 introduces the null-coalescing assignment operator `??=`.</span></span> <span data-ttu-id="be843-298">Puede usar el operador `??=` para asignar el valor de su operando derecho al operando izquierdo solo si el operando izquierdo se evalúa como `null`.</span><span class="sxs-lookup"><span data-stu-id="be843-298">You can use the `??=` operator to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span>

```csharp
List<int> numbers = null;
int? i = null;

numbers ??= new List<int>();
numbers.Add(i ??= 17);
numbers.Add(i ??= 20);

Console.WriteLine(string.Join(" ", numbers));  // output: 17 17
Console.WriteLine(i);  // output: 17
```

<span data-ttu-id="be843-299">Para obtener más información, consulte [Operadores ?? y ??](../language-reference/operators/null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="be843-299">For more information, see the [?? and ??= operators](../language-reference/operators/null-coalescing-operator.md) article.</span></span>

## <a name="unmanaged-constructed-types"></a><span data-ttu-id="be843-300">Tipos construidos no administrados</span><span class="sxs-lookup"><span data-stu-id="be843-300">Unmanaged constructed types</span></span>

<span data-ttu-id="be843-301">En C# 7.3 y versiones anteriores, un tipo construido (es decir, un tipo que incluye al menos un argumento de tipo) no puede ser un [tipo no administrado](../language-reference/builtin-types/unmanaged-types.md).</span><span class="sxs-lookup"><span data-stu-id="be843-301">In C# 7.3 and earlier, a constructed type (a type that includes at least one type argument) can't be an [unmanaged type](../language-reference/builtin-types/unmanaged-types.md).</span></span> <span data-ttu-id="be843-302">A partir de C# 8.0, un tipo de valor construido no está administrado si solo contiene campos de tipos no administrados.</span><span class="sxs-lookup"><span data-stu-id="be843-302">Starting with C# 8.0, a constructed value type is unmanaged if it contains fields of unmanaged types only.</span></span>

<span data-ttu-id="be843-303">Por ejemplo, dada la siguiente definición del tipo genérico `Coords<T>`:</span><span class="sxs-lookup"><span data-stu-id="be843-303">For example, given the following definition of the generic `Coords<T>` type:</span></span>

```csharp
public struct Coords<T>
{
    public T X;
    public T Y;
}
```

<span data-ttu-id="be843-304">el tipo `Coords<int>` es un tipo no administrado en C# 8.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="be843-304">the `Coords<int>` type is an unmanaged type in C# 8.0 and later.</span></span> <span data-ttu-id="be843-305">Al igual que en el caso de cualquier tipo no administrado, puede crear un puntero a una variable de este tipo o [asignar un bloque de memoria en la pila](../language-reference/operators/stackalloc.md) para las instancias de este tipo:</span><span class="sxs-lookup"><span data-stu-id="be843-305">Like for any unmanaged type, you can create a pointer to a variable of this type or [allocate a block of memory on the stack](../language-reference/operators/stackalloc.md) for instances of this type:</span></span>

```csharp
Span<Coords<int>> coordinates = stackalloc[]
{
    new Coords<int> { X = 0, Y = 0 },
    new Coords<int> { X = 0, Y = 3 },
    new Coords<int> { X = 4, Y = 0 }
};
```

<span data-ttu-id="be843-306">Para más información, consulte [Tipos no administrados](../language-reference/builtin-types/unmanaged-types.md).</span><span class="sxs-lookup"><span data-stu-id="be843-306">For more information, see [Unmanaged types](../language-reference/builtin-types/unmanaged-types.md).</span></span>

## <a name="stackalloc-in-nested-expressions"></a><span data-ttu-id="be843-307">Stackalloc en expresiones anidadas</span><span class="sxs-lookup"><span data-stu-id="be843-307">Stackalloc in nested expressions</span></span>

<span data-ttu-id="be843-308">A partir de C# 8.0, si el resultado de una expresión [stackalloc](../language-reference/operators/stackalloc.md) es del tipo <xref:System.Span%601?displayProperty=nameWithType> o <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, puede usar la expresión `stackalloc` en otras expresiones:</span><span class="sxs-lookup"><span data-stu-id="be843-308">Starting with C# 8.0, if the result of a [stackalloc](../language-reference/operators/stackalloc.md) expression is of the <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> type, you can use the `stackalloc` expression in other expressions:</span></span>

```csharp
Span<int> numbers = stackalloc[] { 1, 2, 3, 4, 5, 6 };
var ind = numbers.IndexOfAny(stackalloc[] { 2, 4, 6, 8 });
Console.WriteLine(ind);  // output: 1
```

## <a name="enhancement-of-interpolated-verbatim-strings"></a><span data-ttu-id="be843-309">Mejora de las cadenas textuales interpoladas</span><span class="sxs-lookup"><span data-stu-id="be843-309">Enhancement of interpolated verbatim strings</span></span>

<span data-ttu-id="be843-310">El orden de los tokens `$` y `@` en las cadenas textuales [interpoladas](../language-reference/tokens/interpolated.md) puede ser cualquiera: tanto `$@"..."` como `@$"..."` son cadenas textuales interpoladas válidas.</span><span class="sxs-lookup"><span data-stu-id="be843-310">Order of the `$` and `@` tokens in [interpolated](../language-reference/tokens/interpolated.md) verbatim strings can be any: both `$@"..."` and `@$"..."` are valid interpolated verbatim strings.</span></span> <span data-ttu-id="be843-311">En versiones de C# anteriores, el token `$` debe aparecer delante del token `@`.</span><span class="sxs-lookup"><span data-stu-id="be843-311">In earlier C# versions, the `$` token must appear before the `@` token.</span></span>
