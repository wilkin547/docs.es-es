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
# <a name="indices-and-ranges"></a><span data-ttu-id="fbc28-103">Índices y rangos</span><span class="sxs-lookup"><span data-stu-id="fbc28-103">Indices and ranges</span></span>

<span data-ttu-id="fbc28-104">Los rangos e índices proporcionan una sintaxis concisa para acceder a elementos únicos o intervalos en una <xref:System.Array>, <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="fbc28-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in an <xref:System.Array>, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="fbc28-105">Estas características permiten una sintaxis más concisa y clara para acceder a elementos únicos o intervalos de elementos de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="fbc28-105">These features enable more concise, clear syntax to access single elements or ranges of elements in a sequence.</span></span>

<span data-ttu-id="fbc28-106">En este tutorial aprenderá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fbc28-106">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="fbc28-107">Usar la sintaxis para intervalos de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="fbc28-107">Use the syntax for ranges in a sequence.</span></span>
> * <span data-ttu-id="fbc28-108">Comprender las decisiones de diseño para iniciar y finalizar cada secuencia.</span><span class="sxs-lookup"><span data-stu-id="fbc28-108">Understand the design decisions for the start and end of each sequence.</span></span>
> * <span data-ttu-id="fbc28-109">Descubrir escenarios para los tipos <xref:System.Index> y <xref:System.Range>.</span><span class="sxs-lookup"><span data-stu-id="fbc28-109">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="fbc28-110">Compatibilidad con idiomas para los índices y los rangos</span><span class="sxs-lookup"><span data-stu-id="fbc28-110">Language support for indices and ranges</span></span>

<span data-ttu-id="fbc28-111">Puede especificar un índice **desde el final** mediante el carácter `^` antes del índice.</span><span class="sxs-lookup"><span data-stu-id="fbc28-111">You can specify an index **from the end** using the `^` character before the index.</span></span> <span data-ttu-id="fbc28-112">La indexación desde el final se inicia con la regla que `0..^0` especifica el intervalo completo.</span><span class="sxs-lookup"><span data-stu-id="fbc28-112">Indexing from the end starts from the rule that `0..^0` specifies the entire range.</span></span> <span data-ttu-id="fbc28-113">Para enumerar toda una matriz, empiece *en el primer elemento* y continúe hasta *rebasar el último elemento*.</span><span class="sxs-lookup"><span data-stu-id="fbc28-113">To enumerate an entire array, you start *at the first element*, and continue until you are *past the last element*.</span></span> <span data-ttu-id="fbc28-114">Piense en el comportamiento del método `MoveNext` en un enumerador: devuelve false cuando la enumeración rebasa el último elemento.</span><span class="sxs-lookup"><span data-stu-id="fbc28-114">Think of the behavior of the `MoveNext` method on an enumerator: it returns false when the enumeration passes the last element.</span></span> <span data-ttu-id="fbc28-115">El índice `^0` significa "el final", `array[array.Length]`, o el índice que sigue al último elemento.</span><span class="sxs-lookup"><span data-stu-id="fbc28-115">The index `^0` means "the end", `array[array.Length]`, or the index that follows the last element.</span></span> <span data-ttu-id="fbc28-116">Está familiarizado con `array[2]` lo que significa el elemento "2 desde el principio".</span><span class="sxs-lookup"><span data-stu-id="fbc28-116">You are familiar with `array[2]` meaning the element "2 from the start".</span></span> <span data-ttu-id="fbc28-117">Ahora, `array[^2]` significa el elemento "2 desde el final".</span><span class="sxs-lookup"><span data-stu-id="fbc28-117">Now, `array[^2]` means the element "2 from the end".</span></span> 

<span data-ttu-id="fbc28-118">Puede especificar un **rango** con el **operador de rango**: `..`.</span><span class="sxs-lookup"><span data-stu-id="fbc28-118">You can specify a **range** with the **range operator**: `..`.</span></span> <span data-ttu-id="fbc28-119">Por ejemplo, `0..^0` especifica el rango completo de la matriz: 0 desde el principio hasta, pero sin incluir 0 desde el final.</span><span class="sxs-lookup"><span data-stu-id="fbc28-119">For example, `0..^0` specifies the entire range of the array: 0 from the start up to, but not including 0 from the end.</span></span> <span data-ttu-id="fbc28-120">Cualquier operando puede usar "desde el principio" o "desde el final".</span><span class="sxs-lookup"><span data-stu-id="fbc28-120">Either operand may use "from the start" or "from the end".</span></span> <span data-ttu-id="fbc28-121">Además, se puede omitir cualquier operando.</span><span class="sxs-lookup"><span data-stu-id="fbc28-121">Furthermore, either operand may be omitted.</span></span> <span data-ttu-id="fbc28-122">Los valores predeterminados son `0` para el índice de inicio y `^0` para el índice de final.</span><span class="sxs-lookup"><span data-stu-id="fbc28-122">The defaults are `0` for the start index, and `^0` for the end index.</span></span>

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

<span data-ttu-id="fbc28-123">El índice de cada elemento refuerza el concepto de "desde el inicio" y "desde el final", y que los rangos son exclusivos del final del rango.</span><span class="sxs-lookup"><span data-stu-id="fbc28-123">The index of each element reinforces the concept of "from the start", and "from the end", and that ranges are exclusive of the end of the range.</span></span> <span data-ttu-id="fbc28-124">El "inicio" de toda la matriz es el primer elemento.</span><span class="sxs-lookup"><span data-stu-id="fbc28-124">The "start" of the entire array is the first element.</span></span> <span data-ttu-id="fbc28-125">El "final" de toda la matriz es *pasado* el último elemento.</span><span class="sxs-lookup"><span data-stu-id="fbc28-125">The "end" of the entire array is *past* the last element.</span></span>

