---
title: Elección entre tipos anónimos y de tupla
description: Obtenga información sobre Cuándo es adecuado elegir entre tipos anónimos y tipo de tupla.
ms.date: 06/29/2020
ms.technology: dotnet-standard
ms.openlocfilehash: bc17695830a42a6eed9d60c0e097ee9d02a7957e
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803773"
---
# <a name="choosing-between-anonymous-and-tuple-types"></a><span data-ttu-id="8225e-103">Elección entre tipos anónimos y de tupla</span><span class="sxs-lookup"><span data-stu-id="8225e-103">Choosing between anonymous and tuple types</span></span>

<span data-ttu-id="8225e-104">La elección del tipo adecuado implica tener en cuenta su facilidad de uso, rendimiento y contrapartidas en comparación con otros tipos.</span><span class="sxs-lookup"><span data-stu-id="8225e-104">Choosing the appropriate type involves considering its usability, performance, and tradeoffs compared to other types.</span></span> <span data-ttu-id="8225e-105">Los tipos anónimos están disponibles desde C# 3,0, mientras que los tipos genéricos <xref:System.Tuple%602?displayProperty=nameWithType> se introdujeron con .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="8225e-105">Anonymous types have been available since C# 3.0, while generic <xref:System.Tuple%602?displayProperty=nameWithType> types were introduced with .NET Framework 4.0.</span></span> <span data-ttu-id="8225e-106">Dado que se han incorporado nuevas opciones con compatibilidad de nivel de lenguaje, como <xref:System.ValueTuple%602?displayProperty=nameWithType> la que indica el nombre, proporcione un tipo de valor con la flexibilidad de los tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="8225e-106">Since then new options have been introduced with language level support, such as <xref:System.ValueTuple%602?displayProperty=nameWithType> - which as the name implies, provide a value type with the flexibility of anonymous types.</span></span> <span data-ttu-id="8225e-107">En este artículo, aprenderá Cuándo es adecuado elegir un tipo sobre el otro.</span><span class="sxs-lookup"><span data-stu-id="8225e-107">In this article, you'll learn when it's appropriate to choose one type over the other.</span></span>

## <a name="usability-and-functionality"></a><span data-ttu-id="8225e-108">Facilidad de uso y funcionalidad</span><span class="sxs-lookup"><span data-stu-id="8225e-108">Usability and functionality</span></span>

<span data-ttu-id="8225e-109">Los tipos anónimos se introdujeron en C# 3,0 con expresiones Language-Integrated Query (LINQ).</span><span class="sxs-lookup"><span data-stu-id="8225e-109">Anonymous types were introduced in C# 3.0 with Language-Integrated Query (LINQ) expressions.</span></span> <span data-ttu-id="8225e-110">Con LINQ, los desarrolladores suelen proyectar los resultados de las consultas en tipos anónimos que contienen algunas propiedades de selección de los objetos con los que están trabajando.</span><span class="sxs-lookup"><span data-stu-id="8225e-110">With LINQ, developers often project results from queries into anonymous types that hold a few select properties from the objects they're working with.</span></span> <span data-ttu-id="8225e-111">Considere el ejemplo siguiente, que crea una instancia de una matriz de <xref:System.DateTime> objetos y recorre en iteración los proyectos en un tipo anónimo con dos propiedades.</span><span class="sxs-lookup"><span data-stu-id="8225e-111">Consider the following example, that instantiates an array of <xref:System.DateTime> objects, and iterates through them projecting into an anonymous type with two properties.</span></span>

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var anonymous in
             dates.Select(
                 date => new { Formatted = $"{date:MMM dd, yyyy hh:mm zzz}", date.Ticks }))
{
    Console.WriteLine($"Ticks: {anonymous.Ticks}, formatted: {anonymous.Formatted}");
}
```

<span data-ttu-id="8225e-112">Las instancias de los tipos anónimos se crean mediante el [`new`](../../csharp/language-reference/operators/new-operator.md) operador, y los nombres y tipos de propiedad se deducen a partir de la declaración.</span><span class="sxs-lookup"><span data-stu-id="8225e-112">Anonymous types are instantiated by using the [`new`](../../csharp/language-reference/operators/new-operator.md) operator, and the property names and types are inferred from the declaration.</span></span> <span data-ttu-id="8225e-113">Si dos o más inicializadores de objeto anónimo en el mismo ensamblado especifican una secuencia de propiedades que están en el mismo orden y que tienen los mismos nombres y tipos, el compilador trata los objetos como instancias del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="8225e-113">If two or more anonymous object initializers in the same assembly specify a sequence of properties that are in the same order and that have the same names and types, the compiler treats the objects as instances of the same type.</span></span> <span data-ttu-id="8225e-114">Comparten la misma información de tipo generada por el compilador.</span><span class="sxs-lookup"><span data-stu-id="8225e-114">They share the same compiler-generated type information.</span></span>

<span data-ttu-id="8225e-115">El fragmento de código de C# anterior proyecta un tipo anónimo con dos propiedades, de forma similar a la siguiente clase C# generada por el compilador:</span><span class="sxs-lookup"><span data-stu-id="8225e-115">The previous C# snippet projects an anonymous type with two properties, much like the following compiler-generated C# class:</span></span>

```csharp
internal sealed class f__AnonymousType0
{
    public string Formatted { get; }
    public long Ticks { get; }

