---
title: Explorar los intervalos de datos con índices y rangos
description: En este tutorial avanzado se explica cómo explorar datos con índices e intervalos para examinar los segmentos de un conjunto de datos secuencial.
ms.date: 04/19/2019
ms.custom: mvc
ms.openlocfilehash: d53f32bcb310d4859cea67a742ac0e2c4be5d942
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70105786"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="a6e98-103">Índices y rangos</span><span class="sxs-lookup"><span data-stu-id="a6e98-103">Indices and ranges</span></span>

<span data-ttu-id="a6e98-104">Los rangos e índices proporcionan una sintaxis concisa para acceder a elementos únicos o intervalos en una <xref:System.Array>, <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="a6e98-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in an <xref:System.Array>, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="a6e98-105">Estas características permiten una sintaxis más concisa y clara para acceder a elementos únicos o intervalos de elementos de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="a6e98-105">These features enable more concise, clear syntax to access single elements or ranges of elements in a sequence.</span></span>

<span data-ttu-id="a6e98-106">En este tutorial aprenderá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a6e98-106">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> - <span data-ttu-id="a6e98-107">Usar la sintaxis para intervalos de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="a6e98-107">Use the syntax for ranges in a sequence.</span></span>
> - <span data-ttu-id="a6e98-108">Comprender las decisiones de diseño para iniciar y finalizar cada secuencia.</span><span class="sxs-lookup"><span data-stu-id="a6e98-108">Understand the design decisions for the start and end of each sequence.</span></span>
> - <span data-ttu-id="a6e98-109">Descubrir escenarios para los tipos <xref:System.Index> y <xref:System.Range>.</span><span class="sxs-lookup"><span data-stu-id="a6e98-109">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="a6e98-110">Compatibilidad con idiomas para los índices y los rangos</span><span class="sxs-lookup"><span data-stu-id="a6e98-110">Language support for indices and ranges</span></span>

<span data-ttu-id="a6e98-111">Esta compatibilidad con idiomas se basa en dos nuevos tipos y dos nuevos operadores.</span><span class="sxs-lookup"><span data-stu-id="a6e98-111">This language support relies on two new types and two new operators.</span></span>
- <span data-ttu-id="a6e98-112"><xref:System.Index?displayProperty=nameWithType> representa un índice en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="a6e98-112"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="a6e98-113">El operador `^`, que especifica que un índice es relativo al final de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="a6e98-113">The `^` operator, which specifies that an index is relative to the end of a sequence.</span></span>
- <span data-ttu-id="a6e98-114"><xref:System.Range?displayProperty=nameWithType> representa un subrango de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="a6e98-114"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="a6e98-115">El operador de rango (`..`), que especifica el inicio y el fin de un intervalo como sus operandos.</span><span class="sxs-lookup"><span data-stu-id="a6e98-115">The Range operator (`..`), which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="a6e98-116">Comencemos con las reglas de los índices.</span><span class="sxs-lookup"><span data-stu-id="a6e98-116">Let's start with the rules for indices.</span></span> <span data-ttu-id="a6e98-117">Considere un elemento `sequence` de matriz.</span><span class="sxs-lookup"><span data-stu-id="a6e98-117">Consider an array `sequence`.</span></span> <span data-ttu-id="a6e98-118">El índice `0` es igual que `sequence[0]`.</span><span class="sxs-lookup"><span data-stu-id="a6e98-118">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="a6e98-119">El índice `^0` es igual que `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="a6e98-119">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="a6e98-120">Tenga en cuenta que `sequence[^0]` produce una excepción, al igual que `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="a6e98-120">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="a6e98-121">Para cualquier número `n`, el índice `^n` es igual que `sequence[sequence.Length - n]`.</span><span class="sxs-lookup"><span data-stu-id="a6e98-121">For any number `n`, the index `^n` is the same as `sequence[sequence.Length - n]`.</span></span>

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

<span data-ttu-id="a6e98-122">Puede recuperar la última palabra con el índice `^1`.</span><span class="sxs-lookup"><span data-stu-id="a6e98-122">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="a6e98-123">Agregue el código siguiente a la inicialización:</span><span class="sxs-lookup"><span data-stu-id="a6e98-123">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="a6e98-124">Un rango especifica el *inicio* y el *final* de un intervalo.</span><span class="sxs-lookup"><span data-stu-id="a6e98-124">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="a6e98-125">Los rangos son excluyentes, lo que significa que el *final* no se incluye en el intervalo.</span><span class="sxs-lookup"><span data-stu-id="a6e98-125">Ranges are exclusive, meaning the *end* is not included in the range.</span></span> <span data-ttu-id="a6e98-126">El rango `[0..^0]` representa todo el intervalo, al igual que `[0..sequence.Length]` representa todo el intervalo.</span><span class="sxs-lookup"><span data-stu-id="a6e98-126">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span> 

