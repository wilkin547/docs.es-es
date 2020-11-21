---
title: Segmentos
description: 'Obtenga información sobre cómo usar los segmentos para los tipos de datos de F # existentes y cómo definir sus propios segmentos para otros tipos de datos.'
ms.date: 11/20/2020
ms.openlocfilehash: 9c072648ed46ae29871f2be5cc64b493f6a9b857
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "95098962"
---
# <a name="slices"></a><span data-ttu-id="c3b6c-103">Segmentos</span><span class="sxs-lookup"><span data-stu-id="c3b6c-103">Slices</span></span>

<span data-ttu-id="c3b6c-104">En este artículo se explica cómo tomar los segmentos de los tipos de F # existentes y cómo definir sus propios segmentos.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-104">This article explains how to take slices from existing F# types and how to define your own slices.</span></span>

<span data-ttu-id="c3b6c-105">En F #, un segmento es un subconjunto de cualquier tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-105">In F#, a slice is a subset of any data type.</span></span>  <span data-ttu-id="c3b6c-106">Los segmentos son similares a los [indizadores](./members/indexed-properties.md), pero en lugar de producir un valor único de la estructura de datos subyacente, producen varios.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-106">Slices are similar to [indexers](./members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span> <span data-ttu-id="c3b6c-107">Los segmentos utilizan la `..` Sintaxis del operador para seleccionar el intervalo de índices especificados en un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-107">Slices use the `..` operator syntax to select the range of specified indices in a data type.</span></span> <span data-ttu-id="c3b6c-108">Para obtener más información, vea el [artículo referencia de expresiones de bucle](./loops-for-in-expression.md).</span><span class="sxs-lookup"><span data-stu-id="c3b6c-108">For more information, see the [looping expression reference article](./loops-for-in-expression.md).</span></span>

<span data-ttu-id="c3b6c-109">F # tiene actualmente compatibilidad intrínseca con la segmentación de cadenas, listas, matrices y matrices multidimensionales (2D, 3D, 4D).</span><span class="sxs-lookup"><span data-stu-id="c3b6c-109">F# currently has intrinsic support for slicing strings, lists, arrays, and multidimensional (2D, 3D, 4D) arrays.</span></span> <span data-ttu-id="c3b6c-110">La segmentación se usa normalmente con matrices y listas de F #.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-110">Slicing is most commonly used with F# arrays and lists.</span></span> <span data-ttu-id="c3b6c-111">Puede Agregar la segmentación a los tipos de datos personalizados con el `GetSlice` método en la definición de tipo o en una extensión de [tipo](type-extensions.md)en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-111">You can add slicing to your custom data types by using the `GetSlice` method in your type definition or in an in-scope [type extension](type-extensions.md).</span></span>

## <a name="slicing-f-lists-and-arrays"></a><span data-ttu-id="c3b6c-112">Segmentar listas y matrices de F #</span><span class="sxs-lookup"><span data-stu-id="c3b6c-112">Slicing F# lists and arrays</span></span>

<span data-ttu-id="c3b6c-113">Los tipos de datos más comunes que se segmentan son listas y matrices de F #.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-113">The most common data types that are sliced are F# lists and arrays.</span></span>  <span data-ttu-id="c3b6c-114">En el ejemplo siguiente se muestra cómo segmentar listas:</span><span class="sxs-lookup"><span data-stu-id="c3b6c-114">The following example demonstrates how to slice lists:</span></span>

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

<span data-ttu-id="c3b6c-115">La segmentación de matrices es igual que las listas de segmentación:</span><span class="sxs-lookup"><span data-stu-id="c3b6c-115">Slicing arrays is just like slicing lists:</span></span>

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

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="c3b6c-116">Segmentar matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="c3b6c-116">Slicing multidimensional arrays</span></span>

<span data-ttu-id="c3b6c-117">F # admite matrices multidimensionales en la biblioteca básica de F #.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-117">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="c3b6c-118">Al igual que con las matrices unidimensionales, los segmentos de matrices multidimensionales también pueden ser útiles.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-118">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="c3b6c-119">Sin embargo, la introducción de dimensiones adicionales asigna una sintaxis ligeramente diferente para que pueda tomar segmentos de filas y columnas específicas.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-119">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="c3b6c-120">En los siguientes ejemplos se muestra cómo segmentar una matriz 2D:</span><span class="sxs-lookup"><span data-stu-id="c3b6c-120">The following examples demonstrate how to slice a 2D array:</span></span>

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

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="c3b6c-121">Definir segmentos para otras estructuras de datos</span><span class="sxs-lookup"><span data-stu-id="c3b6c-121">Defining slices for other data structures</span></span>

