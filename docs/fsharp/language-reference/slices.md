---
title: Segmentos
description: 'Obtenga información sobre cómo usar los segmentos para los tipos de datos de F # existentes y cómo definir sus propios segmentos para otros tipos de datos.'
ms.date: 12/23/2019
ms.openlocfilehash: a3920ad9e1b205b506aaee92c4606bcebf94feba
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557084"
---
# <a name="slices"></a>Segmentos

En F #, un segmento es un subconjunto de cualquier tipo de datos que tenga un `GetSlice` método en su definición o en una [extensión de tipo](type-extensions.md)en el ámbito. Se usa normalmente con matrices y listas de F #. En este artículo se explica cómo tomar los segmentos de los tipos de F # existentes y cómo definir sus propios segmentos.

Los segmentos son similares a los [indizadores](./members/indexed-properties.md), pero en lugar de producir un valor único de la estructura de datos subyacente, producen varios.

F # tiene actualmente compatibilidad intrínseca con la segmentación de cadenas, listas, matrices y matrices 2D.

## <a name="basic-slicing-with-f-lists-and-arrays"></a>Segmentación básica con listas y matrices de F #

Los tipos de datos más comunes que se segmentan son listas y matrices de F #. En el ejemplo siguiente se muestra cómo hacerlo con listas:

```fsharp
// Generate a list of 100 integers
let fullList = [ 1 .. 100 ]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullList.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullList.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullList.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

La segmentación de matrices es igual que las listas de segmentación:

```fsharp
// Generate an array of 100 integers
let fullArray = [| 1 .. 100 |]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullArray.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullArray.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullArray.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

## <a name="slicing-multidimensional-arrays"></a>Segmentar matrices multidimensionales

F # admite matrices multidimensionales en la biblioteca básica de F #. Al igual que con las matrices unidimensionales, los segmentos de matrices multidimensionales también pueden ser útiles. Sin embargo, la introducción de dimensiones adicionales asigna una sintaxis ligeramente diferente para que pueda tomar segmentos de filas y columnas específicas.

En los siguientes ejemplos se muestra cómo segmentar una matriz 2D:

```fsharp
// Generate a 3x3 2D matrix
let A = array2D [[1;2;3];[4;5;6];[7;8;9]]
printfn "Full matrix:\n %A" A

// Take the first row
let row0 = A.[0,*]
printfn "Row 0: %A" row0

// Take the first column
let col0 = A.[*,0]
printfn "Column 0: %A" col0

// Take all rows but only two columns
let subA = A.[*,0..1]
printfn "%A" subA

// Take two rows and all columns
let subA' = A.[0..1,*]
printfn "%A" subA'

// Slice a 2x2 matrix out of the full 3x3 matrix
let twoByTwo = A.[0..1,0..1]
printfn "%A" twoByTwo
```

La biblioteca básica de F # no define actualmente `GetSlice` para las matrices 3D. Si desea segmentar matrices 3D u otras matrices de más dimensiones, defina el `GetSlice` miembro usted mismo.

## <a name="defining-slices-for-other-data-structures"></a>Definir segmentos para otras estructuras de datos

La biblioteca básica de F # define los segmentos para un conjunto limitado de tipos. Si desea definir segmentos para más tipos de datos, puede hacerlo en la propia definición de tipo o en una extensión de tipo.

Por ejemplo, aquí se muestra cómo podría definir los segmentos de la <xref:System.ArraySegment%601> clase para permitir una manipulación de datos adecuada:

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(start, finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

Otro ejemplo de uso de los <xref:System.Span%601> <xref:System.ReadOnlySpan%601> tipos y:

```fsharp
open System

type ReadOnlySpan<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

type Span<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..3] // |2; 3|]
```

## <a name="built-in-f-slices-are-end-inclusive"></a>Los segmentos de F # integrados son de fin-inclusivo

Todos los segmentos intrínsecos de F # son de fin-inclusivo; es decir, el límite superior se incluye en el segmento. Para un segmento determinado con el índice `x` de inicio y `y` el de finalización, el segmento resultante incluirá el valor de *YTH* .

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="built-in-f-empty-slices"></a>Segmentos vacíos de F # integrados

Las listas, matrices, secuencias, cadenas, matrices 2D, matrices 3D y 4D matrices de F # producirán un segmento vacío si la sintaxis podría producir un segmento que no existe.

Tenga en cuenta lo siguiente.

```fsharp
let l = [ 1..10 ]
let a = [| 1..10 |]
let s = "hello!"

let emptyList = l.[-2..(-1)]
let emptyArray = a.[-2..(-1)]
let emptyString = s.[-2..(-1)]
```

Los desarrolladores de C# pueden esperar que se produzca una excepción en lugar de producir un segmento vacío. Se trata de una decisión de diseño que se basa en el hecho de que las colecciones vacías se componen en F #. Una lista vacía de F # puede estar formada por otra lista de F #, una cadena vacía se puede Agregar a una cadena existente, etc. Puede ser común tomar los segmentos en función de los valores pasados como parámetros y ser tolerante de los límites fuera de los límites mediante la generación de una colección vacía que se ajusta a la naturaleza de composición del código de F #.

## <a name="fixed-index-slices-for-3d-and-4d-arrays"></a>Segmentos de índice fijo para matrices 3D y 4D

En el caso de las matrices F # 3D y 4D, puede "corregir" un índice determinado y segmentar otras dimensiones con ese índice fijo.

Para ilustrar esto, considere la siguiente matriz 3D:

*z = 0*
| x\y   | 0 | 1 |
|-------|---|---|
| **0** | 0 | 1 |
| **1** | 2 | 3 |

*z = 1*
| x\y   | 0 | 1 |
|-------|---|---|
| **0** | 4 | 5 |
| **1** | 6 | 7 |

Si desea extraer el segmento `[| 4; 5 |]` de la matriz, use un segmento de índice fijo.

```fsharp
let dim = 2
let m = Array3D.zeroCreate<int> dim dim dim

let mutable count = 0

for z in 0..dim-1 do
    for y in 0..dim-1 do
        for x in 0..dim-1 do
            m.[x,y,z] <- count
            count <- count + 1

// Now let's get the [4;5] slice!
m.[*, 0, 1]
```

La última línea corrige las `y` `z` lenguas y de la matriz 3D y toma el resto de los `x` valores que corresponden a la matriz.

## <a name="see-also"></a>Consulte también

- [Propiedades indizadas](./members/indexed-properties.md)
