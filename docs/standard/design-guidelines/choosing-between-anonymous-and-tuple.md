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
# <a name="choosing-between-anonymous-and-tuple-types"></a>Elección entre tipos anónimos y de tupla

La elección del tipo adecuado implica tener en cuenta su facilidad de uso, rendimiento y contrapartidas en comparación con otros tipos. Los tipos anónimos están disponibles desde C# 3,0, mientras que los tipos genéricos <xref:System.Tuple%602?displayProperty=nameWithType> se introdujeron con .NET Framework 4,0. Dado que se han incorporado nuevas opciones con compatibilidad de nivel de lenguaje, como <xref:System.ValueTuple%602?displayProperty=nameWithType> la que indica el nombre, proporcione un tipo de valor con la flexibilidad de los tipos anónimos. En este artículo, aprenderá Cuándo es adecuado elegir un tipo sobre el otro.

## <a name="usability-and-functionality"></a>Facilidad de uso y funcionalidad

Los tipos anónimos se introdujeron en C# 3,0 con expresiones Language-Integrated Query (LINQ). Con LINQ, los desarrolladores suelen proyectar los resultados de las consultas en tipos anónimos que contienen algunas propiedades de selección de los objetos con los que están trabajando. Considere el ejemplo siguiente, que crea una instancia de una matriz de <xref:System.DateTime> objetos y recorre en iteración los proyectos en un tipo anónimo con dos propiedades.

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

Las instancias de los tipos anónimos se crean mediante el [`new`](../../csharp/language-reference/operators/new-operator.md) operador, y los nombres y tipos de propiedad se deducen a partir de la declaración. Si dos o más inicializadores de objeto anónimo en el mismo ensamblado especifican una secuencia de propiedades que están en el mismo orden y que tienen los mismos nombres y tipos, el compilador trata los objetos como instancias del mismo tipo. Comparten la misma información de tipo generada por el compilador.

El fragmento de código de C# anterior proyecta un tipo anónimo con dos propiedades, de forma similar a la siguiente clase C# generada por el compilador:

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

Para obtener más información, vea [tipos anónimos](../../csharp/programming-guide/classes-and-structs/anonymous-types.md). Existe la misma funcionalidad con tuplas al proyectar en consultas LINQ, puede seleccionar Propiedades en tuplas. Estas tuplas fluyen a través de la consulta, de la misma forma que los tipos anónimos. Ahora, considere el siguiente ejemplo usando `System.Tuple<string, long>` .

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

Con <xref:System.Tuple%602?displayProperty=nameWithType> , la instancia de expone propiedades de elementos numeradas, como `Item1` y `Item2` . Estos nombres de propiedad pueden dificultar la comprensión de la intención de los valores de propiedad, ya que el nombre de la propiedad solo proporciona el ordinal. Además, los `System.Tuple` tipos son tipos de referencia `class` . <xref:System.ValueTuple%602?displayProperty=nameWithType>Sin embargo, es un tipo de valor `struct` . En el siguiente fragmento de código de C#, `ValueTuple<string, long>` se usa para proyectar en. Al hacerlo, se asigna mediante una sintaxis literal.

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

C# proporciona compatibilidad de lenguajes de tuplas con el <xref:System.ValueTuple> tipo y la semántica para:

- [Asignación de tupla](../../csharp/tuples.md#assignment-and-tuples)
- [Desconstrucción de tuplas](../../csharp/deconstruct.md) (no limitadas a tuplas)
- [Comprobaciones de igualdad de tupla](../../csharp/tuples.md#equality-and-tuples)
- [Inicializadores de proyección de tupla](../../csharp/tuples.md#tuple-projection-initializers)

Sin embargo, los ejemplos anteriores son funcionalmente equivalentes; hay ligeras diferencias en su facilidad de uso y sus implementaciones subyacentes.

## <a name="tradeoffs"></a>Compromisos

Es posible que desee usar siempre <xref:System.ValueTuple> los <xref:System.Tuple> tipos en y anónimos, pero hay que tener en cuenta los inconvenientes. Los <xref:System.ValueTuple> tipos son mutables, mientras que <xref:System.Tuple> son de solo lectura. Los tipos anónimos se pueden usar en los árboles de expresión, mientras que las tuplas no pueden. En la tabla siguiente se presenta una visión general de algunas de las diferencias clave.

### <a name="key-differences"></a>Diferencias clave

| Nombre                     | Modificador de acceso | Tipo     | Nombre de propiedad personalizada | Compatibilidad con la desconstrucción | Compatibilidad con árboles de expresión |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| Tipos anónimos          | `internal`      | `class`  | ✔️                   | ❌                     | ✔️                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | ✔️                     |
| <xref:System.ValueTuple> | `public`        | `struct` | ✔️                   | ✔️                     | ❌                     |

### <a name="serialization"></a>Serialización

Una consideración importante a la hora de elegir un tipo es si se debe serializar o no. La serialización es el proceso de convertir el estado de un objeto en un formato que se pueda almacenar o transportar. Para obtener más información, vea [serialización](../../csharp/programming-guide/concepts/serialization/index.md). Cuando la serialización es importante, `class` se prefiere crear un o `struct` a través de tipos anónimos o tipos de tupla.

## <a name="performance"></a>Rendimiento

El rendimiento entre estos tipos depende del escenario. El mayor impacto implica el equilibrio entre las asignaciones y la copia. En la mayoría de los escenarios, el impacto es pequeño. Cuando pudieran surgir impactos importantes, se deben tomar medidas para informar sobre la decisión.

## <a name="conclusion"></a>Conclusión

Como desarrollador que elige entre tuplas y tipos anónimos, debe tener en cuenta varios factores. En general, si no está trabajando con [árboles de expresión](../../csharp/expression-trees.md)y está familiarizado con la sintaxis de tupla, elija a <xref:System.ValueTuple> medida que proporcionan un tipo de valor con la flexibilidad para asignar nombres a las propiedades. Si está trabajando con árboles de expresión y prefiere asignar un nombre a las propiedades, elija tipos anónimos. De lo contrario, use <xref:System.Tuple>.

## <a name="see-also"></a>Vea también

- [Tipos anónimos (Guía de programación de C#)](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).
- [Árboles de expresión](../../csharp/expression-trees.md)
- [Instrucciones de diseño de los marcos](index.md)
- [Tipos de tupla](../../csharp/tuples.md)
- [Instrucciones de diseño de tipos](type.md)