<span data-ttu-id="c3b6c-122">La biblioteca básica de F # define los segmentos para un conjunto limitado de tipos.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-122">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="c3b6c-123">Si desea definir segmentos para más tipos de datos, puede hacerlo en la propia definición de tipo o en una extensión de tipo.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-123">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="c3b6c-124">Por ejemplo, aquí se muestra cómo podría definir los segmentos de la <xref:System.ArraySegment%601> clase para permitir una manipulación de datos adecuada:</span><span class="sxs-lookup"><span data-stu-id="c3b6c-124">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

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

<span data-ttu-id="c3b6c-125">Otro ejemplo de uso de los <xref:System.Span%601> <xref:System.ReadOnlySpan%601> tipos y:</span><span class="sxs-lookup"><span data-stu-id="c3b6c-125">Another example using the <xref:System.Span%601> and <xref:System.ReadOnlySpan%601> types:</span></span>

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

## <a name="built-in-f-slices-are-end-inclusive"></a><span data-ttu-id="c3b6c-126">Los segmentos de F # integrados son de fin-inclusivo</span><span class="sxs-lookup"><span data-stu-id="c3b6c-126">Built-in F# slices are end-inclusive</span></span>

<span data-ttu-id="c3b6c-127">Todos los segmentos intrínsecos de F # son de fin-inclusivo; es decir, el límite superior se incluye en el segmento.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-127">All intrinsic slices in F# are end-inclusive; that is, the upper bound is included in the slice.</span></span> <span data-ttu-id="c3b6c-128">Para un segmento determinado con el índice `x` de inicio y `y` el de finalización, el segmento resultante incluirá el valor de *YTH* .</span><span class="sxs-lookup"><span data-stu-id="c3b6c-128">For a given slice with starting index `x` and ending index `y`, the resulting slice will include the *yth* value.</span></span>

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="built-in-f-empty-slices"></a><span data-ttu-id="c3b6c-129">Segmentos vacíos de F # integrados</span><span class="sxs-lookup"><span data-stu-id="c3b6c-129">Built-in F# empty slices</span></span>

<span data-ttu-id="c3b6c-130">Las listas de F #, matrices, secuencias, cadenas, matrices multidimensionales (2D, 3D, 4D) producirán un segmento vacío si la sintaxis podría producir un segmento que no existe.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-130">F# lists, arrays, sequences, strings, multidimensional (2D, 3D, 4D) arrays will all produce an empty slice if the syntax could produce a slice that doesn't exist.</span></span>

<span data-ttu-id="c3b6c-131">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3b6c-131">Consider the following example:</span></span>

```fsharp
let l = [ 1..10 ]
let a = [| 1..10 |]
let s = "hello!"

let emptyList = l.[-2..(-1)]
let emptyArray = a.[-2..(-1)]
let emptyString = s.[-2..(-1)]
```

> [!IMPORTANT]
> <span data-ttu-id="c3b6c-132">Los desarrolladores de C# pueden esperar que se produzca una excepción en lugar de producir un segmento vacío.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-132">C# developers may expect these to throw an exception rather than produce an empty slice.</span></span> <span data-ttu-id="c3b6c-133">Se trata de una decisión de diseño que se basa en el hecho de que las colecciones vacías se componen en F #.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-133">This is a design decision rooted in the fact that empty collections compose in F#.</span></span> <span data-ttu-id="c3b6c-134">Una lista vacía de F # puede estar formada por otra lista de F #, una cadena vacía se puede Agregar a una cadena existente, etc.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-134">An empty F# list can be composed with another F# list, an empty string can be added to an existing string, and so on.</span></span> <span data-ttu-id="c3b6c-135">Puede ser común tomar los segmentos en función de los valores pasados como parámetros y tolerar los límites fuera de los límites > mediante la generación de una colección vacía se ajusta a la naturaleza de composición del código de F #.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-135">It can be common to take slices based on values passed in as parameters, and being tolerant of out-of-bounds > by producing an empty collection fits with the compositional nature of F# code.</span></span>

## <a name="fixed-index-slices-for-3d-and-4d-arrays"></a><span data-ttu-id="c3b6c-136">Segmentos de índice fijo para matrices 3D y 4D</span><span class="sxs-lookup"><span data-stu-id="c3b6c-136">Fixed-index slices for 3D and 4D arrays</span></span>