    public f__AnonymousType0(string formatted, long ticks)
    {
        Formatted = formatted;
        Ticks = ticks;
    }
}
```

<span data-ttu-id="8225e-116">Para obtener más información, vea [tipos anónimos](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="8225e-116">For more information, see [anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="8225e-117">Existe la misma funcionalidad con tuplas al proyectar en consultas LINQ, puede seleccionar Propiedades en tuplas.</span><span class="sxs-lookup"><span data-stu-id="8225e-117">The same functionality exists with tuples when projecting into LINQ queries, you can select properties into tuples.</span></span> <span data-ttu-id="8225e-118">Estas tuplas fluyen a través de la consulta, de la misma forma que los tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="8225e-118">These tuples flow through the query, just as anonymous types would.</span></span> <span data-ttu-id="8225e-119">Ahora, considere el siguiente ejemplo usando `System.Tuple<string, long>` .</span><span class="sxs-lookup"><span data-stu-id="8225e-119">Now consider the following example using the `System.Tuple<string, long>`.</span></span>

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var tuple in
            dates.Select(
                date => new Tuple<string, long>($"{date:MMM dd, yyyy hh:mm zzz}", date.Ticks)))
{
    Console.WriteLine($"Ticks: {tuple.Item2}, formatted: {tuple.Item1}");
}
```