<span data-ttu-id="a6e98-127">El siguiente código crea un subrango con las palabras "quick", "brown" y "fox".</span><span class="sxs-lookup"><span data-stu-id="a6e98-127">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="a6e98-128">Va de `words[1]` a `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="a6e98-128">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="a6e98-129">El elemento `words[4]` no se encuentra en el intervalo.</span><span class="sxs-lookup"><span data-stu-id="a6e98-129">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="a6e98-130">Agregue el código siguiente al mismo método.</span><span class="sxs-lookup"><span data-stu-id="a6e98-130">Add the following code to the same method.</span></span> <span data-ttu-id="a6e98-131">Cópielo y péguelo en la parte inferior de la ventana interactiva.</span><span class="sxs-lookup"><span data-stu-id="a6e98-131">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="a6e98-132">El siguiente código crea un subrango con "lazy" y "dog".</span><span class="sxs-lookup"><span data-stu-id="a6e98-132">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="a6e98-133">Incluye `words[^2]` y `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="a6e98-133">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="a6e98-134">El índice del final `words[^0]` no se incluye.</span><span class="sxs-lookup"><span data-stu-id="a6e98-134">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="a6e98-135">Agregue el código siguiente también:</span><span class="sxs-lookup"><span data-stu-id="a6e98-135">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="a6e98-136">En los ejemplos siguientes se crean rangos con final abierto para el inicio, el final o ambos:</span><span class="sxs-lookup"><span data-stu-id="a6e98-136">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="a6e98-137">También puede declarar rangos o índices como variables.</span><span class="sxs-lookup"><span data-stu-id="a6e98-137">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="a6e98-138">La variable se puede usar luego dentro de los caracteres `[` y `]`:</span><span class="sxs-lookup"><span data-stu-id="a6e98-138">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="a6e98-139">El ejemplo siguiente muestra muchos de los motivos para esas opciones.</span><span class="sxs-lookup"><span data-stu-id="a6e98-139">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="a6e98-140">Modifique `x`, `y` y `z` para probar diferentes combinaciones.</span><span class="sxs-lookup"><span data-stu-id="a6e98-140">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="a6e98-141">Al experimentar, use valores donde `x` sea menor que `y` y `y` sea menor que `z` para las combinaciones válidas.</span><span class="sxs-lookup"><span data-stu-id="a6e98-141">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="a6e98-142">Agregue el código siguiente a un nuevo método.</span><span class="sxs-lookup"><span data-stu-id="a6e98-142">Add the following code in a new method.</span></span> <span data-ttu-id="a6e98-143">Pruebe diferentes combinaciones:</span><span class="sxs-lookup"><span data-stu-id="a6e98-143">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="a6e98-144">Escenarios para los índices y los rangos</span><span class="sxs-lookup"><span data-stu-id="a6e98-144">Scenarios for Indices and Ranges</span></span>

<span data-ttu-id="a6e98-145">A menudo usará rangos e índices cuando desee realizar un poco de análisis en el subrango de una secuencia completa.</span><span class="sxs-lookup"><span data-stu-id="a6e98-145">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="a6e98-146">La nueva sintaxis es más clara al leer exactamente lo que implica el subrango.</span><span class="sxs-lookup"><span data-stu-id="a6e98-146">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="a6e98-147">La función local `MovingAverage` toma un <xref:System.Range> como su argumento.</span><span class="sxs-lookup"><span data-stu-id="a6e98-147">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="a6e98-148">El método enumera solo ese rango al calcular el mínimo, el máximo y la media.</span><span class="sxs-lookup"><span data-stu-id="a6e98-148">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="a6e98-149">Pruebe con el código siguiente en su proyecto:</span><span class="sxs-lookup"><span data-stu-id="a6e98-149">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="a6e98-150">Puede descargar el código completado del repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes).</span><span class="sxs-lookup"><span data-stu-id="a6e98-150">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
