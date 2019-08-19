---
title: Segmentos (F#)
description: Obtenga información sobre cómo usar los segmentos para F# los tipos de datos existentes y cómo definir sus propios segmentos para otros tipos de datos.
ms.date: 01/22/2019
ms.openlocfilehash: 3067982c2b4249312c7e9365bbfb994be840911d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627145"
---
# <a name="slices"></a><span data-ttu-id="f99de-103">Segmentos</span><span class="sxs-lookup"><span data-stu-id="f99de-103">Slices</span></span>

<span data-ttu-id="f99de-104">En F#, un segmento es un subconjunto de un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="f99de-104">In F#, a slice is a subset of a data type.</span></span> <span data-ttu-id="f99de-105">Para poder tomar un segmento de un tipo de datos, el tipo de datos debe definir un `GetSlice` método o una extensión de [tipo](type-extensions.md) que esté en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="f99de-105">To be able to take a slice from a data type, the data type must either define a `GetSlice` method or in a [type extension](type-extensions.md) that is in scope.</span></span> <span data-ttu-id="f99de-106">En este artículo se explica cómo tomar los segmentos F# de los tipos existentes y cómo definir los suyos propios.</span><span class="sxs-lookup"><span data-stu-id="f99de-106">This article explains how to take slices from existing F# types and how to define your own.</span></span>

<span data-ttu-id="f99de-107">Los segmentos son similares a los [indizadores](./members/indexed-properties.md), pero en lugar de producir un valor único de la estructura de datos subyacente, producen varios.</span><span class="sxs-lookup"><span data-stu-id="f99de-107">Slices are similar to [indexers](./members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="f99de-108">F#Actualmente tiene compatibilidad intrínseca con la segmentación de cadenas, listas, matrices y matrices 2D.</span><span class="sxs-lookup"><span data-stu-id="f99de-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="f99de-109">Segmentación básica con F# listas y matrices</span><span class="sxs-lookup"><span data-stu-id="f99de-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="f99de-110">Los tipos de datos más comunes que se segmentan F# son listas y matrices.</span><span class="sxs-lookup"><span data-stu-id="f99de-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="f99de-111">En el ejemplo siguiente se muestra cómo hacerlo con listas:</span><span class="sxs-lookup"><span data-stu-id="f99de-111">The following example demonstrates how to do this with lists:</span></span>

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

<span data-ttu-id="f99de-112">La segmentación de matrices es igual que las listas de segmentación:</span><span class="sxs-lookup"><span data-stu-id="f99de-112">Slicing arrays is just like slicing lists:</span></span>

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

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="f99de-113">Segmentar matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="f99de-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="f99de-114">F#admite matrices multidimensionales en la F# biblioteca principal.</span><span class="sxs-lookup"><span data-stu-id="f99de-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="f99de-115">Al igual que con las matrices unidimensionales, los segmentos de matrices multidimensionales también pueden ser útiles.</span><span class="sxs-lookup"><span data-stu-id="f99de-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="f99de-116">Sin embargo, la introducción de dimensiones adicionales asigna una sintaxis ligeramente diferente para que pueda tomar segmentos de filas y columnas específicas.</span><span class="sxs-lookup"><span data-stu-id="f99de-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="f99de-117">En los siguientes ejemplos se muestra cómo segmentar una matriz 2D:</span><span class="sxs-lookup"><span data-stu-id="f99de-117">The following examples demonstrate how to slice a 2D array:</span></span>

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

<span data-ttu-id="f99de-118">La F# biblioteca principal no define `GetSlice`para las matrices 3D.</span><span class="sxs-lookup"><span data-stu-id="f99de-118">The F# core library does not define `GetSlice`for 3D arrays.</span></span> <span data-ttu-id="f99de-119">Si desea segmentar esas u otras matrices de más dimensiones, debe definir el `GetSlice` miembro usted mismo.</span><span class="sxs-lookup"><span data-stu-id="f99de-119">If you wish to slice those or other arrays of more dimensions, you must define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="f99de-120">Definir segmentos para otras estructuras de datos</span><span class="sxs-lookup"><span data-stu-id="f99de-120">Defining slices for other data structures</span></span>

<span data-ttu-id="f99de-121">La F# biblioteca principal define los segmentos para un conjunto limitado de tipos.</span><span class="sxs-lookup"><span data-stu-id="f99de-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="f99de-122">Si desea definir segmentos para más tipos de datos, puede hacerlo en la propia definición de tipo o en una extensión de tipo.</span><span class="sxs-lookup"><span data-stu-id="f99de-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="f99de-123">Por ejemplo, aquí se muestra cómo podría definir los segmentos de <xref:System.ArraySegment%601> la clase para permitir una manipulación de datos adecuada:</span><span class="sxs-lookup"><span data-stu-id="f99de-123">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

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

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a><span data-ttu-id="f99de-124">Usar la inclusión para evitar la conversión boxing si es necesario</span><span class="sxs-lookup"><span data-stu-id="f99de-124">Use inlining to avoid boxing if it is necessary</span></span>

<span data-ttu-id="f99de-125">Si va a definir segmentos para un tipo que es realmente un struct, se recomienda que `inline` sea el `GetSlice` miembro.</span><span class="sxs-lookup"><span data-stu-id="f99de-125">If you are defining slices for a type that is actually a struct, we recommend that you `inline` the `GetSlice` member.</span></span> <span data-ttu-id="f99de-126">El F# compilador optimiza los argumentos opcionales, evitando las asignaciones de montón como resultado de la segmentación.</span><span class="sxs-lookup"><span data-stu-id="f99de-126">The F# compiler optimizes away the optional arguments, avoiding any heap allocations as a result of slicing.</span></span> <span data-ttu-id="f99de-127">Esto es muy importante para las construcciones de segmentación como, <xref:System.Span%601> por ejemplo, que no se pueden asignar en el montón.</span><span class="sxs-lookup"><span data-stu-id="f99de-127">This is critically important for slicing constructs such as <xref:System.Span%601> that cannot be allocated on the heap.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f99de-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f99de-128">See also</span></span>

- [<span data-ttu-id="f99de-129">Propiedades indizadas</span><span class="sxs-lookup"><span data-stu-id="f99de-129">Indexed properties</span></span>](./members/indexed-properties.md)
