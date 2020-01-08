---
title: Segmentos
description: Obtenga información sobre cómo usar los segmentos F# para los tipos de datos existentes y cómo definir sus propios segmentos para otros tipos de datos.
ms.date: 12/23/2019
ms.openlocfilehash: 3911139c7ce656043817eb23d30f3686555b6efe
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/29/2019
ms.locfileid: "75545104"
---
# <a name="slices"></a><span data-ttu-id="e467e-103">Segmentos</span><span class="sxs-lookup"><span data-stu-id="e467e-103">Slices</span></span>

<span data-ttu-id="e467e-104">En F#, un segmento es un subconjunto de cualquier tipo de datos que tenga un método `GetSlice` en su definición o en una [extensión de tipo](type-extensions.md)en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="e467e-104">In F#, a slice is a subset of any data type that has a `GetSlice` method in its definition or in an in-scope [type extension](type-extensions.md).</span></span> <span data-ttu-id="e467e-105">Normalmente se usa con F# matrices y listas.</span><span class="sxs-lookup"><span data-stu-id="e467e-105">It is most commonly used with F# arrays and lists.</span></span> <span data-ttu-id="e467e-106">En este artículo se explica cómo tomar los segmentos F# de los tipos existentes y cómo definir sus propios segmentos.</span><span class="sxs-lookup"><span data-stu-id="e467e-106">This article explains how to take slices from existing F# types and how to define your own slices.</span></span>

<span data-ttu-id="e467e-107">Los segmentos son similares a los [indizadores](./members/indexed-properties.md), pero en lugar de producir un valor único de la estructura de datos subyacente, producen varios.</span><span class="sxs-lookup"><span data-stu-id="e467e-107">Slices are similar to [indexers](./members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="e467e-108">F#Actualmente tiene compatibilidad intrínseca con la segmentación de cadenas, listas, matrices y matrices 2D.</span><span class="sxs-lookup"><span data-stu-id="e467e-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="e467e-109">Segmentación básica con F# listas y matrices</span><span class="sxs-lookup"><span data-stu-id="e467e-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="e467e-110">Los tipos de datos más comunes que se segmentan F# son listas y matrices.</span><span class="sxs-lookup"><span data-stu-id="e467e-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="e467e-111">En el ejemplo siguiente se muestra cómo hacerlo con listas:</span><span class="sxs-lookup"><span data-stu-id="e467e-111">The following example demonstrates how to do this with lists:</span></span>

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

<span data-ttu-id="e467e-112">La segmentación de matrices es igual que las listas de segmentación:</span><span class="sxs-lookup"><span data-stu-id="e467e-112">Slicing arrays is just like slicing lists:</span></span>

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

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="e467e-113">Segmentar matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="e467e-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="e467e-114">F#admite matrices multidimensionales en la F# biblioteca principal.</span><span class="sxs-lookup"><span data-stu-id="e467e-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="e467e-115">Al igual que con las matrices unidimensionales, los segmentos de matrices multidimensionales también pueden ser útiles.</span><span class="sxs-lookup"><span data-stu-id="e467e-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="e467e-116">Sin embargo, la introducción de dimensiones adicionales asigna una sintaxis ligeramente diferente para que pueda tomar segmentos de filas y columnas específicas.</span><span class="sxs-lookup"><span data-stu-id="e467e-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="e467e-117">En los siguientes ejemplos se muestra cómo segmentar una matriz 2D:</span><span class="sxs-lookup"><span data-stu-id="e467e-117">The following examples demonstrate how to slice a 2D array:</span></span>

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

<span data-ttu-id="e467e-118">La F# biblioteca principal no define actualmente `GetSlice` para las matrices 3D.</span><span class="sxs-lookup"><span data-stu-id="e467e-118">The F# core library does not currently define `GetSlice` for 3D arrays.</span></span> <span data-ttu-id="e467e-119">Si desea segmentar matrices 3D u otras matrices de más dimensiones, defina el miembro de `GetSlice`.</span><span class="sxs-lookup"><span data-stu-id="e467e-119">If you wish to slice 3D arrays or other arrays of more dimensions, define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="e467e-120">Definir segmentos para otras estructuras de datos</span><span class="sxs-lookup"><span data-stu-id="e467e-120">Defining slices for other data structures</span></span>

<span data-ttu-id="e467e-121">La F# biblioteca principal define los segmentos para un conjunto limitado de tipos.</span><span class="sxs-lookup"><span data-stu-id="e467e-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="e467e-122">Si desea definir segmentos para más tipos de datos, puede hacerlo en la propia definición de tipo o en una extensión de tipo.</span><span class="sxs-lookup"><span data-stu-id="e467e-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="e467e-123">Por ejemplo, aquí se muestra cómo puede definir segmentos para la clase <xref:System.ArraySegment%601> para permitir una manipulación de datos adecuada:</span><span class="sxs-lookup"><span data-stu-id="e467e-123">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

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

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a><span data-ttu-id="e467e-124">Usar la inclusión para evitar la conversión boxing si es necesario</span><span class="sxs-lookup"><span data-stu-id="e467e-124">Use inlining to avoid boxing if it is necessary</span></span>

<span data-ttu-id="e467e-125">Si va a definir segmentos para un tipo que es realmente un struct, recomendamos que `inline` el miembro `GetSlice`.</span><span class="sxs-lookup"><span data-stu-id="e467e-125">If you are defining slices for a type that is actually a struct, we recommend that you `inline` the `GetSlice` member.</span></span> <span data-ttu-id="e467e-126">El F# compilador optimiza los argumentos opcionales, evitando las asignaciones de montón como resultado de la segmentación.</span><span class="sxs-lookup"><span data-stu-id="e467e-126">The F# compiler optimizes away the optional arguments, avoiding any heap allocations as a result of slicing.</span></span> <span data-ttu-id="e467e-127">Esto es muy importante para las construcciones de segmentación como <xref:System.Span%601> que no se pueden asignar en el montón.</span><span class="sxs-lookup"><span data-stu-id="e467e-127">This is critically important for slicing constructs such as <xref:System.Span%601> that cannot be allocated on the heap.</span></span>

```fsharp
open System

type ReadOnlySpan<'T> with
    // Note the 'inline' in the member definition
    member sp.GetSlice(startIdx, endIdx) =
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
printSpan sp.[1..2] // |2; 3|]
```

## <a name="built-in-f-slices-are-end-inclusive"></a><span data-ttu-id="e467e-128">Los F# segmentos integrados son de fin-inclusivo</span><span class="sxs-lookup"><span data-stu-id="e467e-128">Built-in F# slices are end-inclusive</span></span>

<span data-ttu-id="e467e-129">Todos los sectores intrínsecos de F# son de fin-inclusivo; es decir, el límite superior se incluye en el segmento.</span><span class="sxs-lookup"><span data-stu-id="e467e-129">All intrinsic slices in F# are end-inclusive; that is, the upper bound is included in the slice.</span></span> <span data-ttu-id="e467e-130">Para un segmento determinado con el índice de inicio `x` y el final `y`de índice, el segmento resultante incluirá el valor de *YTH* .</span><span class="sxs-lookup"><span data-stu-id="e467e-130">For a given slice with starting index `x` and ending index `y`, the resulting slice will include the *yth* value.</span></span>

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="see-also"></a><span data-ttu-id="e467e-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e467e-131">See also</span></span>

- [<span data-ttu-id="e467e-132">Propiedades indizadas</span><span class="sxs-lookup"><span data-stu-id="e467e-132">Indexed properties</span></span>](./members/indexed-properties.md)
