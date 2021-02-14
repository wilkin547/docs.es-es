---
title: Explorar los intervalos de datos con índices y rangos
description: En este tutorial avanzado se explica cómo explorar datos mediante índices e intervalos para examinar un intervalo continuo de un conjunto de datos secuencial.
ms.date: 09/11/2020
ms.technology: csharp-fundamentals
ms.custom: mvc
ms.openlocfilehash: c0484a42233466e3a2a70a673aee81fce91fe31b
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585408"
---
# <a name="indices-and-ranges"></a>Índices y rangos

Los intervalos e índices proporcionan una sintaxis concisa para acceder a elementos únicos o intervalos en una secuencia.

En este tutorial aprenderá lo siguiente:

> [!div class="checklist"]
>
> - Usar la sintaxis para intervalos de una secuencia.
> - Comprender las decisiones de diseño para iniciar y finalizar cada secuencia.
> - Descubrir escenarios para los tipos <xref:System.Index> y <xref:System.Range>.

## <a name="language-support-for-indices-and-ranges"></a>Compatibilidad con idiomas para los índices y los rangos

Esta compatibilidad con lenguajes se basa en dos nuevos tipos y dos nuevos operadores:

- <xref:System.Index?displayProperty=nameWithType> representa un índice en una secuencia.
- Índice desde el operador final `^`, que especifica que un índice es relativo al final de una secuencia.
- <xref:System.Range?displayProperty=nameWithType> representa un subrango de una secuencia.
- El operador de intervalo `..`, que especifica el inicio y el final de un intervalo como sus operandos.

Comencemos con las reglas de los índices. Considere un elemento `sequence` de matriz. El índice `0` es igual que `sequence[0]`. El índice `^0` es igual que `sequence[sequence.Length]`. La expresión `sequence[^0]` produce una excepción, al igual que `sequence[sequence.Length]`. Para cualquier número `n`, el índice `^n` es igual que `sequence[sequence.Length - n]`.

```csharp
string[] words = new string[]
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

Puede recuperar la última palabra con el índice `^1`. Agregue el código siguiente a la inicialización:

[!code-csharp[LastIndex](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

Un rango especifica el *inicio* y el *final* de un intervalo. Los rangos son excluyentes, lo que significa que el *final* no se incluye en el intervalo. El rango `[0..^0]` representa todo el intervalo, al igual que `[0..sequence.Length]` representa todo el intervalo.

El siguiente código crea un subrango con las palabras "quick", "brown" y "fox". Va de `words[1]` a `words[3]`. El elemento `words[4]` no se encuentra en el intervalo. Agregue el código siguiente al mismo método. Cópielo y péguelo en la parte inferior de la ventana interactiva.

[!code-csharp[Range](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

El código siguiente devuelve el rango con "lazy" y "dog". Incluye `words[^2]` y `words[^1]`. El índice del final `words[^0]` no se incluye. Agregue el código siguiente también:

[!code-csharp[LastRange](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

En los ejemplos siguientes se crean rangos con final abierto para el inicio, el final o ambos:

[!code-csharp[PartialRange](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

También puede declarar rangos o índices como variables. La variable se puede usar luego dentro de los caracteres `[` y `]`:

[!code-csharp[IndexRangeTypes](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

El ejemplo siguiente muestra muchos de los motivos para esas opciones. Modifique `x`, `y` y `z` para probar diferentes combinaciones. Al experimentar, use valores donde `x` sea menor que `y` y `y` sea menor que `z` para las combinaciones válidas. Agregue el código siguiente a un nuevo método. Pruebe diferentes combinaciones:

[!code-csharp[SemanticsExamples](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="type-support-for-indices-and-ranges"></a>Compatibilidad con tipos para los índices y los rangos

Los índices y los intervalos proporcionan una sintaxis clara y concisa para acceder a un único elemento o a un rango de elementos de una secuencia. Normalmente, una expresión de índice devuelve el tipo de los elementos de una secuencia. Una expresión de rango suele devolver el mismo tipo de secuencia que la secuencia de origen.

Cualquier tipo que proporcione un [indexador](../programming-guide/indexers/index.md) con un parámetro <xref:System.Index> o <xref:System.Range> admite de manera explícita índices o rangos, respectivamente. Un indexador que toma un único parámetro <xref:System.Range> puede devolver un tipo de secuencia diferente, como <xref:System.Span%601?displayProperty=nameWithType>.

> [!IMPORTANT]
> El rendimiento del código que usa el operador de rango depende del tipo del operando de la secuencia.
>
> La complejidad temporal del operador de rango depende del tipo de secuencia. Por ejemplo, si la secuencia es un valor `string` o una matriz, el resultado es una copia de la sección especificada de la entrada, por lo que la complejidad temporal es *O(N)* (donde N es la longitud del rango). Por otro lado, si se trata de <xref:System.Span%601?displayProperty=nameWithType> o <xref:System.Memory%601?displayProperty=nameWithType>, el resultado hace referencia a la misma memoria auxiliar, lo que significa que no hay ninguna copia y que la operación es *O(1)* .
>
> Además de la complejidad temporal, esto provoca asignaciones y copias adicionales, lo que afecta al rendimiento. En el código sensible al rendimiento, considere la posibilidad de usar `Span<T>` o `Memory<T>` como el tipo de secuencia, ya que el operador de rango no realiza la asignación.

Un tipo es **contable** si tiene una propiedad denominada `Length` o `Count` con un captador accesible y un tipo de valor devuelto de `int`. Un tipo contable que no admite índices ni rangos de manera explícita podría admitirlos implícitamente. Para más información, consulte las secciones [Compatibilidad implícita de índices](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-index-support) y [Compatibilidad implícita de rangos](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-range-support) de la [nota de propuesta de características](~/_csharplang/proposals/csharp-8.0/ranges.md). Los rangos que usan la compatibilidad implícita del rango devuelven el mismo tipo de secuencia que la secuencia de origen.

Por ejemplo, los tipos de .NET siguientes admiten tanto índices como rangos: <xref:System.String>, <xref:System.Span%601> y <xref:System.ReadOnlySpan%601>. <xref:System.Collections.Generic.List%601> admite índices, pero no rangos.

<xref:System.Array> tiene un comportamiento con más matices. Así, las matrices de una sola dimensión admiten índices y rangos, Las matrices multidimensionales no admiten indexadores o rangos. El indexador de una matriz multidimensional tiene varios parámetros, no un parámetro único. Las matrices escalonadas, también denominadas matriz de matrices, admiten tanto intervalos como indexadores. En el siguiente ejemplo se muestra cómo iterar por una subsección rectangular de una matriz escalonada. Se itera por la sección del centro, excluyendo la primera y las últimas tres filas, así como la primera y las dos últimas columnas de cada fila seleccionada:

[!code-csharp[JaggedArrays](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_JaggedArrays)]

En todos los casos, el operador de rango para <xref:System.Array> asigna una matriz para almacenar los elementos devueltos.

## <a name="scenarios-for-indices-and-ranges"></a>Escenarios para los índices y los rangos

A menudo usará rangos e índices cuando quiera analizar una parte de una secuencia más grande. La nueva sintaxis es más clara al leer exactamente qué parte de la secuencia está implicada. La función local `MovingAverage` toma un <xref:System.Range> como su argumento. El método enumera solo ese rango al calcular el mínimo, el máximo y la media. Pruebe con el código siguiente en su proyecto:

[!code-csharp[MovingAverages](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]
