---
title: Elección entre tipos de tupla y anónimos
description: Obtenga información sobre cuándo es adecuado elegir entre los tipos anónimos y sobre los tipos de tupla.
author: IEvangelist
ms.author: dapine
ms.date: 07/01/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 9c186133a639faf187c89d872856d860a20f5a2d
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174223"
---
# <a name="choosing-between-anonymous-and-tuple-types"></a>Elección entre tipos de tupla y anónimos

A la hora de elegir el tipo adecuado, hay que tener en cuenta su usabilidad, su rendimiento y sus compensaciones en comparación con otros tipos. Los tipos anónimos están disponibles desde la versión 3.0 de C#, mientras que los tipos <xref:System.Tuple%602?displayProperty=nameWithType> genéricos se introdujeron con .NET Framework 4.0. Ya que se han incorporado nuevas opciones con compatibilidad de lenguaje, como <xref:System.ValueTuple%602?displayProperty=nameWithType>, que, como indica su nombre, proporciona un tipo de valor con la flexibilidad de los tipos anónimos. En este artículo aprenderá cuándo es pertinente elegir un tipo en lugar de otro.

## <a name="usability-and-functionality"></a>Usabilidad y funcionalidad

Los tipos anónimos se introdujeron en la versión 3.0 de C# con expresiones de Language Integrated Query (LINQ). Con LINQ, los desarrolladores suelen proyectar los resultados de consultas a tipos anónimos que contienen algunas propiedades concretas de los objetos con los que están trabajando. Fíjese en el ejemplo siguiente, en el que se crea una instancia de una matriz de objetos <xref:System.DateTime> y se itera a través de ellos proyectándose en un tipo anónimo con dos propiedades.

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

Se crea una instancia de los tipos anónimos usando el operador [`new`](../../csharp/language-reference/operators/new-operator.md), y los nombres y tipos de propiedades se infieren a partir de la declaración. Si dos o más inicializadores de objeto anónimo en el mismo ensamblado especifican una secuencia de propiedades que están en el mismo orden y que tienen los mismos nombres y tipos, el compilador trata el objeto como instancias del mismo tipo. Comparten la misma información de tipo generada por el compilador.

El fragmento de C# anterior proyecta un tipo anónimo con dos propiedades, de forma similar a esta clase de C# generada por el compilador:

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

Para obtener más información, consulte los [tipos anónimos](../../csharp/programming-guide/classes-and-structs/anonymous-types.md). Existe la misma funcionalidad con las tuplas al proyectar en consultas de LINQ; puede seleccionar propiedades en tuplas. Estas tuplas fluyen a través de la consulta, de la misma forma que los tipos anónimos. Ahora, tenga en cuenta el ejemplo siguiente usando `System.Tuple<string, long>`.

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

Con <xref:System.Tuple%602?displayProperty=nameWithType>, la instancia expone propiedades de elementos numeradas, como `Item1` y `Item2`. Estos nombres de propiedades pueden hacer que resulte más complicado entender la intención de los valores de propiedad, ya que el nombre propiedad solo proporciona el ordinal. Además, los tipos `System.Tuple` son tipos `class` de referencia. Sin embargo, <xref:System.ValueTuple%602?displayProperty=nameWithType> es un tipo `struct` de valor. En el fragmento de C# siguiente se usa `ValueTuple<string, long>` para hacer la proyección. Al hacerlo, se asigna mediante una sintaxis literal.

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

Para obtener más información sobre las tuplas, consulte [Tipos de tupla (referencia de C#)](../../csharp/language-reference/builtin-types/value-tuples.md) o [Tuplas (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/tuples.md).

Todos los ejemplos anteriores son equivalentes funcionalmente; sin embargo, hay pequeñas diferencias en cuanto a su usabilidad y sus implementaciones subyacentes.

## <a name="tradeoffs"></a>Compromisos

Es recomendable que use siempre <xref:System.ValueTuple> en lugar de <xref:System.Tuple>, además de los tipos anónimos, pero hay compensaciones que debería tener en cuenta. Los tipos de <xref:System.ValueTuple> son mutables, mientras que los de <xref:System.Tuple> son de solo lectura. Los tipos anónimos se pueden usar en árboles de expresión; en cambio, las tuplas no. En la tabla siguiente se muestra información general sobre algunas de las principales diferencias.

### <a name="key-differences"></a>Principales diferencias

| NOMBRE                     | Modificador de acceso | Tipo     | Nombre del miembro personalizado | Compatibilidad con la deconstrucción | Compatibilidad con árboles de expresión |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| Tipos anónimos          | `internal`      | `class`  | ✔️                   | ❌                     | ✔️                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | ✔️                     |
| <xref:System.ValueTuple> | `public`        | `struct` | ✔️                   | ✔️                     | ❌                     |

### <a name="serialization"></a>Serialización

Un elemento importante que hay que tener en cuenta al elegir un tipo es si se tendrá que serializar o no. La serialización es el proceso de convertir el estado de un objeto en un formato que se pueda almacenar o transportar. Para obtener más información, vea el artículo sobre [serialización](../../csharp/programming-guide/concepts/serialization/index.md). Cuando la serialización resulta importante, crear un valor `class` o `struct` es preferible a los tipos anónimos o los de tupla.

## <a name="performance"></a>Rendimiento

El rendimiento entre estos tipos depende de cada escenario. Un mayor impacto supone la compensación entre las asignaciones y las copias. En la mayoría de los escenarios, el impacto es pequeño. Cuando pudieran surgir impactos mayores, se tendrían que tomar medidas para tomar una decisión fundamentada.

## <a name="conclusion"></a>Conclusión

Al elegir entre los tipos de tupla y los anónimos, como desarrollador es necesario tener en cuenta varios factores. En general, si no trabaja con [árboles de expresión](../../csharp/expression-trees.md) y le parece bien usar la sintaxis de tupla, elija <xref:System.ValueTuple>, ya que proporcionan un tipo de valor con la flexibilidad de poner nombre a las propiedades. Si trabaja con árboles de expresión y prefiere poner nombre a las propiedades, elija los tipos anónimos. En otros casos, use <xref:System.Tuple>.

## <a name="see-also"></a>Vea también

- [Tipos anónimos (Guía de programación de C#)](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).
- [Árboles de expresión](../../csharp/expression-trees.md)
- [Tipos de tupla (referencia de C#)](../../csharp/language-reference/builtin-types/value-tuples.md)
- [Tuplas (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/tuples.md)
- [Instrucciones de diseño de tipos](../design-guidelines/type.md)
