---
title: Explorar los intervalos de datos con índices y rangos
description: En este tutorial avanzado se explica cómo explorar datos con índices e intervalos para examinar los segmentos de un conjunto de datos secuencial.
ms.date: 04/19/2019
ms.custom: mvc
ms.openlocfilehash: 64fae4581e265d4f70b8356d5c651b4fdaca3fe9
ms.sourcegitcommit: dd3b897feb5c4ac39732bb165848e37a344b0765
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2019
ms.locfileid: "64431499"
---
# <a name="indices-and-ranges"></a>Índices y rangos

Los rangos e índices proporcionan una sintaxis concisa para acceder a elementos únicos o intervalos en una <xref:System.Array>, <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>. Estas características permiten una sintaxis más concisa y clara para acceder a elementos únicos o intervalos de elementos de una secuencia.

En este tutorial aprenderá lo siguiente:

> [!div class="checklist"]
> * Usar la sintaxis para intervalos de una secuencia.
> * Comprender las decisiones de diseño para iniciar y finalizar cada secuencia.
> * Descubrir escenarios para los tipos <xref:System.Index> y <xref:System.Range>.

## <a name="language-support-for-indices-and-ranges"></a>Compatibilidad con idiomas para los índices y los rangos

Puede especificar un índice **desde el final** mediante el carácter `^` antes del índice. La indexación desde el final se inicia con la regla que `0..^0` especifica el intervalo completo. Para enumerar toda una matriz, empiece *en el primer elemento* y continúe hasta *rebasar el último elemento*. Piense en el comportamiento del método `MoveNext` en un enumerador: devuelve false cuando la enumeración rebasa el último elemento. El índice `^0` significa "el final", `array[array.Length]`, o el índice que sigue al último elemento. Está familiarizado con `array[2]` lo que significa el elemento "2 desde el principio". Ahora, `array[^2]` significa el elemento "2 desde el final". 

Puede especificar un **rango** con el **operador de rango**: `..`. Por ejemplo, `0..^0` especifica el rango completo de la matriz: 0 desde el principio hasta, pero sin incluir 0 desde el final. Cualquier operando puede usar "desde el principio" o "desde el final". Además, se puede omitir cualquier operando. Los valores predeterminados son `0` para el índice de inicio y `^0` para el índice de final.

```csharp-interactive
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

El índice de cada elemento refuerza el concepto de "desde el inicio" y "desde el final", y que los rangos son exclusivos del final del rango. El "inicio" de toda la matriz es el primer elemento. El "final" de toda la matriz es *pasado* el último elemento.

Puede recuperar la última palabra con el índice `^1`. Agregue el código siguiente a la inicialización:

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

El siguiente código crea un subrango con las palabras "quick", "brown" y "fox". Va de `words[1]` a `words[3]`. El elemento `words[4]` no se encuentra en el intervalo. Agregue el código siguiente al mismo método. Cópielo y péguelo en la parte inferior de la ventana interactiva.

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

El siguiente código crea un subrango con "lazy" y "dog". Incluye `words[^2]` y `words[^1]`. El índice del final `words[^0]` no se incluye. Agregue el código siguiente también:

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

En los ejemplos siguientes se crean rangos con final abierto para el inicio, el final o ambos:

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

También puede declarar rangos o índices como variables. La variable se puede usar luego dentro de los caracteres `[` y `]`:

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

Los ejemplos anteriores muestran dos decisiones de diseño que requieren mayor explicación:

- Los intervalos son *exclusivos*, lo que significa que el elemento en el último índice no está en el intervalo.
- El índice `^0` es *el final* de la colección, no *el último elemento* en la colección.

El ejemplo siguiente muestra muchos de los motivos para esas opciones. Modifique `x`, `y` y `z` para probar diferentes combinaciones. Al experimentar, use valores donde `x` sea menor que `y` y `y` sea menor que `z` para las combinaciones válidas. Agregue el código siguiente a un nuevo método. Pruebe diferentes combinaciones:

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a>Escenarios para los índices y los rangos

A menudo usará rangos e índices cuando desee realizar un poco de análisis en el subrango de una secuencia completa. La nueva sintaxis es más clara al leer exactamente lo que implica el subrango. La función local `MovingAverage` toma un <xref:System.Range> como su argumento. El método enumera solo ese rango al calcular el mínimo, el máximo y la media. Pruebe con el código siguiente en su proyecto:

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

Puede descargar el código completado del repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes).
