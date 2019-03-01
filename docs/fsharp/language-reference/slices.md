---
title: Los segmentos (F#)
description: Obtenga información sobre cómo utilizar los segmentos existentes F# tipos de datos y cómo definir sus propios segmentos para otros tipos de datos.
ms.date: 01/22/2019
ms.openlocfilehash: 60b57d4eea40bb26dc43d8255dd933b63ac6303c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970119"
---
# <a name="slices"></a><span data-ttu-id="3a4f9-103">Segmentos</span><span class="sxs-lookup"><span data-stu-id="3a4f9-103">Slices</span></span>

<span data-ttu-id="3a4f9-104">En F#, un segmento es un subconjunto de un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-104">In F#, a slice is a subset of a data type.</span></span> <span data-ttu-id="3a4f9-105">Para poder tomar un segmento de un tipo de datos, debe definir el tipo de datos un `GetSlice` método o en un [escriba extensión](type-extensions.md) decir en ámbito.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-105">To be able to take a slice from a data type, the data type must either define a `GetSlice` method or in a [type extension](type-extensions.md) that is in scope.</span></span> <span data-ttu-id="3a4f9-106">Este artículo explica cómo aprovechar los segmentos de existentes F# tipos y cómo definir las suyas propias.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-106">This article explains how to take slices from existing F# types and how to define your own.</span></span>

<span data-ttu-id="3a4f9-107">Los segmentos son similares a [indizadores](members/indexed-properties.md), pero en lugar de producir un único valor de la estructura de datos subyacente, producen varias.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-107">Slices are similar to [indexers](members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="3a4f9-108">F#actualmente tiene compatibilidad intrínseca para dividir las cadenas, matrices, listas y matrices 2D.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="3a4f9-109">Segmentación básica con F# listas y matrices</span><span class="sxs-lookup"><span data-stu-id="3a4f9-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="3a4f9-110">Los tipos de datos más comunes que se segmenta son F# listas y matrices.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="3a4f9-111">El ejemplo siguiente muestra cómo hacer esto con listas:</span><span class="sxs-lookup"><span data-stu-id="3a4f9-111">The following example demonstrates how to do this with lists:</span></span>

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

<span data-ttu-id="3a4f9-112">Segmentación de matrices es igual que la segmentación de listas:</span><span class="sxs-lookup"><span data-stu-id="3a4f9-112">Slicing arrays is just like slicing lists:</span></span>

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

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="3a4f9-113">Fragmentación de matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="3a4f9-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="3a4f9-114">F#admite matrices multidimensionales en el F# biblioteca principal.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="3a4f9-115">Al igual que con las matrices unidimensionales, también pueden ser útiles sectores de matrices multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="3a4f9-116">Sin embargo, la introducción de dimensiones adicionales exige una sintaxis ligeramente diferente para que pueden tomar segmentos de columnas y filas específicas.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="3a4f9-117">Los ejemplos siguientes muestran cómo segmentar una matriz 2D:</span><span class="sxs-lookup"><span data-stu-id="3a4f9-117">The following examples demonstrate how to slice a 2D array:</span></span>

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
printfn "%A" twobyTwo
```

<span data-ttu-id="3a4f9-118">El F# biblioteca principal no define `GetSlice`para matrices 3D.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-118">The F# core library does not define `GetSlice`for 3D arrays.</span></span> <span data-ttu-id="3a4f9-119">Si desea segmentar los u otras matrices o varias dimensiones, debe definir el `GetSlice` miembro usted mismo.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-119">If you wish to slice those or other arrays of more dimensions, you must define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="3a4f9-120">Definición de segmentos de otras estructuras de datos</span><span class="sxs-lookup"><span data-stu-id="3a4f9-120">Defining slices for other data structures</span></span>

<span data-ttu-id="3a4f9-121">El F# biblioteca principal define los segmentos para un conjunto limitado de tipos.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="3a4f9-122">Si desea definir segmentos más tipos de datos, puede hacerlo en la propia definición de tipo o en una extensión de tipo.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="3a4f9-123">Por ejemplo, aquí es cómo podría definir segmentos de la <xref:System.ArraySegment%601> clase para permitir la manipulación de datos adecuada:</span><span class="sxs-lookup"><span data-stu-id="3a4f9-123">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(?start, ?finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a><span data-ttu-id="3a4f9-124">Uso de inclusión para evitar la conversión boxing si es necesario</span><span class="sxs-lookup"><span data-stu-id="3a4f9-124">Use inlining to avoid boxing if it is necessary</span></span>

<span data-ttu-id="3a4f9-125">Si va a definir segmentos de un tipo que es realmente un struct, se recomienda `inline` el `GetSlice` miembro.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-125">If you are defining slices for a type that is actually a struct, we recommend that you `inline` the `GetSlice` member.</span></span> <span data-ttu-id="3a4f9-126">El F# compilador optimiza los argumentos opcionales, evitando las asignaciones del montón como resultado de la segmentación.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-126">The F# compiler optimizes away the optional arguments, avoiding any heap allocations as a result of slicing.</span></span> <span data-ttu-id="3a4f9-127">Esto es muy importante para la segmentación de construcciones como <xref:System.Span%601> que no se puede asignar en el montón.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-127">This is critically important for slicing constructs such as <xref:System.Span%601> that cannot be allocated on the heap.</span></span>

```fsharp
open System

type Span<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..2] // |2; 3|]
```

## <a name="see-also"></a><span data-ttu-id="3a4f9-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a4f9-128">See also</span></span>

- [<span data-ttu-id="3a4f9-129">Propiedades indizadas</span><span class="sxs-lookup"><span data-stu-id="3a4f9-129">Indexed properties</span></span>](members/indexed-properties.md)
