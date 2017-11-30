---
title: Expresiones con procesamiento diferido (F#)
description: "Obtenga información acerca de cómo F # con procesamiento diferido puede mejorar el rendimiento de sus aplicaciones y bibliotecas."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3499293e-1d53-4b02-b764-f687fbdaa7fe
ms.openlocfilehash: 984c96ab68a8919e2382eefe8260b07f191027dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="lazy-computations"></a><span data-ttu-id="1dc19-104">Expresiones con procesamiento diferido</span><span class="sxs-lookup"><span data-stu-id="1dc19-104">Lazy Computations</span></span>

<span data-ttu-id="1dc19-105">*Expresiones con procesamiento diferidas* son cálculos que no se evalúan inmediatamente, pero en su lugar se evalúan cuando se necesita el resultado.</span><span class="sxs-lookup"><span data-stu-id="1dc19-105">*Lazy computations* are computations that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="1dc19-106">Esto puede ayudar a mejorar el rendimiento del código.</span><span class="sxs-lookup"><span data-stu-id="1dc19-106">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="1dc19-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1dc19-107">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="1dc19-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1dc19-108">Remarks</span></span>

<span data-ttu-id="1dc19-109">En la sintaxis anterior, *expresión* es código que se evalúa solo cuando sea necesario, un resultado y *identificador* es un valor que almacena el resultado.</span><span class="sxs-lookup"><span data-stu-id="1dc19-109">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="1dc19-110">El valor es de tipo [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), donde el tipo real que se utiliza para `'T` se determina a partir del resultado de la expresión.</span><span class="sxs-lookup"><span data-stu-id="1dc19-110">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="1dc19-111">Expresiones con procesamiento diferidas permiten mejorar el rendimiento mediante la restricción de la ejecución de un cálculo a solo aquellas situaciones en que se necesita un resultado.</span><span class="sxs-lookup"><span data-stu-id="1dc19-111">Lazy computations enable you to improve performance by restricting the execution of a computation to only those situations in which a result is needed.</span></span>

<span data-ttu-id="1dc19-112">Para forzar el cálculo que se realice, llame al método `Force`.</span><span class="sxs-lookup"><span data-stu-id="1dc19-112">To force the computation to be performed, you call the method `Force`.</span></span> <span data-ttu-id="1dc19-113">`Force`hace que la ejecución realizar solo una vez.</span><span class="sxs-lookup"><span data-stu-id="1dc19-113">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="1dc19-114">Las llamadas subsiguientes a `Force` devuelven el mismo resultado, pero no ejecute ningún código.</span><span class="sxs-lookup"><span data-stu-id="1dc19-114">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="1dc19-115">El código siguiente muestra el uso de expresiones con procesamiento diferido y el uso de `Force`.</span><span class="sxs-lookup"><span data-stu-id="1dc19-115">The following code illustrates the use of lazy computation and the use of `Force`.</span></span> <span data-ttu-id="1dc19-116">En este código, el tipo de `result` es `Lazy<int>`y el `Force` método devuelve un `int`.</span><span class="sxs-lookup"><span data-stu-id="1dc19-116">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="1dc19-117">La evaluación diferida, pero no el `Lazy` escriba, también se utiliza para las secuencias.</span><span class="sxs-lookup"><span data-stu-id="1dc19-117">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="1dc19-118">Para obtener más información, consulte [secuencias](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="1dc19-118">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1dc19-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1dc19-119">See Also</span></span>

[<span data-ttu-id="1dc19-120">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="1dc19-120">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="1dc19-121">LazyExtensions (módulo)</span><span class="sxs-lookup"><span data-stu-id="1dc19-121">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
