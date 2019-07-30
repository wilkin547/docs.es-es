---
title: 'Bucles: expresión for...in'
description: Vea cómo F# ... en, la construcción de bucle de expresión se usa para iterar por las coincidencias de un patrón en una colección Enumerable.
ms.date: 05/16/2016
ms.openlocfilehash: 640b0f91f6c641f3b49a99dc67abe7e4c31911ea
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630717"
---
# <a name="loops-forin-expression"></a><span data-ttu-id="735c5-103">Bucles: expresión for...in</span><span class="sxs-lookup"><span data-stu-id="735c5-103">Loops: for...in Expression</span></span>

<span data-ttu-id="735c5-104">Esta construcción de bucle se usa para iterar por las coincidencias de un patrón en una colección Enumerable como una expresión de intervalo, una secuencia, una lista, una matriz u otra construcción que admita la enumeración.</span><span class="sxs-lookup"><span data-stu-id="735c5-104">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>

## <a name="syntax"></a><span data-ttu-id="735c5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="735c5-105">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="735c5-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="735c5-106">Remarks</span></span>

<span data-ttu-id="735c5-107">La `for...in` expresión se puede comparar con la `for each` instrucción en otros lenguajes .net porque se usa para recorrer los valores de una colección Enumerable.</span><span class="sxs-lookup"><span data-stu-id="735c5-107">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="735c5-108">Sin embargo `for...in` , también admite la coincidencia de patrones en la colección en lugar de simplemente la iteración en toda la colección.</span><span class="sxs-lookup"><span data-stu-id="735c5-108">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="735c5-109">La expresión Enumerable se puede especificar como una colección Enumerable o, mediante `..` el operador, como un intervalo en un tipo entero.</span><span class="sxs-lookup"><span data-stu-id="735c5-109">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="735c5-110">Las colecciones enumerables incluyen listas, secuencias, matrices, conjuntos, asignaciones, etc.</span><span class="sxs-lookup"><span data-stu-id="735c5-110">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="735c5-111">Se `System.Collections.IEnumerable` puede usar cualquier tipo que implemente.</span><span class="sxs-lookup"><span data-stu-id="735c5-111">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="735c5-112">Al expresar un intervalo mediante el `..` operador, puede usar la sintaxis siguiente.</span><span class="sxs-lookup"><span data-stu-id="735c5-112">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="735c5-113">*iniciar* ..</span><span class="sxs-lookup"><span data-stu-id="735c5-113">*start* ..</span></span> <span data-ttu-id="735c5-114">*finish*</span><span class="sxs-lookup"><span data-stu-id="735c5-114">*finish*</span></span>

<span data-ttu-id="735c5-115">También puede usar una versión que incluya un incremento denominado *SKIP*, como en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="735c5-115">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="735c5-116">*iniciar* ..</span><span class="sxs-lookup"><span data-stu-id="735c5-116">*start* ..</span></span> <span data-ttu-id="735c5-117">*omitir* ...</span><span class="sxs-lookup"><span data-stu-id="735c5-117">*skip* ..</span></span> <span data-ttu-id="735c5-118">*finish*</span><span class="sxs-lookup"><span data-stu-id="735c5-118">*finish*</span></span>

<span data-ttu-id="735c5-119">Cuando se usan intervalos enteros y una variable de contador simple como patrón, el comportamiento típico es incrementar la variable de contador en 1 en cada iteración, pero si el intervalo incluye un valor de omisión, el contador se incrementa en su lugar por el valor de omisión.</span><span class="sxs-lookup"><span data-stu-id="735c5-119">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="735c5-120">Los valores coincidentes en el patrón también se pueden utilizar en la expresión del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="735c5-120">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="735c5-121">En los siguientes ejemplos de código se muestra el `for...in` uso de la expresión.</span><span class="sxs-lookup"><span data-stu-id="735c5-121">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="735c5-122">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="735c5-122">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="735c5-123">En el ejemplo siguiente se muestra cómo crear un bucle sobre una secuencia y cómo usar un patrón de tupla en lugar de una variable simple.</span><span class="sxs-lookup"><span data-stu-id="735c5-123">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="735c5-124">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="735c5-124">The output is as follows.</span></span>

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

<span data-ttu-id="735c5-125">En el ejemplo siguiente se muestra cómo recorrer un intervalo entero simple.</span><span class="sxs-lookup"><span data-stu-id="735c5-125">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="735c5-126">La salida de function1 es como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="735c5-126">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="735c5-127">En el ejemplo siguiente se muestra cómo recorrer en bucle un intervalo con un salto de 2, que incluye todos los demás elementos del intervalo.</span><span class="sxs-lookup"><span data-stu-id="735c5-127">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="735c5-128">La salida de `function2` es como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="735c5-128">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="735c5-129">En el ejemplo siguiente se muestra cómo usar un intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="735c5-129">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="735c5-130">La salida de `function3` es como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="735c5-130">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="735c5-131">En el ejemplo siguiente se muestra cómo usar un valor de SKIP negativo para una iteración inversa.</span><span class="sxs-lookup"><span data-stu-id="735c5-131">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="735c5-132">La salida de `function4` es como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="735c5-132">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="735c5-133">El principio y el final del intervalo también pueden ser expresiones, como las funciones, como en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="735c5-133">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="735c5-134">La salida de `function5` con esta entrada es como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="735c5-134">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="735c5-135">En el ejemplo siguiente se muestra el uso de un carácter\_comodín () cuando el elemento no es necesario en el bucle.</span><span class="sxs-lookup"><span data-stu-id="735c5-135">The next example shows the use of a wildcard character (\_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="735c5-136">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="735c5-136">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="735c5-137">`Note`Puede usar `for...in` en expresiones de secuencia y otras expresiones de cálculo, en cuyo caso se utiliza una versión personalizada `for...in` de la expresión.</span><span class="sxs-lookup"><span data-stu-id="735c5-137">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="735c5-138">Para obtener más información, vea [secuencias](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md)y expresiones de [cálculo](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="735c5-138">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="735c5-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="735c5-139">See also</span></span>

- [<span data-ttu-id="735c5-140">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="735c5-140">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="735c5-141">Bucles `for...to`Expresiones</span><span class="sxs-lookup"><span data-stu-id="735c5-141">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
- [<span data-ttu-id="735c5-142">Bucles `while...do`Expresiones</span><span class="sxs-lookup"><span data-stu-id="735c5-142">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