<span data-ttu-id="8225e-120">Con <xref:System.Tuple%602?displayProperty=nameWithType> , la instancia de expone propiedades de elementos numeradas, como `Item1` y `Item2` .</span><span class="sxs-lookup"><span data-stu-id="8225e-120">With the <xref:System.Tuple%602?displayProperty=nameWithType>, the instance exposes numbered item properties, such as `Item1`, and `Item2`.</span></span> <span data-ttu-id="8225e-121">Estos nombres de propiedad pueden dificultar la comprensión de la intención de los valores de propiedad, ya que el nombre de la propiedad solo proporciona el ordinal.</span><span class="sxs-lookup"><span data-stu-id="8225e-121">These property names can make it more difficult to understand the intent of the property values, as the property name only provides the ordinal.</span></span> <span data-ttu-id="8225e-122">Además, los `System.Tuple` tipos son tipos de referencia `class` .</span><span class="sxs-lookup"><span data-stu-id="8225e-122">Furthermore, the `System.Tuple` types are reference `class` types.</span></span> <span data-ttu-id="8225e-123"><xref:System.ValueTuple%602?displayProperty=nameWithType>Sin embargo, es un tipo de valor `struct` .</span><span class="sxs-lookup"><span data-stu-id="8225e-123">The <xref:System.ValueTuple%602?displayProperty=nameWithType> however, is a value `struct` type.</span></span> <span data-ttu-id="8225e-124">En el siguiente fragmento de código de C#, `ValueTuple<string, long>` se usa para proyectar en.</span><span class="sxs-lookup"><span data-stu-id="8225e-124">The following C# snippet, uses `ValueTuple<string, long>` to project into.</span></span> <span data-ttu-id="8225e-125">Al hacerlo, se asigna mediante una sintaxis literal.</span><span class="sxs-lookup"><span data-stu-id="8225e-125">In doing so, it assigns using a literal syntax.</span></span>

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var (formatted, ticks) in
            dates.Select(
                date => (Formatted: $"{date:MMM dd, yyyy at hh:mm zzz}", date.Ticks)))
{
    Console.WriteLine($"Ticks: {ticks}, formatted: {formatted}");
}
```

<span data-ttu-id="8225e-126">C# proporciona compatibilidad de lenguajes de tuplas con el <xref:System.ValueTuple> tipo y la semántica para:</span><span class="sxs-lookup"><span data-stu-id="8225e-126">C# provides language support of tuples with the <xref:System.ValueTuple> type, and semantics for:</span></span>

- [<span data-ttu-id="8225e-127">Asignación de tupla</span><span class="sxs-lookup"><span data-stu-id="8225e-127">Tuple assignment</span></span>](../../csharp/tuples.md#assignment-and-tuples)
- <span data-ttu-id="8225e-128">[Desconstrucción de tuplas](../../csharp/deconstruct.md) (no limitadas a tuplas)</span><span class="sxs-lookup"><span data-stu-id="8225e-128">[Tuple deconstruction](../../csharp/deconstruct.md) (not limited to tuples)</span></span>
- [<span data-ttu-id="8225e-129">Comprobaciones de igualdad de tupla</span><span class="sxs-lookup"><span data-stu-id="8225e-129">Tuple equality checks</span></span>](../../csharp/tuples.md#equality-and-tuples)
- [<span data-ttu-id="8225e-130">Inicializadores de proyección de tupla</span><span class="sxs-lookup"><span data-stu-id="8225e-130">Tuple projection initializers</span></span>](../../csharp/tuples.md#tuple-projection-initializers)

<span data-ttu-id="8225e-131">Sin embargo, los ejemplos anteriores son funcionalmente equivalentes; hay ligeras diferencias en su facilidad de uso y sus implementaciones subyacentes.</span><span class="sxs-lookup"><span data-stu-id="8225e-131">The previous examples are all functionally equivalent, however; there are slight differences in their usability and their underlying implementations.</span></span>

## <a name="tradeoffs"></a><span data-ttu-id="8225e-132">Compromisos</span><span class="sxs-lookup"><span data-stu-id="8225e-132">Tradeoffs</span></span>

<span data-ttu-id="8225e-133">Es posible que desee usar siempre <xref:System.ValueTuple> los <xref:System.Tuple> tipos en y anónimos, pero hay que tener en cuenta los inconvenientes.</span><span class="sxs-lookup"><span data-stu-id="8225e-133">You might want to always use <xref:System.ValueTuple> over <xref:System.Tuple>, and anonymous types, but there are tradeoffs you should consider.</span></span> <span data-ttu-id="8225e-134">Los <xref:System.ValueTuple> tipos son mutables, mientras que <xref:System.Tuple> son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="8225e-134">The <xref:System.ValueTuple> types are mutable, whereas <xref:System.Tuple> are read-only.</span></span> <span data-ttu-id="8225e-135">Los tipos anónimos se pueden usar en los árboles de expresión, mientras que las tuplas no pueden.</span><span class="sxs-lookup"><span data-stu-id="8225e-135">Anonymous types can be used in expression trees, while tuples cannot.</span></span> <span data-ttu-id="8225e-136">En la tabla siguiente se presenta una visión general de algunas de las diferencias clave.</span><span class="sxs-lookup"><span data-stu-id="8225e-136">The following table is an overview of some of the key differences.</span></span>

### <a name="key-differences"></a><span data-ttu-id="8225e-137">Diferencias clave</span><span class="sxs-lookup"><span data-stu-id="8225e-137">Key differences</span></span>

| <span data-ttu-id="8225e-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="8225e-138">Name</span></span>                     | <span data-ttu-id="8225e-139">Modificador de acceso</span><span class="sxs-lookup"><span data-stu-id="8225e-139">Access modifier</span></span> | <span data-ttu-id="8225e-140">Tipo</span><span class="sxs-lookup"><span data-stu-id="8225e-140">Type</span></span>     | <span data-ttu-id="8225e-141">Nombre de propiedad personalizada</span><span class="sxs-lookup"><span data-stu-id="8225e-141">Custom property name</span></span> | <span data-ttu-id="8225e-142">Compatibilidad con la desconstrucción</span><span class="sxs-lookup"><span data-stu-id="8225e-142">Deconstruction support</span></span> | <span data-ttu-id="8225e-143">Compatibilidad con árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="8225e-143">Expression tree support</span></span> |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| <span data-ttu-id="8225e-144">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="8225e-144">Anonymous types</span></span>          | `internal`      | `class`  | <span data-ttu-id="8225e-145">✔️</span><span class="sxs-lookup"><span data-stu-id="8225e-145">✔️</span></span>                   | ❌                     | <span data-ttu-id="8225e-146">✔️</span><span class="sxs-lookup"><span data-stu-id="8225e-146">✔️</span></span>                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | <span data-ttu-id="8225e-147">✔️</span><span class="sxs-lookup"><span data-stu-id="8225e-147">✔️</span></span>                     |
| <xref:System.ValueTuple> | `public`        | `struct` | <span data-ttu-id="8225e-148">✔️</span><span class="sxs-lookup"><span data-stu-id="8225e-148">✔️</span></span>                   | <span data-ttu-id="8225e-149">✔️</span><span class="sxs-lookup"><span data-stu-id="8225e-149">✔️</span></span>                     | ❌                     |

### <a name="serialization"></a><span data-ttu-id="8225e-150">Serialización</span><span class="sxs-lookup"><span data-stu-id="8225e-150">Serialization</span></span>

<span data-ttu-id="8225e-151">Una consideración importante a la hora de elegir un tipo es si se debe serializar o no.</span><span class="sxs-lookup"><span data-stu-id="8225e-151">One important consideration when choosing a type, is whether or not it will need to be serialized.</span></span> <span data-ttu-id="8225e-152">La serialización es el proceso de convertir el estado de un objeto en un formato que se pueda almacenar o transportar.</span><span class="sxs-lookup"><span data-stu-id="8225e-152">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="8225e-153">Para obtener más información, vea [serialización](../../csharp/programming-guide/concepts/serialization/index.md).</span><span class="sxs-lookup"><span data-stu-id="8225e-153">For more information, see [serialization](../../csharp/programming-guide/concepts/serialization/index.md).</span></span> <span data-ttu-id="8225e-154">Cuando la serialización es importante, `class` se prefiere crear un o `struct` a través de tipos anónimos o tipos de tupla.</span><span class="sxs-lookup"><span data-stu-id="8225e-154">When serialization is important, creating a `class` or `struct` is preferred over anonymous types or tuple types.</span></span>

## <a name="performance"></a><span data-ttu-id="8225e-155">Rendimiento</span><span class="sxs-lookup"><span data-stu-id="8225e-155">Performance</span></span>

<span data-ttu-id="8225e-156">El rendimiento entre estos tipos depende del escenario.</span><span class="sxs-lookup"><span data-stu-id="8225e-156">Performance between these types depends on the scenario.</span></span> <span data-ttu-id="8225e-157">El mayor impacto implica el equilibrio entre las asignaciones y la copia.</span><span class="sxs-lookup"><span data-stu-id="8225e-157">The major impact involves the tradeoff between allocations and copying.</span></span> <span data-ttu-id="8225e-158">En la mayoría de los escenarios, el impacto es pequeño.</span><span class="sxs-lookup"><span data-stu-id="8225e-158">In most scenarios, the impact is small.</span></span> <span data-ttu-id="8225e-159">Cuando pudieran surgir impactos importantes, se deben tomar medidas para informar sobre la decisión.</span><span class="sxs-lookup"><span data-stu-id="8225e-159">When major impacts could arise, measurements should be taken to inform the decision.</span></span>

## <a name="conclusion"></a><span data-ttu-id="8225e-160">Conclusión</span><span class="sxs-lookup"><span data-stu-id="8225e-160">Conclusion</span></span>

<span data-ttu-id="8225e-161">Como desarrollador que elige entre tuplas y tipos anónimos, debe tener en cuenta varios factores.</span><span class="sxs-lookup"><span data-stu-id="8225e-161">As a developer choosing between tuples and anonymous types, there are several factors to consider.</span></span> <span data-ttu-id="8225e-162">En general, si no está trabajando con [árboles de expresión](../../csharp/expression-trees.md)y está familiarizado con la sintaxis de tupla, elija a <xref:System.ValueTuple> medida que proporcionan un tipo de valor con la flexibilidad para asignar nombres a las propiedades.</span><span class="sxs-lookup"><span data-stu-id="8225e-162">Generally speaking, if you're not working with [expression trees](../../csharp/expression-trees.md), and you're comfortable with tuple syntax then choose <xref:System.ValueTuple> as they provide a value type with the flexibility to name properties.</span></span> <span data-ttu-id="8225e-163">Si está trabajando con árboles de expresión y prefiere asignar un nombre a las propiedades, elija tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="8225e-163">If you're working with expression trees, and you'd prefer to name properties, choose anonymous types.</span></span> <span data-ttu-id="8225e-164">De lo contrario, use <xref:System.Tuple>.</span><span class="sxs-lookup"><span data-stu-id="8225e-164">Otherwise, use <xref:System.Tuple>.</span></span>

## <a name="see-also"></a><span data-ttu-id="8225e-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="8225e-165">See also</span></span>

- <span data-ttu-id="8225e-166">[Tipos anónimos (Guía de programación de C#)](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="8225e-166">[Anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)</span></span>
- [<span data-ttu-id="8225e-167">Árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="8225e-167">Expression trees</span></span>](../../csharp/expression-trees.md)
- [<span data-ttu-id="8225e-168">Instrucciones de diseño de los marcos</span><span class="sxs-lookup"><span data-stu-id="8225e-168">Framework design guidelines</span></span>](index.md)
- [<span data-ttu-id="8225e-169">Tipos de tupla</span><span class="sxs-lookup"><span data-stu-id="8225e-169">Tuple types</span></span>](../../csharp/tuples.md)
- [<span data-ttu-id="8225e-170">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="8225e-170">Type design guidelines</span></span>](type.md)