<span data-ttu-id="c3b6c-137">En el caso de las matrices F # 3D y 4D, puede "corregir" un índice determinado y segmentar otras dimensiones con ese índice fijo.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-137">For F# 3D and 4D arrays, you can "fix" a particular index and slice other dimensions with that index fixed.</span></span>

<span data-ttu-id="c3b6c-138">Para ilustrar esto, considere la siguiente matriz 3D:</span><span class="sxs-lookup"><span data-stu-id="c3b6c-138">To illustrate this, consider the following 3D array:</span></span>

<span data-ttu-id="c3b6c-139">*z = 0*</span><span class="sxs-lookup"><span data-stu-id="c3b6c-139">*z = 0*</span></span>

| <span data-ttu-id="c3b6c-140">x\y</span><span class="sxs-lookup"><span data-stu-id="c3b6c-140">x\y</span></span>   | <span data-ttu-id="c3b6c-141">0</span><span class="sxs-lookup"><span data-stu-id="c3b6c-141">0</span></span> | <span data-ttu-id="c3b6c-142">1</span><span class="sxs-lookup"><span data-stu-id="c3b6c-142">1</span></span> |
|-------|---|---|
| <span data-ttu-id="c3b6c-143">**0**</span><span class="sxs-lookup"><span data-stu-id="c3b6c-143">**0**</span></span> | <span data-ttu-id="c3b6c-144">0</span><span class="sxs-lookup"><span data-stu-id="c3b6c-144">0</span></span> | <span data-ttu-id="c3b6c-145">1</span><span class="sxs-lookup"><span data-stu-id="c3b6c-145">1</span></span> |
| <span data-ttu-id="c3b6c-146">**1**</span><span class="sxs-lookup"><span data-stu-id="c3b6c-146">**1**</span></span> | <span data-ttu-id="c3b6c-147">2</span><span class="sxs-lookup"><span data-stu-id="c3b6c-147">2</span></span> | <span data-ttu-id="c3b6c-148">3</span><span class="sxs-lookup"><span data-stu-id="c3b6c-148">3</span></span> |

<span data-ttu-id="c3b6c-149">*z = 1*</span><span class="sxs-lookup"><span data-stu-id="c3b6c-149">*z = 1*</span></span>

| <span data-ttu-id="c3b6c-150">x\y</span><span class="sxs-lookup"><span data-stu-id="c3b6c-150">x\y</span></span>   | <span data-ttu-id="c3b6c-151">0</span><span class="sxs-lookup"><span data-stu-id="c3b6c-151">0</span></span> | <span data-ttu-id="c3b6c-152">1</span><span class="sxs-lookup"><span data-stu-id="c3b6c-152">1</span></span> |
|-------|---|---|
| <span data-ttu-id="c3b6c-153">**0**</span><span class="sxs-lookup"><span data-stu-id="c3b6c-153">**0**</span></span> | <span data-ttu-id="c3b6c-154">4</span><span class="sxs-lookup"><span data-stu-id="c3b6c-154">4</span></span> | <span data-ttu-id="c3b6c-155">5</span><span class="sxs-lookup"><span data-stu-id="c3b6c-155">5</span></span> |
| <span data-ttu-id="c3b6c-156">**1**</span><span class="sxs-lookup"><span data-stu-id="c3b6c-156">**1**</span></span> | <span data-ttu-id="c3b6c-157">6</span><span class="sxs-lookup"><span data-stu-id="c3b6c-157">6</span></span> | <span data-ttu-id="c3b6c-158">7</span><span class="sxs-lookup"><span data-stu-id="c3b6c-158">7</span></span> |

<span data-ttu-id="c3b6c-159">Si desea extraer el segmento `[| 4; 5 |]` de la matriz, use un segmento de índice fijo.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-159">If you want to extract the slice `[| 4; 5 |]` from the array, use a fixed-index slice.</span></span>

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

<span data-ttu-id="c3b6c-160">La última línea corrige los `y` `z` índices e de la matriz 3D y toma el resto de los `x` valores que corresponden a la matriz.</span><span class="sxs-lookup"><span data-stu-id="c3b6c-160">The last line fixes the `y` and `z` indices of the 3D array and takes the rest of the `x` values that correspond to the matrix.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3b6c-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3b6c-161">See also</span></span>

- [<span data-ttu-id="c3b6c-162">Propiedades indizadas</span><span class="sxs-lookup"><span data-stu-id="c3b6c-162">Indexed properties</span></span>](./members/indexed-properties.md)