<span data-ttu-id="fbc28-126">Puede recuperar la última palabra con el índice `^1`.</span><span class="sxs-lookup"><span data-stu-id="fbc28-126">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="fbc28-127">Agregue el código siguiente a la inicialización:</span><span class="sxs-lookup"><span data-stu-id="fbc28-127">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="fbc28-128">El siguiente código crea un subrango con las palabras "quick", "brown" y "fox".</span><span class="sxs-lookup"><span data-stu-id="fbc28-128">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="fbc28-129">Va de `words[1]` a `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="fbc28-129">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="fbc28-130">El elemento `words[4]` no se encuentra en el intervalo.</span><span class="sxs-lookup"><span data-stu-id="fbc28-130">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="fbc28-131">Agregue el código siguiente al mismo método.</span><span class="sxs-lookup"><span data-stu-id="fbc28-131">Add the following code to the same method.</span></span> <span data-ttu-id="fbc28-132">Cópielo y péguelo en la parte inferior de la ventana interactiva.</span><span class="sxs-lookup"><span data-stu-id="fbc28-132">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="fbc28-133">El siguiente código crea un subrango con "lazy" y "dog".</span><span class="sxs-lookup"><span data-stu-id="fbc28-133">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="fbc28-134">Incluye `words[^2]` y `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="fbc28-134">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="fbc28-135">El índice del final `words[^0]` no se incluye.</span><span class="sxs-lookup"><span data-stu-id="fbc28-135">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="fbc28-136">Agregue el código siguiente también:</span><span class="sxs-lookup"><span data-stu-id="fbc28-136">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="fbc28-137">En los ejemplos siguientes se crean rangos con final abierto para el inicio, el final o ambos:</span><span class="sxs-lookup"><span data-stu-id="fbc28-137">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="fbc28-138">También puede declarar rangos o índices como variables.</span><span class="sxs-lookup"><span data-stu-id="fbc28-138">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="fbc28-139">La variable se puede usar luego dentro de los caracteres `[` y `]`:</span><span class="sxs-lookup"><span data-stu-id="fbc28-139">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="fbc28-140">Los ejemplos anteriores muestran dos decisiones de diseño que requieren mayor explicación:</span><span class="sxs-lookup"><span data-stu-id="fbc28-140">The previous examples show two design decisions that require more explanation:</span></span>

- <span data-ttu-id="fbc28-141">Los intervalos son *exclusivos*, lo que significa que el elemento en el último índice no está en el intervalo.</span><span class="sxs-lookup"><span data-stu-id="fbc28-141">Ranges are *exclusive*, meaning the element at the last index isn't in the range.</span></span>
- <span data-ttu-id="fbc28-142">El índice `^0` es *el final* de la colección, no *el último elemento* en la colección.</span><span class="sxs-lookup"><span data-stu-id="fbc28-142">The index `^0` is *the end* of the collection, not *the last element* in the collection.</span></span>

<span data-ttu-id="fbc28-143">El ejemplo siguiente muestra muchos de los motivos para esas opciones.</span><span class="sxs-lookup"><span data-stu-id="fbc28-143">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="fbc28-144">Modifique `x`, `y` y `z` para probar diferentes combinaciones.</span><span class="sxs-lookup"><span data-stu-id="fbc28-144">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="fbc28-145">Al experimentar, use valores donde `x` sea menor que `y` y `y` sea menor que `z` para las combinaciones válidas.</span><span class="sxs-lookup"><span data-stu-id="fbc28-145">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="fbc28-146">Agregue el código siguiente a un nuevo método.</span><span class="sxs-lookup"><span data-stu-id="fbc28-146">Add the following code in a new method.</span></span> <span data-ttu-id="fbc28-147">Pruebe diferentes combinaciones:</span><span class="sxs-lookup"><span data-stu-id="fbc28-147">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="fbc28-148">Escenarios para los índices y los rangos</span><span class="sxs-lookup"><span data-stu-id="fbc28-148">Scenarios for Indices and Ranges</span></span>

<span data-ttu-id="fbc28-149">A menudo usará rangos e índices cuando desee realizar un poco de análisis en el subrango de una secuencia completa.</span><span class="sxs-lookup"><span data-stu-id="fbc28-149">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="fbc28-150">La nueva sintaxis es más clara al leer exactamente lo que implica el subrango.</span><span class="sxs-lookup"><span data-stu-id="fbc28-150">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="fbc28-151">La función local `MovingAverage` toma un <xref:System.Range> como su argumento.</span><span class="sxs-lookup"><span data-stu-id="fbc28-151">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="fbc28-152">El método enumera solo ese rango al calcular el mínimo, el máximo y la media.</span><span class="sxs-lookup"><span data-stu-id="fbc28-152">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="fbc28-153">Pruebe con el código siguiente en su proyecto:</span><span class="sxs-lookup"><span data-stu-id="fbc28-153">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="fbc28-154">Puede descargar el código completado del repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes).</span><span class="sxs-lookup"><span data-stu-id="fbc28-154">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
