---
title: Elección entre tipos de tupla y anónimos
description: Obtenga información sobre cuándo es adecuado elegir entre los tipos anónimos y sobre los tipos de tupla.
ms.date: 07/01/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 24ab770d709b9f3968f4c7fe4b01eb0729dbd751
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853990"
---
# <a name="choosing-between-anonymous-and-tuple-types"></a><span data-ttu-id="3736b-103">Elección entre tipos de tupla y anónimos</span><span class="sxs-lookup"><span data-stu-id="3736b-103">Choosing between anonymous and tuple types</span></span>

<span data-ttu-id="3736b-104">A la hora de elegir el tipo adecuado, hay que tener en cuenta su usabilidad, su rendimiento y sus compensaciones en comparación con otros tipos.</span><span class="sxs-lookup"><span data-stu-id="3736b-104">Choosing the appropriate type involves considering its usability, performance, and tradeoffs compared to other types.</span></span> <span data-ttu-id="3736b-105">Los tipos anónimos están disponibles desde la versión 3.0 de C#, mientras que los tipos <xref:System.Tuple%602?displayProperty=nameWithType> genéricos se introdujeron con .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="3736b-105">Anonymous types have been available since C# 3.0, while generic <xref:System.Tuple%602?displayProperty=nameWithType> types were introduced with .NET Framework 4.0.</span></span> <span data-ttu-id="3736b-106">Ya que se han incorporado nuevas opciones con compatibilidad de lenguaje, como <xref:System.ValueTuple%602?displayProperty=nameWithType>, que, como indica su nombre, proporciona un tipo de valor con la flexibilidad de los tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="3736b-106">Since then new options have been introduced with language level support, such as <xref:System.ValueTuple%602?displayProperty=nameWithType> - which as the name implies, provide a value type with the flexibility of anonymous types.</span></span> <span data-ttu-id="3736b-107">En este artículo aprenderá cuándo es pertinente elegir un tipo en lugar de otro.</span><span class="sxs-lookup"><span data-stu-id="3736b-107">In this article, you'll learn when it's appropriate to choose one type over the other.</span></span>

## <a name="usability-and-functionality"></a><span data-ttu-id="3736b-108">Usabilidad y funcionalidad</span><span class="sxs-lookup"><span data-stu-id="3736b-108">Usability and functionality</span></span>

<span data-ttu-id="3736b-109">Los tipos anónimos se introdujeron en la versión 3.0 de C# con expresiones de Language Integrated Query (LINQ).</span><span class="sxs-lookup"><span data-stu-id="3736b-109">Anonymous types were introduced in C# 3.0 with Language-Integrated Query (LINQ) expressions.</span></span> <span data-ttu-id="3736b-110">Con LINQ, los desarrolladores suelen proyectar los resultados de consultas a tipos anónimos que contienen algunas propiedades concretas de los objetos con los que están trabajando.</span><span class="sxs-lookup"><span data-stu-id="3736b-110">With LINQ, developers often project results from queries into anonymous types that hold a few select properties from the objects they're working with.</span></span> <span data-ttu-id="3736b-111">Fíjese en el ejemplo siguiente, en el que se crea una instancia de una matriz de objetos <xref:System.DateTime> y se itera a través de ellos proyectándose en un tipo anónimo con dos propiedades.</span><span class="sxs-lookup"><span data-stu-id="3736b-111">Consider the following example, that instantiates an array of <xref:System.DateTime> objects, and iterates through them projecting into an anonymous type with two properties.</span></span>

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

<span data-ttu-id="3736b-112">Se crea una instancia de los tipos anónimos usando el operador [`new`](../../csharp/language-reference/operators/new-operator.md), y los nombres y tipos de propiedades se infieren a partir de la declaración.</span><span class="sxs-lookup"><span data-stu-id="3736b-112">Anonymous types are instantiated by using the [`new`](../../csharp/language-reference/operators/new-operator.md) operator, and the property names and types are inferred from the declaration.</span></span> <span data-ttu-id="3736b-113">Si dos o más inicializadores de objeto anónimo en el mismo ensamblado especifican una secuencia de propiedades que están en el mismo orden y que tienen los mismos nombres y tipos, el compilador trata el objeto como instancias del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="3736b-113">If two or more anonymous object initializers in the same assembly specify a sequence of properties that are in the same order and that have the same names and types, the compiler treats the objects as instances of the same type.</span></span> <span data-ttu-id="3736b-114">Comparten la misma información de tipo generada por el compilador.</span><span class="sxs-lookup"><span data-stu-id="3736b-114">They share the same compiler-generated type information.</span></span>

