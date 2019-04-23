---
title: 'Novedades de C# 8.0: Guía de C#'
description: Obtenga información general sobre las nuevas características disponibles en C# 8.0. Este artículo está actualizado con la versión preliminar 2.
ms.date: 02/12/2019
ms.openlocfilehash: eecc37433e4b026b7337418eac1a5e80ef48ea6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59427284"
---
# <a name="whats-new-in-c-80"></a><span data-ttu-id="c9877-104">Novedades de C# 8.0</span><span class="sxs-lookup"><span data-stu-id="c9877-104">What's new in C# 8.0</span></span>

<span data-ttu-id="c9877-105">Hay muchas mejoras en el lenguaje C# que ya se pueden probar en la versión preliminar 2.</span><span class="sxs-lookup"><span data-stu-id="c9877-105">There are many enhancements to the C# language that you can try out already with preview 2.</span></span> <span data-ttu-id="c9877-106">Las nuevas características agregadas en la versión preliminar 2 son:</span><span class="sxs-lookup"><span data-stu-id="c9877-106">The new features added in preview 2 are:</span></span>

- <span data-ttu-id="c9877-107">[Mejoras de coincidencia de patrones](#more-patterns-in-more-places):</span><span class="sxs-lookup"><span data-stu-id="c9877-107">[Pattern matching enhancements](#more-patterns-in-more-places):</span></span>
  * [<span data-ttu-id="c9877-108">Expresiones switch</span><span class="sxs-lookup"><span data-stu-id="c9877-108">Switch expressions</span></span>](#switch-expressions)
  * [<span data-ttu-id="c9877-109">Patrones de propiedades</span><span class="sxs-lookup"><span data-stu-id="c9877-109">Property patterns</span></span>](#property-patterns)
  * [<span data-ttu-id="c9877-110">Patrones de tupla</span><span class="sxs-lookup"><span data-stu-id="c9877-110">Tuple patterns</span></span>](#tuple-patterns)
  * [<span data-ttu-id="c9877-111">Patrones posicionales</span><span class="sxs-lookup"><span data-stu-id="c9877-111">Positional patterns</span></span>](#positional-patterns)
- [<span data-ttu-id="c9877-112">Declaraciones using</span><span class="sxs-lookup"><span data-stu-id="c9877-112">Using declarations</span></span>](#using-declarations)
- [<span data-ttu-id="c9877-113">Funciones locales estáticas</span><span class="sxs-lookup"><span data-stu-id="c9877-113">Static local functions</span></span>](#static-local-functions)
- [<span data-ttu-id="c9877-114">Estructuras ref descartables</span><span class="sxs-lookup"><span data-stu-id="c9877-114">Disposable ref structs</span></span>](#disposable-ref-structs)

<span data-ttu-id="c9877-115">Las siguientes características del lenguaje aparecieron primero en la versión preliminar 1 de C# 8.0:</span><span class="sxs-lookup"><span data-stu-id="c9877-115">The following language features first appeared in C# 8.0 preview 1:</span></span>

- [<span data-ttu-id="c9877-116">Tipos de referencia que aceptan valores null</span><span class="sxs-lookup"><span data-stu-id="c9877-116">Nullable reference types</span></span>](#nullable-reference-types)
- [<span data-ttu-id="c9877-117">Secuencias asincrónicas</span><span class="sxs-lookup"><span data-stu-id="c9877-117">Asynchronous streams</span></span>](#asynchronous-streams)
- [<span data-ttu-id="c9877-118">Índices y rangos</span><span class="sxs-lookup"><span data-stu-id="c9877-118">Indices and ranges</span></span>](#indices-and-ranges)

> [!NOTE]
> <span data-ttu-id="c9877-119">Este artículo se actualizó por última vez para la versión preliminar 2 de C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="c9877-119">This article was last updated for C# 8.0 preview 2.</span></span>

<span data-ttu-id="c9877-120">En el resto de este artículo se describen brevemente estas características.</span><span class="sxs-lookup"><span data-stu-id="c9877-120">The remainder of this article briefly describes these features.</span></span> <span data-ttu-id="c9877-121">Cuando hay disponibles artículos detallados, se proporcionan vínculos a esos tutoriales e introducciones.</span><span class="sxs-lookup"><span data-stu-id="c9877-121">Where in-depth articles are available, links to those tutorials and overviews are provided.</span></span>

## <a name="more-patterns-in-more-places"></a><span data-ttu-id="c9877-122">Más patrones en más lugares</span><span class="sxs-lookup"><span data-stu-id="c9877-122">More patterns in more places</span></span>

<span data-ttu-id="c9877-123">La **coincidencia de patrones** ofrece herramientas que proporcionan funcionalidad dependiente de la forma entre tipos de datos relacionados pero diferentes.</span><span class="sxs-lookup"><span data-stu-id="c9877-123">**Pattern matching** gives tools to provide shape-dependent functionality across related but different kinds of data.</span></span> <span data-ttu-id="c9877-124">C# 7.0 introdujo la sintaxis de patrones de tipos y patrones de constantes mediante la expresión [`is`](../language-reference/keywords/is.md) y la instrucción [`switch`](../language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="c9877-124">C# 7.0 introduced syntax for type patterns and constant patterns by using the [`is`](../language-reference/keywords/is.md) expression and the [`switch`](../language-reference/keywords/switch.md) statement.</span></span> <span data-ttu-id="c9877-125">Estas características representaban los primeros pasos hacia el uso de paradigmas de programación donde los datos y la funcionalidad están separados.</span><span class="sxs-lookup"><span data-stu-id="c9877-125">These features represented the first tentative steps toward supporting programming paradigms where data and functionality live apart.</span></span> <span data-ttu-id="c9877-126">A medida que el sector se mueve hacia más microservicios y otras arquitecturas basadas en la nube, se necesitan otras herramientas de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="c9877-126">As the industry moves toward more microservices and other cloud-based architectures, other language tools are needed.</span></span>

<span data-ttu-id="c9877-127">C# 8.0 amplía este vocabulario para que pueda usar más expresiones de patrones en más lugares del código.</span><span class="sxs-lookup"><span data-stu-id="c9877-127">C# 8.0 expands this vocabulary so you can use more pattern expressions in more places in your code.</span></span> <span data-ttu-id="c9877-128">Cuando los datos y la funcionalidad estén separados, tenga en cuenta estas características.</span><span class="sxs-lookup"><span data-stu-id="c9877-128">Consider these features when your data and functionality are separate.</span></span> <span data-ttu-id="c9877-129">Cuando los algoritmos dependan de un hecho distinto del tipo de entorno de ejecución de un objeto, tenga en cuenta la coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="c9877-129">Consider pattern matching when your algorithms depend on a fact other than the runtime type of an object.</span></span> <span data-ttu-id="c9877-130">Estas técnicas ofrecen otra forma de expresar los diseños.</span><span class="sxs-lookup"><span data-stu-id="c9877-130">These techniques provide another way to express designs.</span></span>

<span data-ttu-id="c9877-131">Además de nuevos patrones en nuevos lugares C# 8.0 agrega **patrones recursivos**.</span><span class="sxs-lookup"><span data-stu-id="c9877-131">In addition to new patterns in new places, C# 8.0 adds **recursive patterns**.</span></span> <span data-ttu-id="c9877-132">El resultado de cualquier expresión de patrón es una expresión.</span><span class="sxs-lookup"><span data-stu-id="c9877-132">The result of any pattern expression is an expression.</span></span> <span data-ttu-id="c9877-133">Un patrón recursivo es simplemente una expresión de patrón aplicada a la salida de otra expresión de patrón.</span><span class="sxs-lookup"><span data-stu-id="c9877-133">A recursive pattern is simply a pattern expression applied to the output of another pattern expression.</span></span>

### <a name="switch-expressions"></a><span data-ttu-id="c9877-134">Expresiones switch</span><span class="sxs-lookup"><span data-stu-id="c9877-134">switch expressions</span></span>

<span data-ttu-id="c9877-135">Con frecuencia, una instrucción [ `switch`](../language-reference/keywords/switch.md) genera un valor en cada uno de sus bloques `case`.</span><span class="sxs-lookup"><span data-stu-id="c9877-135">Often, a [`switch`](../language-reference/keywords/switch.md) statement produces a value in each of its `case` blocks.</span></span> <span data-ttu-id="c9877-136">Las **expresiones switch** le permiten usar una sintaxis de expresiones más concisa.</span><span class="sxs-lookup"><span data-stu-id="c9877-136">**Switch expressions** enable you to use more concise expression syntax.</span></span> <span data-ttu-id="c9877-137">Hay menos palabras clave `case` y `break` repetitivas y menos llaves.</span><span class="sxs-lookup"><span data-stu-id="c9877-137">There are fewer repetitive `case` and `break` keywords, and fewer curly braces.</span></span>  <span data-ttu-id="c9877-138">Por ejemplo, considere la siguiente enumeración que muestra los colores del arco iris:</span><span class="sxs-lookup"><span data-stu-id="c9877-138">As an example, consider the following enum that lists the colors of the rainbow:</span></span>

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

<span data-ttu-id="c9877-139">Si la aplicación definió un tipo `RGBColor` construido a partir de los componentes `R`, `G` y `B`, podría convertir un valor `Rainbow` a sus valores RGB con el método siguiente que contiene una expresión switch:</span><span class="sxs-lookup"><span data-stu-id="c9877-139">If your application defined an `RGBColor` type that is constructed from the `R`, `G` and `B` components, you could convert a `Rainbow` value to its RGB values using the following method containing a switch expression:</span></span>

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

<span data-ttu-id="c9877-140">Aquí hay varias mejoras en la sintaxis:</span><span class="sxs-lookup"><span data-stu-id="c9877-140">There are several syntax improvements here:</span></span>

- <span data-ttu-id="c9877-141">La variable precede a la palabra clave `switch`.</span><span class="sxs-lookup"><span data-stu-id="c9877-141">The variable comes before the `switch` keyword.</span></span> <span data-ttu-id="c9877-142">El orden diferente permite distinguir fácilmente la expresión switch de la instrucción switch.</span><span class="sxs-lookup"><span data-stu-id="c9877-142">The different order makes it visually easy to distinguish the switch expression from the switch statement.</span></span>
- <span data-ttu-id="c9877-143">Los elementos `case` y `:` se reemplazan por `=>`.</span><span class="sxs-lookup"><span data-stu-id="c9877-143">The `case` and `:` elements are replaced with `=>`.</span></span> <span data-ttu-id="c9877-144">Es más concisa e intuitiva.</span><span class="sxs-lookup"><span data-stu-id="c9877-144">It's more concise and intuitive.</span></span>
- <span data-ttu-id="c9877-145">El caso `default` se reemplaza por un descarte `_`.</span><span class="sxs-lookup"><span data-stu-id="c9877-145">The `default` case is replaced with a `_` discard.</span></span>
- <span data-ttu-id="c9877-146">Los cuerpos son expresiones, no instrucciones.</span><span class="sxs-lookup"><span data-stu-id="c9877-146">The bodies are expressions, not statements.</span></span>

<span data-ttu-id="c9877-147">Compárelo con el código equivalente mediante la instrucción clásica `switch`:</span><span class="sxs-lookup"><span data-stu-id="c9877-147">Contrast that with the equivalent code using the classic `switch` statement:</span></span>

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

### <a name="property-patterns"></a><span data-ttu-id="c9877-148">Patrones de propiedades</span><span class="sxs-lookup"><span data-stu-id="c9877-148">Property patterns</span></span>

<span data-ttu-id="c9877-149">El **patrón de propiedades** permite hallar la coincidencia con las propiedades del objeto examinado.</span><span class="sxs-lookup"><span data-stu-id="c9877-149">The **property pattern** enables you to match on properties of the object examined.</span></span> <span data-ttu-id="c9877-150">Considere un sitio de comercio electrónico que debe calcular los impuestos de ventas según la dirección del comprador.</span><span class="sxs-lookup"><span data-stu-id="c9877-150">Consider an eCommerce site that must compute sales tax based on the buyer's address.</span></span> <span data-ttu-id="c9877-151">Ese cálculo no es una responsabilidad fundamental de una clase `Address`.</span><span class="sxs-lookup"><span data-stu-id="c9877-151">That computation is not a core responsibility of an `Address` class.</span></span> <span data-ttu-id="c9877-152">Cambiará con el tiempo, probablemente con más frecuencia que el formato de dirección.</span><span class="sxs-lookup"><span data-stu-id="c9877-152">It will change over time, likely more often than address format changes.</span></span> <span data-ttu-id="c9877-153">El importe de los impuestos de ventas depende de la propiedad `State` de la dirección.</span><span class="sxs-lookup"><span data-stu-id="c9877-153">The amount of sales tax depends on the `State` property of the address.</span></span> <span data-ttu-id="c9877-154">El método siguiente usa el patrón de propiedades para calcular los impuestos de ventas a partir de la dirección y el precio:</span><span class="sxs-lookup"><span data-stu-id="c9877-154">The following method uses the property pattern to compute the sales tax from the address and the price:</span></span>

```csharp
public static decimal ComputeSalesTax(Address location, decimal salePrice) =>
    location switch
    {
        { State: "WA" } => salePrice * 0.06M,
        { State: "MN" } => salePrice * 0.75M,
        { State: "MI" } => salePrice * 0.05M,
        // other cases removed for brevity...
        _ => 0M
    };
```

<span data-ttu-id="c9877-155">La coincidencia de patrones crea una sintaxis concisa para expresar este algoritmo.</span><span class="sxs-lookup"><span data-stu-id="c9877-155">Pattern matching creates a concise syntax for expressing this algorithm.</span></span>

### <a name="tuple-patterns"></a><span data-ttu-id="c9877-156">Patrones de tupla</span><span class="sxs-lookup"><span data-stu-id="c9877-156">Tuple patterns</span></span>

<span data-ttu-id="c9877-157">Algunos algoritmos dependen de varias entradas.</span><span class="sxs-lookup"><span data-stu-id="c9877-157">Some algorithms depend on multiple inputs.</span></span> <span data-ttu-id="c9877-158">Los **patrones de tupla** permiten hacer cambios en función de varios valores, expresados como una [tupla](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="c9877-158">**Tuple patterns** allow you to switch based on multiple values expressed as a [tuple](../tuples.md).</span></span>  <span data-ttu-id="c9877-159">El código siguiente muestra una expresión switch del juego *piedra, papel, tijeras*:</span><span class="sxs-lookup"><span data-stu-id="c9877-159">The following code shows a switch expression for the game *rock, paper, scissors*:</span></span>

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

<span data-ttu-id="c9877-160">Los mensajes indican el ganador.</span><span class="sxs-lookup"><span data-stu-id="c9877-160">The messages indicate the winner.</span></span> <span data-ttu-id="c9877-161">El caso de descarte representa las tres combinaciones de valores equivalentes, u otras entradas de texto.</span><span class="sxs-lookup"><span data-stu-id="c9877-161">The discard case represents the three combinations for ties, or other text inputs.</span></span>

### <a name="positional-patterns"></a><span data-ttu-id="c9877-162">Patrones posicionales</span><span class="sxs-lookup"><span data-stu-id="c9877-162">Positional patterns</span></span>

<span data-ttu-id="c9877-163">Algunos tipos incluyen un método `Deconstruct` que deconstruye sus propiedades en variables discretas.</span><span class="sxs-lookup"><span data-stu-id="c9877-163">Some types include a `Deconstruct` method that deconstructs its properties into discrete variables.</span></span> <span data-ttu-id="c9877-164">Cuando un método `Deconstruct` es accesible, puede usar **patrones posicionales** para inspeccionar las propiedades del objeto y usar esas propiedades en un patrón.</span><span class="sxs-lookup"><span data-stu-id="c9877-164">When a `Deconstruct` method is accessible, you can use **positional patterns** to inspect properties of the object and use those properties for a pattern.</span></span>  <span data-ttu-id="c9877-165">Tenga en cuenta la siguiente clase `Point` que incluye un método `Deconstruct` con el objetivo de crear variables discretas para `X` y `Y`:</span><span class="sxs-lookup"><span data-stu-id="c9877-165">Consider the following `Point` class that includes a `Deconstruct` method to create discrete variables for `X` and `Y`:</span></span>

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

<span data-ttu-id="c9877-166">Además, tenga en cuenta la siguiente enumeración, que representa diversas posiciones de un cuadrante:</span><span class="sxs-lookup"><span data-stu-id="c9877-166">Additionally, consider the following enum that represents various positions of a quadrant:</span></span>

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

<span data-ttu-id="c9877-167">El método siguiente usa el **patrón posicional** para extraer los valores de `x` y `y`.</span><span class="sxs-lookup"><span data-stu-id="c9877-167">The following method uses the **positional pattern** to extract the values of `x` and `y`.</span></span> <span data-ttu-id="c9877-168">A continuación, usa una cláusula `when` para determinar el valor `Quadrant` del punto:</span><span class="sxs-lookup"><span data-stu-id="c9877-168">Then, it uses a `when` clause to determine the `Quadrant` of the point:</span></span>

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

<span data-ttu-id="c9877-169">El patrón de descarte del modificador anterior coincide cuando `x` o `y` es 0, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="c9877-169">The discard pattern in the preceding switch matches when either `x` or `y` is 0, but not both.</span></span> <span data-ttu-id="c9877-170">Una expresión switch debe generar un valor o producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="c9877-170">A switch expression must either produce a value or throw an exception.</span></span> <span data-ttu-id="c9877-171">Si ninguno de los casos coincide, la expresión switch produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="c9877-171">If none of the cases match, the switch expression throws an exception.</span></span> <span data-ttu-id="c9877-172">El compilador genera una advertencia si no cubre todos los posibles casos en la expresión switch.</span><span class="sxs-lookup"><span data-stu-id="c9877-172">The compiler generates a warning for you if you do not cover all possible cases in your switch expression.</span></span>

<span data-ttu-id="c9877-173">Puede explorar las técnicas de coincidencia de patrones en este [tutorial avanzado sobre la coincidencia de patrones](../tutorials/pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="c9877-173">You can explore pattern matching techniques in this [advanced tutorial on pattern matching](../tutorials/pattern-matching.md).</span></span>

## <a name="using-declarations"></a><span data-ttu-id="c9877-174">Declaraciones using</span><span class="sxs-lookup"><span data-stu-id="c9877-174">using declarations</span></span>

<span data-ttu-id="c9877-175">Una **declaración using** es una declaración de variable precedida por la palabra clave `using`.</span><span class="sxs-lookup"><span data-stu-id="c9877-175">A **using declaration** is a variable declaration preceded by the `using` keyword.</span></span> <span data-ttu-id="c9877-176">Indica al compilador que la variable que se declara debe eliminarse al final del ámbito de inclusión.</span><span class="sxs-lookup"><span data-stu-id="c9877-176">It tells the compiler that the variable being declared should be disposed at the end of the enclosing scope.</span></span> <span data-ttu-id="c9877-177">Por ejemplo, considere el siguiente código que escribe un archivo de texto:</span><span class="sxs-lookup"><span data-stu-id="c9877-177">For example, consider the following code that writes a text file:</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    foreach (string line in lines)
    {
        // If the line doesn't contain the word 'Second', write the line to the file.
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
    }
// file is disposed here
}
```

<span data-ttu-id="c9877-178">En el ejemplo anterior, el archivo se elimina cuando se alcanza la llave de cierre del método.</span><span class="sxs-lookup"><span data-stu-id="c9877-178">In the preceding example, the file is disposed when the closing brace for the method is reached.</span></span> <span data-ttu-id="c9877-179">Ese es el final del ámbito en el que se declara `file`.</span><span class="sxs-lookup"><span data-stu-id="c9877-179">That's the end of the scope in which `file` is declared.</span></span> <span data-ttu-id="c9877-180">El código anterior es equivalente al siguiente código que usa las [instrucciones using](../language-reference/keywords/using-statement.md) clásicas:</span><span class="sxs-lookup"><span data-stu-id="c9877-180">The preceding code is equivalent to the following code using the classic [using statements](../language-reference/keywords/using-statement.md) statement:</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        foreach (string line in lines)
        {
            // If the line doesn't contain the word 'Second', write the line to the file.
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
        }
    } // file is disposed here
}
```

<span data-ttu-id="c9877-181">En el ejemplo anterior, el archivo se elimina cuando se alcanza la llave de cierre asociada con la instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="c9877-181">In the preceding example, the file is disposed when the closing brace associated with the `using` statement is reached.</span></span>

<span data-ttu-id="c9877-182">En ambos casos, el compilador genera la llamada a `Dispose()`.</span><span class="sxs-lookup"><span data-stu-id="c9877-182">In both cases, the compiler generates the call to `Dispose()`.</span></span> <span data-ttu-id="c9877-183">El compilador genera un error si la expresión de la instrucción using no se puede eliminar.</span><span class="sxs-lookup"><span data-stu-id="c9877-183">The compiler generates an error if the expression in the using statement is not disposable.</span></span>

## <a name="static-local-functions"></a><span data-ttu-id="c9877-184">Funciones locales estáticas</span><span class="sxs-lookup"><span data-stu-id="c9877-184">Static local functions</span></span>

<span data-ttu-id="c9877-185">Ahora puede agregar el modificador `static` a funciones locales para asegurarse de que la función local no captura (hace referencia a) las variables del ámbito de inclusión.</span><span class="sxs-lookup"><span data-stu-id="c9877-185">You can now add the `static` modifier to local functions to ensure that local function doesn't capture (reference) any variables from the enclosing scope.</span></span> <span data-ttu-id="c9877-186">Si lo hace, se generará un error `CS8421` en el que se indicará que una función local estática no puede contener una referencia a \<variable>.</span><span class="sxs-lookup"><span data-stu-id="c9877-186">Doing so generates `CS8421`, "A static local function can't contain a reference to \<variable>."</span></span> 

<span data-ttu-id="c9877-187">Observe el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c9877-187">Consider the following code.</span></span> <span data-ttu-id="c9877-188">La función local `LocalFunction` accede a la variable `y`, declarada en el ámbito de inclusión (el método `M`).</span><span class="sxs-lookup"><span data-stu-id="c9877-188">The local function `LocalFunction` accesses the variable `y`, declared in the enclosing scope (the method `M`).</span></span> <span data-ttu-id="c9877-189">Por lo tanto, `LocalFunction` no se puede declarar con el modificador `static`:</span><span class="sxs-lookup"><span data-stu-id="c9877-189">Therefore, `LocalFunction` can't be declared with the `static` modifier:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="c9877-190">El código siguiente contiene una función local estática.</span><span class="sxs-lookup"><span data-stu-id="c9877-190">The following code contains a static local function.</span></span> <span data-ttu-id="c9877-191">Puede ser estática porque no accede a las variables del ámbito de inclusión:</span><span class="sxs-lookup"><span data-stu-id="c9877-191">It can be static because it doesn't access any variables in the enclosing scope:</span></span>

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a><span data-ttu-id="c9877-192">Estructuras ref descartables</span><span class="sxs-lookup"><span data-stu-id="c9877-192">Disposable ref structs</span></span>

<span data-ttu-id="c9877-193">Un elemento `struct` declarado con el modificador `ref` no puede implementar ninguna interfaz y, por tanto, no puede implementar <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="c9877-193">A `struct` declared with the `ref` modifier may not implement any interfaces and so cannot implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="c9877-194">Por lo tanto, para permitir que se elimine un elemento `ref struct`, debe tener un método `void Dispose()` accesible.</span><span class="sxs-lookup"><span data-stu-id="c9877-194">Therefore, to enable a `ref struct` to be disposed, it must have an accessible `void Dispose()` method.</span></span> <span data-ttu-id="c9877-195">Esto también se aplica a las declaraciones `readonly ref struct`.</span><span class="sxs-lookup"><span data-stu-id="c9877-195">This also applies to `readonly ref struct` declarations.</span></span>

## <a name="nullable-reference-types"></a><span data-ttu-id="c9877-196">Tipos de referencia que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="c9877-196">Nullable reference types</span></span>

<span data-ttu-id="c9877-197">Dentro de un contexto de anotación que acepta valores NULL, cualquier variable de un tipo de referencia se considera un **tipo de referencia que no acepta valores NULL**.</span><span class="sxs-lookup"><span data-stu-id="c9877-197">Inside a nullable annotation context, any variable of a reference type is considered to be a **nonnullable reference type**.</span></span> <span data-ttu-id="c9877-198">Si quiere indicar que una variable puede ser NULL, debe anexar `?` al nombre del tipo para declarar la variable como un **tipo de referencia que acepta valores NULL**.</span><span class="sxs-lookup"><span data-stu-id="c9877-198">If you want to indicate that a variable may be null, you must append the type name with the `?` to declare the variable as a **nullable reference type**.</span></span>

<span data-ttu-id="c9877-199">En los tipos de referencia que no aceptan valores NULL, el compilador usa el análisis de flujo para garantizar que las variables locales se inicializan en un valor no NULL cuando se declaran.</span><span class="sxs-lookup"><span data-stu-id="c9877-199">For nonnullable reference types, the compiler uses flow analysis to ensure that local variables are initialized to a non-null value when declared.</span></span> <span data-ttu-id="c9877-200">Los campos se deben inicializar durante la construcción.</span><span class="sxs-lookup"><span data-stu-id="c9877-200">Fields must be initialized during construction.</span></span> <span data-ttu-id="c9877-201">Si la variable no se establece mediante una llamada a alguno de los constructores disponibles o por medio de un inicializador, el compilador genera una advertencia.</span><span class="sxs-lookup"><span data-stu-id="c9877-201">The compiler generates a warning if the variable is not set by a call to any of the available constructors or by an initializer.</span></span> <span data-ttu-id="c9877-202">Además, los tipos de referencia que no aceptan valores NULL no pueden tener asignado un valor que podría ser NULL.</span><span class="sxs-lookup"><span data-stu-id="c9877-202">Furthermore, nonnullable reference types can't be assigned a value that could be null.</span></span>

<span data-ttu-id="c9877-203">Los tipos de referencia que aceptan valores NULL no se comprueban para garantizar que se asignan o inicializan como NULL.</span><span class="sxs-lookup"><span data-stu-id="c9877-203">Nullable reference types aren't checked to ensure they aren't assigned or initialized to null.</span></span> <span data-ttu-id="c9877-204">Sin embargo, el compilador usa el análisis de flujo para garantizar que cualquier variable de un tipo de referencia que acepta valores NULL se compara con NULL antes de acceder a ella o de asignarse a un tipo de referencia que no los acepta.</span><span class="sxs-lookup"><span data-stu-id="c9877-204">However, the compiler uses flow analysis to ensure that any variable of a nullable reference type is checked against null before it's accessed or assigned to a nonnullable reference type.</span></span>

<span data-ttu-id="c9877-205">Puede aprender más sobre la característica en la introducción a los [tipos de referencia que aceptan valores NULL](../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="c9877-205">You can learn more about the feature in the overview of [nullable reference types](../nullable-references.md).</span></span> <span data-ttu-id="c9877-206">Pruébela por su cuenta en una nueva aplicación en este [tutorial de tipos de referencia que aceptan valores NULL](../tutorials/nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="c9877-206">Try it yourself in a new application in this [nullable reference types tutorial](../tutorials/nullable-reference-types.md).</span></span> <span data-ttu-id="c9877-207">Puede encontrar más información sobre los pasos para migrar una base de código existente para hacer uso de los tipos de referencia que aceptan valores NULL en el [tutorial sobre la migración de una aplicación para usar tipos de referencia que aceptan valores NULL](../tutorials/upgrade-to-nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="c9877-207">Learn about the steps to migrate an existing codebase to make use of nullable reference types in the [migrating an application to use nullable reference types tutorial](../tutorials/upgrade-to-nullable-references.md).</span></span>

## <a name="asynchronous-streams"></a><span data-ttu-id="c9877-208">Secuencias asincrónicas</span><span class="sxs-lookup"><span data-stu-id="c9877-208">Asynchronous streams</span></span>

<span data-ttu-id="c9877-209">A partir de C# 8.0, puede crear y consumir secuencias de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="c9877-209">Starting with C# 8.0, you can create and consume streams asynchronously.</span></span> <span data-ttu-id="c9877-210">Un método que devuelve una secuencia asincrónica tiene tres propiedades:</span><span class="sxs-lookup"><span data-stu-id="c9877-210">A method that returns an asynchronous stream has three properties:</span></span>

1. <span data-ttu-id="c9877-211">Se declara con el modificador `async`.</span><span class="sxs-lookup"><span data-stu-id="c9877-211">It's declared with the `async` modifier.</span></span>
1. <span data-ttu-id="c9877-212">Devuelve <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="c9877-212">It returns an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span>
1. <span data-ttu-id="c9877-213">El método contiene instrucciones `yield return` que devuelven elementos sucesivos de la secuencia asincrónica.</span><span class="sxs-lookup"><span data-stu-id="c9877-213">The method contains `yield return` statements to return successive elements in the asynchronous stream.</span></span>

<span data-ttu-id="c9877-214">Para consumir una secuencia asincrónica es necesario agregar la palabra clave `await` delante de la palabra clave `foreach` al enumerar los elementos de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="c9877-214">Consuming an asynchronous stream requires you to add the `await` keyword before the `foreach` keyword when you enumerate the elements of the stream.</span></span> <span data-ttu-id="c9877-215">Para agregar la palabra clave `await` es necesario declarar el método que enumera la secuencia asincrónica con el modificador `async` y devolver un tipo permitido para un método `async`.</span><span class="sxs-lookup"><span data-stu-id="c9877-215">Adding the `await` keyword requires the method that enumerates the asynchronous stream to be declared with the `async` modifier and to return a type allowed for an `async` method.</span></span> <span data-ttu-id="c9877-216">Normalmente, esto significa devolver <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="c9877-216">Typically that means returning a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="c9877-217">También puede ser <xref:System.Threading.Tasks.ValueTask> o <xref:System.Threading.Tasks.ValueTask%601>.</span><span class="sxs-lookup"><span data-stu-id="c9877-217">It can also be a <xref:System.Threading.Tasks.ValueTask> or <xref:System.Threading.Tasks.ValueTask%601>.</span></span> <span data-ttu-id="c9877-218">Un método puede consumir y producir una secuencia asincrónica, lo que significa que devolvería <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="c9877-218">A method can both consume and produce an asynchronous stream, which means it would return an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span> <span data-ttu-id="c9877-219">El siguiente código genera una secuencia de 0 a 19, con una espera de 100 ms entre la generación de cada número:</span><span class="sxs-lookup"><span data-stu-id="c9877-219">The following code generates a sequence from 0 to 19, waiting 100 ms between generating each number:</span></span>

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

<span data-ttu-id="c9877-220">Se enumeraría la secuencia mediante la instrucción `await foreach`:</span><span class="sxs-lookup"><span data-stu-id="c9877-220">You would enumerate the sequence using the `await foreach` statement:</span></span>

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

<span data-ttu-id="c9877-221">Puede probar secuencias asincrónicas por su cuenta en nuestro tutorial sobre la [creación y consumo de secuencias asincrónicas](../tutorials/generate-consume-asynchronous-stream.md).</span><span class="sxs-lookup"><span data-stu-id="c9877-221">You can try asynchronous streams yourself in our tutorial on [creating and consuming async streams](../tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="indices-and-ranges"></a><span data-ttu-id="c9877-222">Índices y rangos</span><span class="sxs-lookup"><span data-stu-id="c9877-222">Indices and ranges</span></span>

<span data-ttu-id="c9877-223">Los rangos e índices proporcionan una sintaxis concisa para especificar subrangos en una matriz, <xref:System.Span%601>, o <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="c9877-223">Ranges and indices provide a succinct syntax for specifying subranges in an array, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span>

<span data-ttu-id="c9877-224">Puede especificar un índice **desde el final**.</span><span class="sxs-lookup"><span data-stu-id="c9877-224">You can specify an index **from the end**.</span></span> <span data-ttu-id="c9877-225">Para especificar **desde el final**, puede usar el operador `^`.</span><span class="sxs-lookup"><span data-stu-id="c9877-225">You specify **from the end** using the `^` operator.</span></span> <span data-ttu-id="c9877-226">Está familiarizado con `array[2]` lo que significa el elemento "2 desde el principio".</span><span class="sxs-lookup"><span data-stu-id="c9877-226">You are familiar with `array[2]` meaning the element "2 from the start".</span></span> <span data-ttu-id="c9877-227">Ahora, `array[^2]` significa el elemento "2 desde el final".</span><span class="sxs-lookup"><span data-stu-id="c9877-227">Now, `array[^2]` means the element "2 from the end".</span></span> <span data-ttu-id="c9877-228">El índice `^0` significa "el final" o el índice que sigue al último elemento.</span><span class="sxs-lookup"><span data-stu-id="c9877-228">The index `^0` means "the end", or the index that follows the last element.</span></span>

<span data-ttu-id="c9877-229">Puede especificar un **rango** con el **operador de rango**: `..`.</span><span class="sxs-lookup"><span data-stu-id="c9877-229">You can specify a **range** with the **range operator**: `..`.</span></span> <span data-ttu-id="c9877-230">Por ejemplo, `0..^0` especifica el rango completo de la matriz: 0 desde el principio hasta, pero sin incluir 0 desde el final.</span><span class="sxs-lookup"><span data-stu-id="c9877-230">For example, `0..^0` specifies the entire range of the array: 0 from the start up to, but not including 0 from the end.</span></span> <span data-ttu-id="c9877-231">Cualquier operando puede usar "desde el principio" o "desde el final".</span><span class="sxs-lookup"><span data-stu-id="c9877-231">Either operand may use "from the start" or "from the end".</span></span> <span data-ttu-id="c9877-232">Además, se puede omitir cualquier operando.</span><span class="sxs-lookup"><span data-stu-id="c9877-232">Furthermore, either operand may be omitted.</span></span> <span data-ttu-id="c9877-233">Los valores predeterminados son `0` para el índice de inicio y `^0` para el índice de final.</span><span class="sxs-lookup"><span data-stu-id="c9877-233">The defaults are `0` for the start index, and `^0` for the end index.</span></span>

<span data-ttu-id="c9877-234">Veamos algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c9877-234">Let's look at a few examples.</span></span> <span data-ttu-id="c9877-235">Tenga en cuenta la siguiente matriz, anotada con su índice desde el principio y desde el final:</span><span class="sxs-lookup"><span data-stu-id="c9877-235">Consider the following array, annotated with its index from the start and from the end:</span></span>

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
};
```

<span data-ttu-id="c9877-236">El índice de cada elemento refuerza el concepto de "desde el inicio" y "desde el final", y que los rangos son exclusivos del final del rango.</span><span class="sxs-lookup"><span data-stu-id="c9877-236">The index of each element reinforces the concept of "from the start", and "from the end", and that ranges are exclusive of the end of the range.</span></span> <span data-ttu-id="c9877-237">El "inicio" de toda la matriz es el primer elemento.</span><span class="sxs-lookup"><span data-stu-id="c9877-237">The "start" of the entire array is the first element.</span></span> <span data-ttu-id="c9877-238">El "final" de toda la matriz es *pasado* el último elemento.</span><span class="sxs-lookup"><span data-stu-id="c9877-238">The "end" of the entire array is *past* the last element.</span></span>

<span data-ttu-id="c9877-239">Puede recuperar la última palabra con el índice `^1`:</span><span class="sxs-lookup"><span data-stu-id="c9877-239">You can retrieve the last word with the `^1` index:</span></span>

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

<span data-ttu-id="c9877-240">El siguiente código crea un subrango con las palabras "quick", "brown" y "fox".</span><span class="sxs-lookup"><span data-stu-id="c9877-240">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="c9877-241">Va de `words[1]` a `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="c9877-241">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="c9877-242">El elemento `words[4]` no está en el rango.</span><span class="sxs-lookup"><span data-stu-id="c9877-242">The element `words[4]` is not in the range.</span></span>

```csharp
var quickBrownFox = words[1..4];
```

<span data-ttu-id="c9877-243">El siguiente código crea un subrango con "lazy" y "dog".</span><span class="sxs-lookup"><span data-stu-id="c9877-243">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="c9877-244">Incluye `words[^2]` y `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="c9877-244">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="c9877-245">El índice del final `words[^0]` no se incluye:</span><span class="sxs-lookup"><span data-stu-id="c9877-245">The end index `words[^0]` is not included:</span></span>

```csharp
var lazyDog = words[^2..^0];
```

<span data-ttu-id="c9877-246">En los ejemplos siguientes se crean rangos con final abierto para el inicio, el final o ambos:</span><span class="sxs-lookup"><span data-stu-id="c9877-246">The following examples create ranges that are open ended for the start, end, or both:</span></span>

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the, "lazy" and "dog"
```

<span data-ttu-id="c9877-247">También puede declarar rangos como variables:</span><span class="sxs-lookup"><span data-stu-id="c9877-247">You can also declare ranges as variables:</span></span>

```csharp
Range phrase = 1..4;
```

<span data-ttu-id="c9877-248">El rango se puede usar luego dentro de los caracteres `[` y `]`:</span><span class="sxs-lookup"><span data-stu-id="c9877-248">The range can then be used inside the `[` and `]` characters:</span></span>

```csharp
var text = words[phrase];
```
