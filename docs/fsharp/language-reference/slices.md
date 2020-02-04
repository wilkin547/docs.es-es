---
title: Segmentos
description: Obtenga información sobre cómo usar los segmentos F# para los tipos de datos existentes y cómo definir sus propios segmentos para otros tipos de datos.
ms.date: 12/23/2019
ms.openlocfilehash: 928005f2c63ffe099bb64e11ed29bb625e0a54c6
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980384"
---
# <a name="slices"></a>Segmentos

En F#, un segmento es un subconjunto de cualquier tipo de datos que tenga un método `GetSlice` en su definición o en una [extensión de tipo](type-extensions.md)en el ámbito. Normalmente se usa con F# matrices y listas. En este artículo se explica cómo tomar los segmentos F# de los tipos existentes y cómo definir sus propios segmentos.

Los segmentos son similares a los [indizadores](./members/indexed-properties.md), pero en lugar de producir un valor único de la estructura de datos subyacente, producen varios.

F#Actualmente tiene compatibilidad intrínseca con la segmentación de cadenas, listas, matrices y matrices 2D.

## <a name="basic-slicing-with-f-lists-and-arrays"></a>Segmentación básica con F# listas y matrices

Los tipos de datos más comunes que se segmentan F# son listas y matrices. En el ejemplo siguiente se muestra cómo hacerlo con listas:

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

F#admite matrices multidimensionales en la F# biblioteca principal. Al igual que con las matrices unidimensionales, los segmentos de matrices multidimensionales también pueden ser útiles. Sin embargo, la introducción de dimensiones adicionales asigna una sintaxis ligeramente diferente para que pueda tomar segmentos de filas y columnas específicas.

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

La F# biblioteca principal no define actualmente `GetSlice` para las matrices 3D. Si desea segmentar matrices 3D u otras matrices de más dimensiones, defina el miembro de `GetSlice`.

## <a name="defining-slices-for-other-data-structures"></a>Definir segmentos para otras estructuras de datos

La F# biblioteca principal define los segmentos para un conjunto limitado de tipos. Si desea definir segmentos para más tipos de datos, puede hacerlo en la propia definición de tipo o en una extensión de tipo.

Por ejemplo, aquí se muestra cómo puede definir segmentos para la clase <xref:System.ArraySegment%601> para permitir una manipulación de datos adecuada:

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

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a>Usar la inclusión para evitar la conversión boxing si es necesario

Si va a definir segmentos para un tipo que es realmente un struct, recomendamos que `inline` el miembro `GetSlice`. El F# compilador optimiza los argumentos opcionales, evitando las asignaciones de montón como resultado de la segmentación. Esto es muy importante para las construcciones de segmentación como <xref:System.Span%601> que no se pueden asignar en el montón.

```fsharp
open System

type ReadOnlySpan<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

type Span<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
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

## <a name="built-in-f-slices-are-end-inclusive"></a>Los F# segmentos integrados son de fin-inclusivo

Todos los sectores intrínsecos de F# son de fin-inclusivo; es decir, el límite superior se incluye en el segmento. Para un segmento determinado con el índice de inicio `x` y el final `y`de índice, el segmento resultante incluirá el valor de *YTH* .

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="see-also"></a>Vea también

- [Propiedades indizadas](./members/indexed-properties.md)
