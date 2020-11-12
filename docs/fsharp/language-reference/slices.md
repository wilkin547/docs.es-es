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
# <a name="slices"></a><span data-ttu-id="64cfc-103">Segmentos</span><span class="sxs-lookup"><span data-stu-id="64cfc-103">Slices</span></span>

<span data-ttu-id="64cfc-104">En F #, un segmento es un subconjunto de cualquier tipo de datos que tenga un `GetSlice` método en su definición o en una [extensión de tipo](type-extensions.md)en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="64cfc-104">In F#, a slice is a subset of any data type that has a `GetSlice` method in its definition or in an in-scope [type extension](type-extensions.md).</span></span> <span data-ttu-id="64cfc-105">Se usa normalmente con matrices y listas de F #.</span><span class="sxs-lookup"><span data-stu-id="64cfc-105">It is most commonly used with F# arrays and lists.</span></span> <span data-ttu-id="64cfc-106">En este artículo se explica cómo tomar los segmentos de los tipos de F # existentes y cómo definir sus propios segmentos.</span><span class="sxs-lookup"><span data-stu-id="64cfc-106">This article explains how to take slices from existing F# types and how to define your own slices.</span></span>

<span data-ttu-id="64cfc-107">Los segmentos son similares a los [indizadores](./members/indexed-properties.md), pero en lugar de producir un valor único de la estructura de datos subyacente, producen varios.</span><span class="sxs-lookup"><span data-stu-id="64cfc-107">Slices are similar to [indexers](./members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="64cfc-108">F # tiene actualmente compatibilidad intrínseca con la segmentación de cadenas, listas, matrices y matrices 2D.</span><span class="sxs-lookup"><span data-stu-id="64cfc-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="64cfc-109">Segmentación básica con listas y matrices de F #</span><span class="sxs-lookup"><span data-stu-id="64cfc-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="64cfc-110">Los tipos de datos más comunes que se segmentan son listas y matrices de F #.</span><span class="sxs-lookup"><span data-stu-id="64cfc-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="64cfc-111">En el ejemplo siguiente se muestra cómo hacerlo con listas:</span><span class="sxs-lookup"><span data-stu-id="64cfc-111">The following example demonstrates how to do this with lists:</span></span>

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

<span data-ttu-id="64cfc-112">La segmentación de matrices es igual que las listas de segmentación:</span><span class="sxs-lookup"><span data-stu-id="64cfc-112">Slicing arrays is just like slicing lists:</span></span>

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

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="64cfc-113">Segmentar matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="64cfc-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="64cfc-114">F # admite matrices multidimensionales en la biblioteca básica de F #.</span><span class="sxs-lookup"><span data-stu-id="64cfc-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="64cfc-115">Al igual que con las matrices unidimensionales, los segmentos de matrices multidimensionales también pueden ser útiles.</span><span class="sxs-lookup"><span data-stu-id="64cfc-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="64cfc-116">Sin embargo, la introducción de dimensiones adicionales asigna una sintaxis ligeramente diferente para que pueda tomar segmentos de filas y columnas específicas.</span><span class="sxs-lookup"><span data-stu-id="64cfc-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="64cfc-117">En los siguientes ejemplos se muestra cómo segmentar una matriz 2D:</span><span class="sxs-lookup"><span data-stu-id="64cfc-117">The following examples demonstrate how to slice a 2D array:</span></span>

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

<span data-ttu-id="64cfc-118">La biblioteca básica de F # no define actualmente `GetSlice` para las matrices 3D.</span><span class="sxs-lookup"><span data-stu-id="64cfc-118">The F# core library does not currently define `GetSlice` for 3D arrays.</span></span> <span data-ttu-id="64cfc-119">Si desea segmentar matrices 3D u otras matrices de más dimensiones, defina el `GetSlice` miembro usted mismo.</span><span class="sxs-lookup"><span data-stu-id="64cfc-119">If you wish to slice 3D arrays or other arrays of more dimensions, define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="64cfc-120">Definir segmentos para otras estructuras de datos</span><span class="sxs-lookup"><span data-stu-id="64cfc-120">Defining slices for other data structures</span></span>

<span data-ttu-id="64cfc-121">La biblioteca básica de F # define los segmentos para un conjunto limitado de tipos.</span><span class="sxs-lookup"><span data-stu-id="64cfc-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="64cfc-122">Si desea definir segmentos para más tipos de datos, puede hacerlo en la propia definición de tipo o en una extensión de tipo.</span><span class="sxs-lookup"><span data-stu-id="64cfc-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="64cfc-123">Por ejemplo, aquí se muestra cómo podría definir los segmentos de la <xref:System.ArraySegment%601> clase para permitir una manipulación de datos adecuada:</span><span class="sxs-lookup"><span data-stu-id="64cfc-123">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

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

<span data-ttu-id="64cfc-124">Otro ejemplo de uso de los <xref:System.Span%601> <xref:System.ReadOnlySpan%601> tipos y:</span><span class="sxs-lookup"><span data-stu-id="64cfc-124">Another example using the <xref:System.Span%601> and <xref:System.ReadOnlySpan%601> types:</span></span>

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

## <a name="built-in-f-slices-are-end-inclusive"></a><span data-ttu-id="64cfc-125">Los segmentos de F # integrados son de fin-inclusivo</span><span class="sxs-lookup"><span data-stu-id="64cfc-125">Built-in F# slices are end-inclusive</span></span>

<span data-ttu-id="64cfc-126">Todos los segmentos intrínsecos de F # son de fin-inclusivo; es decir, el límite superior se incluye en el segmento.</span><span class="sxs-lookup"><span data-stu-id="64cfc-126">All intrinsic slices in F# are end-inclusive; that is, the upper bound is included in the slice.</span></span> <span data-ttu-id="64cfc-127">Para un segmento determinado con el índice `x` de inicio y `y` el de finalización, el segmento resultante incluirá el valor de *YTH* .</span><span class="sxs-lookup"><span data-stu-id="64cfc-127">For a given slice with starting index `x` and ending index `y`, the resulting slice will include the *yth* value.</span></span>

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="built-in-f-empty-slices"></a><span data-ttu-id="64cfc-128">Segmentos vacíos de F # integrados</span><span class="sxs-lookup"><span data-stu-id="64cfc-128">Built-in F# empty slices</span></span>

<span data-ttu-id="64cfc-129">Las listas, matrices, secuencias, cadenas, matrices 2D, matrices 3D y 4D matrices de F # producirán un segmento vacío si la sintaxis podría producir un segmento que no existe.</span><span class="sxs-lookup"><span data-stu-id="64cfc-129">F# lists, arrays, sequences, strings, 2D arrays, 3D arrays, and 4D arrays will all produce an empty slice if the syntax could produce a slice that doesn't exist.</span></span>

<span data-ttu-id="64cfc-130">Tenga en cuenta lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="64cfc-130">Consider the following:</span></span>

```fsharp
let l = [ 1..10 ]
let a = [| 1..10 |]
let s = "hello!"

let emptyList = l.[-2..(-1)]
let emptyArray = a.[-2..(-1)]
let emptyString = s.[-2..(-1)]
```

<span data-ttu-id="64cfc-131">Los desarrolladores de C# pueden esperar que se produzca una excepción en lugar de producir un segmento vacío.</span><span class="sxs-lookup"><span data-stu-id="64cfc-131">C# developers may expect these to throw an exception rather than produce an empty slice.</span></span> <span data-ttu-id="64cfc-132">Se trata de una decisión de diseño que se basa en el hecho de que las colecciones vacías se componen en F #.</span><span class="sxs-lookup"><span data-stu-id="64cfc-132">This is a design decision rooted in the fact that empty collections compose in F#.</span></span> <span data-ttu-id="64cfc-133">Una lista vacía de F # puede estar formada por otra lista de F #, una cadena vacía se puede Agregar a una cadena existente, etc.</span><span class="sxs-lookup"><span data-stu-id="64cfc-133">An empty F# list can be composed with another F# list, an empty string can be added to an existing string, and so on.</span></span> <span data-ttu-id="64cfc-134">Puede ser común tomar los segmentos en función de los valores pasados como parámetros y ser tolerante de los límites fuera de los límites mediante la generación de una colección vacía que se ajusta a la naturaleza de composición del código de F #.</span><span class="sxs-lookup"><span data-stu-id="64cfc-134">It can be common to take slices based on values passed in as parameters, and being tolerant of out-of-bounds by producing an empty collection fits with the compositional nature of F# code.</span></span>

## <a name="fixed-index-slices-for-3d-and-4d-arrays"></a><span data-ttu-id="64cfc-135">Segmentos de índice fijo para matrices 3D y 4D</span><span class="sxs-lookup"><span data-stu-id="64cfc-135">Fixed-index slices for 3D and 4D arrays</span></span>

<span data-ttu-id="64cfc-136">En el caso de las matrices F # 3D y 4D, puede "corregir" un índice determinado y segmentar otras dimensiones con ese índice fijo.</span><span class="sxs-lookup"><span data-stu-id="64cfc-136">For F# 3D and 4D arrays, you can "fix" a particular index and slice other dimensions with that index fixed.</span></span>

<span data-ttu-id="64cfc-137">Para ilustrar esto, considere la siguiente matriz 3D:</span><span class="sxs-lookup"><span data-stu-id="64cfc-137">To illustrate this, consider the following 3D array:</span></span>

<span data-ttu-id="64cfc-138">*z = 0*</span><span class="sxs-lookup"><span data-stu-id="64cfc-138">*z = 0*</span></span>
| <span data-ttu-id="64cfc-139">x\y</span><span class="sxs-lookup"><span data-stu-id="64cfc-139">x\y</span></span>   | <span data-ttu-id="64cfc-140">0</span><span class="sxs-lookup"><span data-stu-id="64cfc-140">0</span></span> | <span data-ttu-id="64cfc-141">1</span><span class="sxs-lookup"><span data-stu-id="64cfc-141">1</span></span> |
|-------|---|---|
| <span data-ttu-id="64cfc-142">**0**</span><span class="sxs-lookup"><span data-stu-id="64cfc-142">**0**</span></span> | <span data-ttu-id="64cfc-143">0</span><span class="sxs-lookup"><span data-stu-id="64cfc-143">0</span></span> | <span data-ttu-id="64cfc-144">1</span><span class="sxs-lookup"><span data-stu-id="64cfc-144">1</span></span> |
| <span data-ttu-id="64cfc-145">**1**</span><span class="sxs-lookup"><span data-stu-id="64cfc-145">**1**</span></span> | <span data-ttu-id="64cfc-146">2</span><span class="sxs-lookup"><span data-stu-id="64cfc-146">2</span></span> | <span data-ttu-id="64cfc-147">3</span><span class="sxs-lookup"><span data-stu-id="64cfc-147">3</span></span> |

<span data-ttu-id="64cfc-148">*z = 1*</span><span class="sxs-lookup"><span data-stu-id="64cfc-148">*z = 1*</span></span>
| <span data-ttu-id="64cfc-149">x\y</span><span class="sxs-lookup"><span data-stu-id="64cfc-149">x\y</span></span>   | <span data-ttu-id="64cfc-150">0</span><span class="sxs-lookup"><span data-stu-id="64cfc-150">0</span></span> | <span data-ttu-id="64cfc-151">1</span><span class="sxs-lookup"><span data-stu-id="64cfc-151">1</span></span> |
|-------|---|---|
| <span data-ttu-id="64cfc-152">**0**</span><span class="sxs-lookup"><span data-stu-id="64cfc-152">**0**</span></span> | <span data-ttu-id="64cfc-153">4</span><span class="sxs-lookup"><span data-stu-id="64cfc-153">4</span></span> | <span data-ttu-id="64cfc-154">5</span><span class="sxs-lookup"><span data-stu-id="64cfc-154">5</span></span> |
| <span data-ttu-id="64cfc-155">**1**</span><span class="sxs-lookup"><span data-stu-id="64cfc-155">**1**</span></span> | <span data-ttu-id="64cfc-156">6</span><span class="sxs-lookup"><span data-stu-id="64cfc-156">6</span></span> | <span data-ttu-id="64cfc-157">7</span><span class="sxs-lookup"><span data-stu-id="64cfc-157">7</span></span> |

<span data-ttu-id="64cfc-158">Si desea extraer el segmento `[| 4; 5 |]` de la matriz, use un segmento de índice fijo.</span><span class="sxs-lookup"><span data-stu-id="64cfc-158">If you want to extract the slice `[| 4; 5 |]` from the array, use a fixed-index slice.</span></span>

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

<span data-ttu-id="64cfc-159">La última línea corrige las `y` `z` lenguas y de la matriz 3D y toma el resto de los `x` valores que corresponden a la matriz.</span><span class="sxs-lookup"><span data-stu-id="64cfc-159">The last line fixes the `y` and `z` indicies of the 3D array and takes the rest of the `x` values that correspond to the matrix.</span></span>

## <a name="see-also"></a><span data-ttu-id="64cfc-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64cfc-160">See also</span></span>

- [<span data-ttu-id="64cfc-161">Propiedades indizadas</span><span class="sxs-lookup"><span data-stu-id="64cfc-161">Indexed properties</span></span>](./members/indexed-properties.md)
