---
title: "Bucles: expresión for...in (F#)"
description: "Vea cómo la estructura de F # for.. en expresión la construcción de bucle se utiliza para recorrer en iteración las coincidencias de un patrón en una colección enumerable."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f54e3228-4aec-4d0a-ae37-bc3376508284
ms.openlocfilehash: d86aeb3bdd975261e59004d636354a740bd95c47
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="loops-forin-expression"></a><span data-ttu-id="39ebb-104">Bucles: expresión for...in</span><span class="sxs-lookup"><span data-stu-id="39ebb-104">Loops: for...in Expression</span></span>

<span data-ttu-id="39ebb-105">Esta construcción de bucle se utiliza para recorrer en iteración las coincidencias de un patrón en una colección enumerable como una expresión de intervalo, secuencia, lista, matriz u otra construcción que admita la enumeración.</span><span class="sxs-lookup"><span data-stu-id="39ebb-105">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>


## <a name="syntax"></a><span data-ttu-id="39ebb-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39ebb-106">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="39ebb-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="39ebb-107">Remarks</span></span>
<span data-ttu-id="39ebb-108">El `for...in` expresión se puede comparar con la `for each` instrucción en otros lenguajes .NET porque se usa para iterar por los valores de una colección enumerable.</span><span class="sxs-lookup"><span data-stu-id="39ebb-108">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="39ebb-109">Sin embargo, `for...in` también admite el patrón de coincidencia en la colección en lugar de solo la iteración a través de toda la colección.</span><span class="sxs-lookup"><span data-stu-id="39ebb-109">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="39ebb-110">La expresión enumerable puede especificarse como una colección enumerable o, mediante el `..` operador, como un intervalo en un tipo entero.</span><span class="sxs-lookup"><span data-stu-id="39ebb-110">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="39ebb-111">Las colecciones enumerables incluyen listas, secuencias, matrices, conjuntos, asignaciones y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="39ebb-111">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="39ebb-112">Cualquier tipo que implemente `System.Collections.IEnumerable` puede utilizarse.</span><span class="sxs-lookup"><span data-stu-id="39ebb-112">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="39ebb-113">Al expresar un intervalo mediante el `..` operador, puede utilizar la siguiente sintaxis.</span><span class="sxs-lookup"><span data-stu-id="39ebb-113">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="39ebb-114">*iniciar* ...</span><span class="sxs-lookup"><span data-stu-id="39ebb-114">*start* ..</span></span> <span data-ttu-id="39ebb-115">*Finalizar*</span><span class="sxs-lookup"><span data-stu-id="39ebb-115">*finish*</span></span>

<span data-ttu-id="39ebb-116">También puede usar una versión que incluye un incremento denominado el *omitir*, como en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="39ebb-116">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="39ebb-117">*iniciar* ...</span><span class="sxs-lookup"><span data-stu-id="39ebb-117">*start* ..</span></span> <span data-ttu-id="39ebb-118">*omitir* ...</span><span class="sxs-lookup"><span data-stu-id="39ebb-118">*skip* ..</span></span> <span data-ttu-id="39ebb-119">*Finalizar*</span><span class="sxs-lookup"><span data-stu-id="39ebb-119">*finish*</span></span>

<span data-ttu-id="39ebb-120">Cuando utiliza intervalos de enteros y una variable de contador simple como un patrón, el comportamiento típico es incrementar la variable de contador en 1 en cada iteración, pero si el intervalo incluye un valor de salto, el contador se incrementa en el valor de omisión en su lugar.</span><span class="sxs-lookup"><span data-stu-id="39ebb-120">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="39ebb-121">Los valores coincidentes en el modelo también pueden utilizarse en la expresión del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="39ebb-121">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="39ebb-122">Ejemplos de código siguientes muestran el uso de la `for...in` expresión.</span><span class="sxs-lookup"><span data-stu-id="39ebb-122">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="39ebb-123">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="39ebb-123">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="39ebb-124">En el ejemplo siguiente se muestra cómo crear bucles a través de una secuencia y cómo utilizar un tupla (modelo) en lugar de una variable simple.</span><span class="sxs-lookup"><span data-stu-id="39ebb-124">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="39ebb-125">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="39ebb-125">The output is as follows.</span></span>

```
1 squared is 1
2 squared is 4
3 squared is 9
4 squared is 16
5 squared is 25
6 squared is 36
7 squared is 49
8 squared is 64
9 squared is 81
10 squared is 100
```

<span data-ttu-id="39ebb-126">En el ejemplo siguiente se muestra cómo recorrer en iteración un intervalo de enteros simple.</span><span class="sxs-lookup"><span data-stu-id="39ebb-126">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="39ebb-127">La salida de function1 es como sigue.</span><span class="sxs-lookup"><span data-stu-id="39ebb-127">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="39ebb-128">En el ejemplo siguiente se muestra cómo recorrer en iteración un intervalo con un salto de 2, que incluye todos los elementos del intervalo.</span><span class="sxs-lookup"><span data-stu-id="39ebb-128">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="39ebb-129">La salida de `function2` es como sigue.</span><span class="sxs-lookup"><span data-stu-id="39ebb-129">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="39ebb-130">En el ejemplo siguiente se muestra cómo usar un intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="39ebb-130">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="39ebb-131">La salida de `function3` es como sigue.</span><span class="sxs-lookup"><span data-stu-id="39ebb-131">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="39ebb-132">En el ejemplo siguiente se muestra cómo usar un valor negativo skip para una iteración inversa.</span><span class="sxs-lookup"><span data-stu-id="39ebb-132">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="39ebb-133">La salida de `function4` es como sigue.</span><span class="sxs-lookup"><span data-stu-id="39ebb-133">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="39ebb-134">El principio y el final del intervalo también pueden ser expresiones, como funciones, como en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="39ebb-134">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="39ebb-135">La salida de `function5` con esta entrada es como sigue.</span><span class="sxs-lookup"><span data-stu-id="39ebb-135">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="39ebb-136">En el ejemplo siguiente se muestra el uso de un carácter comodín (_) cuando el elemento no es necesaria en el bucle.</span><span class="sxs-lookup"><span data-stu-id="39ebb-136">The next example shows the use of a wildcard character (_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="39ebb-137">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="39ebb-137">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="39ebb-138">`Note`Puede usar `for...in` en expresiones de secuencia y otras expresiones de cálculo, en cuyo caso una versión personalizada de la `for...in` se utiliza la expresión.</span><span class="sxs-lookup"><span data-stu-id="39ebb-138">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="39ebb-139">Para obtener más información, consulte [secuencias](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md), y [expresiones de cálculo](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="39ebb-139">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="39ebb-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="39ebb-140">See Also</span></span>
[<span data-ttu-id="39ebb-141">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="39ebb-141">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="39ebb-142">Bucles: expresión `for...to`</span><span class="sxs-lookup"><span data-stu-id="39ebb-142">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)

[<span data-ttu-id="39ebb-143">Bucles: expresión `while...do`</span><span class="sxs-lookup"><span data-stu-id="39ebb-143">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