<span data-ttu-id="3736b-115">El fragmento de C# anterior proyecta un tipo anónimo con dos propiedades, de forma similar a esta clase de C# generada por el compilador:</span><span class="sxs-lookup"><span data-stu-id="3736b-115">The previous C# snippet projects an anonymous type with two properties, much like the following compiler-generated C# class:</span></span>

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

<span data-ttu-id="3736b-116">Para obtener más información, consulte los [tipos anónimos](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="3736b-116">For more information, see [anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="3736b-117">Existe la misma funcionalidad con las tuplas al proyectar en consultas de LINQ; puede seleccionar propiedades en tuplas.</span><span class="sxs-lookup"><span data-stu-id="3736b-117">The same functionality exists with tuples when projecting into LINQ queries, you can select properties into tuples.</span></span> <span data-ttu-id="3736b-118">Estas tuplas fluyen a través de la consulta, de la misma forma que los tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="3736b-118">These tuples flow through the query, just as anonymous types would.</span></span> <span data-ttu-id="3736b-119">Ahora, tenga en cuenta el ejemplo siguiente usando `System.Tuple<string, long>`.</span><span class="sxs-lookup"><span data-stu-id="3736b-119">Now consider the following example using the `System.Tuple<string, long>`.</span></span>

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

<span data-ttu-id="3736b-120">Con <xref:System.Tuple%602?displayProperty=nameWithType>, la instancia expone propiedades de elementos numeradas, como `Item1` y `Item2`.</span><span class="sxs-lookup"><span data-stu-id="3736b-120">With the <xref:System.Tuple%602?displayProperty=nameWithType>, the instance exposes numbered item properties, such as `Item1`, and `Item2`.</span></span> <span data-ttu-id="3736b-121">Estos nombres de propiedades pueden hacer que resulte más complicado entender la intención de los valores de propiedad, ya que el nombre propiedad solo proporciona el ordinal.</span><span class="sxs-lookup"><span data-stu-id="3736b-121">These property names can make it more difficult to understand the intent of the property values, as the property name only provides the ordinal.</span></span> <span data-ttu-id="3736b-122">Además, los tipos `System.Tuple` son tipos `class` de referencia.</span><span class="sxs-lookup"><span data-stu-id="3736b-122">Furthermore, the `System.Tuple` types are reference `class` types.</span></span> <span data-ttu-id="3736b-123">Sin embargo, <xref:System.ValueTuple%602?displayProperty=nameWithType> es un tipo `struct` de valor.</span><span class="sxs-lookup"><span data-stu-id="3736b-123">The <xref:System.ValueTuple%602?displayProperty=nameWithType> however, is a value `struct` type.</span></span> <span data-ttu-id="3736b-124">En el fragmento de C# siguiente se usa `ValueTuple<string, long>` para hacer la proyección.</span><span class="sxs-lookup"><span data-stu-id="3736b-124">The following C# snippet, uses `ValueTuple<string, long>` to project into.</span></span> <span data-ttu-id="3736b-125">Al hacerlo, se asigna mediante una sintaxis literal.</span><span class="sxs-lookup"><span data-stu-id="3736b-125">In doing so, it assigns using a literal syntax.</span></span>

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

<span data-ttu-id="3736b-126">C# proporciona compatibilidad de lenguaje para las tuplas con el tipo <xref:System.ValueTuple>, además de semántica para:</span><span class="sxs-lookup"><span data-stu-id="3736b-126">C# provides language support of tuples with the <xref:System.ValueTuple> type, and semantics for:</span></span>

- [<span data-ttu-id="3736b-127">Asignación de tuplas</span><span class="sxs-lookup"><span data-stu-id="3736b-127">Tuple assignment</span></span>](../../csharp/tuples.md#assignment-and-tuples)
- <span data-ttu-id="3736b-128">[Deconstrucción de tuplas](../../csharp/deconstruct.md) (no está limitada a las tuplas)</span><span class="sxs-lookup"><span data-stu-id="3736b-128">[Tuple deconstruction](../../csharp/deconstruct.md) (not limited to tuples)</span></span>
- [<span data-ttu-id="3736b-129">Comprobaciones de igualdad de tuplas</span><span class="sxs-lookup"><span data-stu-id="3736b-129">Tuple equality checks</span></span>](../../csharp/tuples.md#equality-and-tuples)
- [<span data-ttu-id="3736b-130">Inicializadores de proyección de tupla</span><span class="sxs-lookup"><span data-stu-id="3736b-130">Tuple projection initializers</span></span>](../../csharp/tuples.md#tuple-projection-initializers)

<span data-ttu-id="3736b-131">Todos los ejemplos anteriores son equivalentes funcionalmente; sin embargo, hay pequeñas diferencias en cuanto a su usabilidad y sus implementaciones subyacentes.</span><span class="sxs-lookup"><span data-stu-id="3736b-131">The previous examples are all functionally equivalent, however; there are slight differences in their usability and their underlying implementations.</span></span>

## <a name="tradeoffs"></a><span data-ttu-id="3736b-132">Compromisos</span><span class="sxs-lookup"><span data-stu-id="3736b-132">Tradeoffs</span></span>

<span data-ttu-id="3736b-133">Es recomendable que use siempre <xref:System.ValueTuple> en lugar de <xref:System.Tuple>, además de los tipos anónimos, pero hay compensaciones que debería tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="3736b-133">You might want to always use <xref:System.ValueTuple> over <xref:System.Tuple>, and anonymous types, but there are tradeoffs you should consider.</span></span> <span data-ttu-id="3736b-134">Los tipos de <xref:System.ValueTuple> son mutables, mientras que los de <xref:System.Tuple> son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="3736b-134">The <xref:System.ValueTuple> types are mutable, whereas <xref:System.Tuple> are read-only.</span></span> <span data-ttu-id="3736b-135">Los tipos anónimos se pueden usar en árboles de expresión; en cambio, las tuplas no.</span><span class="sxs-lookup"><span data-stu-id="3736b-135">Anonymous types can be used in expression trees, while tuples cannot.</span></span> <span data-ttu-id="3736b-136">En la tabla siguiente se muestra información general sobre algunas de las principales diferencias.</span><span class="sxs-lookup"><span data-stu-id="3736b-136">The following table is an overview of some of the key differences.</span></span>

### <a name="key-differences"></a><span data-ttu-id="3736b-137">Principales diferencias</span><span class="sxs-lookup"><span data-stu-id="3736b-137">Key differences</span></span>

| <span data-ttu-id="3736b-138">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="3736b-138">Name</span></span>                     | <span data-ttu-id="3736b-139">Modificador de acceso</span><span class="sxs-lookup"><span data-stu-id="3736b-139">Access modifier</span></span> | <span data-ttu-id="3736b-140">Tipo</span><span class="sxs-lookup"><span data-stu-id="3736b-140">Type</span></span>     | <span data-ttu-id="3736b-141">Nombre de propiedad personalizada</span><span class="sxs-lookup"><span data-stu-id="3736b-141">Custom property name</span></span> | <span data-ttu-id="3736b-142">Compatibilidad con la deconstrucción</span><span class="sxs-lookup"><span data-stu-id="3736b-142">Deconstruction support</span></span> | <span data-ttu-id="3736b-143">Compatibilidad con árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="3736b-143">Expression tree support</span></span> |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| <span data-ttu-id="3736b-144">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="3736b-144">Anonymous types</span></span>          | `internal`      | `class`  | <span data-ttu-id="3736b-145">✔️</span><span class="sxs-lookup"><span data-stu-id="3736b-145">✔️</span></span>                   | ❌                     | <span data-ttu-id="3736b-146">✔️</span><span class="sxs-lookup"><span data-stu-id="3736b-146">✔️</span></span>                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | <span data-ttu-id="3736b-147">✔️</span><span class="sxs-lookup"><span data-stu-id="3736b-147">✔️</span></span>                     |
| <xref:System.ValueTuple> | `public`        | `struct` | <span data-ttu-id="3736b-148">✔️</span><span class="sxs-lookup"><span data-stu-id="3736b-148">✔️</span></span>                   | <span data-ttu-id="3736b-149">✔️</span><span class="sxs-lookup"><span data-stu-id="3736b-149">✔️</span></span>                     | ❌                     |

### <a name="serialization"></a><span data-ttu-id="3736b-150">Serialización</span><span class="sxs-lookup"><span data-stu-id="3736b-150">Serialization</span></span>

<span data-ttu-id="3736b-151">Un elemento importante que hay que tener en cuenta al elegir un tipo es si se tendrá que serializar o no.</span><span class="sxs-lookup"><span data-stu-id="3736b-151">One important consideration when choosing a type, is whether or not it will need to be serialized.</span></span> <span data-ttu-id="3736b-152">La serialización es el proceso de convertir el estado de un objeto en un formato que se pueda almacenar o transportar.</span><span class="sxs-lookup"><span data-stu-id="3736b-152">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="3736b-153">Para obtener más información, vea el artículo sobre [serialización](../../csharp/programming-guide/concepts/serialization/index.md).</span><span class="sxs-lookup"><span data-stu-id="3736b-153">For more information, see [serialization](../../csharp/programming-guide/concepts/serialization/index.md).</span></span> <span data-ttu-id="3736b-154">Cuando la serialización resulta importante, crear un valor `class` o `struct` es preferible a los tipos anónimos o los de tupla.</span><span class="sxs-lookup"><span data-stu-id="3736b-154">When serialization is important, creating a `class` or `struct` is preferred over anonymous types or tuple types.</span></span>

## <a name="performance"></a><span data-ttu-id="3736b-155">Rendimiento</span><span class="sxs-lookup"><span data-stu-id="3736b-155">Performance</span></span>

<span data-ttu-id="3736b-156">El rendimiento entre estos tipos depende de cada escenario.</span><span class="sxs-lookup"><span data-stu-id="3736b-156">Performance between these types depends on the scenario.</span></span> <span data-ttu-id="3736b-157">Un mayor impacto supone la compensación entre las asignaciones y las copias.</span><span class="sxs-lookup"><span data-stu-id="3736b-157">The major impact involves the tradeoff between allocations and copying.</span></span> <span data-ttu-id="3736b-158">En la mayoría de los escenarios, el impacto es pequeño.</span><span class="sxs-lookup"><span data-stu-id="3736b-158">In most scenarios, the impact is small.</span></span> <span data-ttu-id="3736b-159">Cuando pudieran surgir impactos mayores, se tendrían que tomar medidas para tomar una decisión fundamentada.</span><span class="sxs-lookup"><span data-stu-id="3736b-159">When major impacts could arise, measurements should be taken to inform the decision.</span></span>

## <a name="conclusion"></a><span data-ttu-id="3736b-160">Conclusión</span><span class="sxs-lookup"><span data-stu-id="3736b-160">Conclusion</span></span>

<span data-ttu-id="3736b-161">Al elegir entre los tipos de tupla y los anónimos, como desarrollador es necesario tener en cuenta varios factores.</span><span class="sxs-lookup"><span data-stu-id="3736b-161">As a developer choosing between tuples and anonymous types, there are several factors to consider.</span></span> <span data-ttu-id="3736b-162">En general, si no trabaja con [árboles de expresión](../../csharp/expression-trees.md) y le parece bien usar la sintaxis de tupla, elija <xref:System.ValueTuple>, ya que proporcionan un tipo de valor con la flexibilidad de poner nombre a las propiedades.</span><span class="sxs-lookup"><span data-stu-id="3736b-162">Generally speaking, if you're not working with [expression trees](../../csharp/expression-trees.md), and you're comfortable with tuple syntax then choose <xref:System.ValueTuple> as they provide a value type with the flexibility to name properties.</span></span> <span data-ttu-id="3736b-163">Si trabaja con árboles de expresión y prefiere poner nombre a las propiedades, elija los tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="3736b-163">If you're working with expression trees, and you'd prefer to name properties, choose anonymous types.</span></span> <span data-ttu-id="3736b-164">En otros casos, use <xref:System.Tuple>.</span><span class="sxs-lookup"><span data-stu-id="3736b-164">Otherwise, use <xref:System.Tuple>.</span></span>

## <a name="see-also"></a><span data-ttu-id="3736b-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="3736b-165">See also</span></span>

- <span data-ttu-id="3736b-166">[Tipos anónimos (Guía de programación de C#)](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="3736b-166">[Anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)</span></span>
- [<span data-ttu-id="3736b-167">Árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="3736b-167">Expression trees</span></span>](../../csharp/expression-trees.md)
- [<span data-ttu-id="3736b-168">Tipos de tupla</span><span class="sxs-lookup"><span data-stu-id="3736b-168">Tuple types</span></span>](../../csharp/tuples.md)
- [<span data-ttu-id="3736b-169">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="3736b-169">Type design guidelines</span></span>](../design-guidelines/type.md)
