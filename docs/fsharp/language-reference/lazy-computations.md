---
title: Expresiones con procesamiento diferido (F#)
description: 'Obtenga información sobre cómo F # con procesamiento diferido puede mejorar el rendimiento de las aplicaciones y bibliotecas.'
ms.date: 05/16/2016
ms.openlocfilehash: 8afe815f26978de96291a52973d54a9dbcc5eaf2
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45698215"
---
# <a name="lazy-computations"></a><span data-ttu-id="16f8b-103">Expresiones con procesamiento diferido</span><span class="sxs-lookup"><span data-stu-id="16f8b-103">Lazy Computations</span></span>

<span data-ttu-id="16f8b-104">*Expresiones con procesamiento diferidas* son cálculos que no se evaluarán inmediatamente, pero en su lugar se evalúan cuando se necesita el resultado.</span><span class="sxs-lookup"><span data-stu-id="16f8b-104">*Lazy computations* are computations that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="16f8b-105">Esto puede ayudar a mejorar el rendimiento del código.</span><span class="sxs-lookup"><span data-stu-id="16f8b-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="16f8b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16f8b-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="16f8b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="16f8b-107">Remarks</span></span>

<span data-ttu-id="16f8b-108">En la sintaxis anterior, *expresión* es código que se evalúa solo cuando es necesario, un resultado y *identificador* es un valor que almacena el resultado.</span><span class="sxs-lookup"><span data-stu-id="16f8b-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="16f8b-109">El valor es de tipo [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), donde el tipo real que se usa para `'T` se determina a partir del resultado de la expresión.</span><span class="sxs-lookup"><span data-stu-id="16f8b-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="16f8b-110">Expresiones con procesamiento diferidas permiten mejorar el rendimiento mediante la restricción de la ejecución de un cálculo a sólo aquellas situaciones en que se necesita un resultado.</span><span class="sxs-lookup"><span data-stu-id="16f8b-110">Lazy computations enable you to improve performance by restricting the execution of a computation to only those situations in which a result is needed.</span></span>

<span data-ttu-id="16f8b-111">Para forzar que se puede realizar el cálculo, se llama al método `Force`.</span><span class="sxs-lookup"><span data-stu-id="16f8b-111">To force the computation to be performed, you call the method `Force`.</span></span> <span data-ttu-id="16f8b-112">`Force` hace que la ejecución se realiza solo una vez.</span><span class="sxs-lookup"><span data-stu-id="16f8b-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="16f8b-113">Las llamadas subsiguientes a `Force` devuelven el mismo resultado, pero no ejecute ningún código.</span><span class="sxs-lookup"><span data-stu-id="16f8b-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="16f8b-114">El código siguiente ilustra el uso de la expresión con procesamiento diferido y el uso de `Force`.</span><span class="sxs-lookup"><span data-stu-id="16f8b-114">The following code illustrates the use of lazy computation and the use of `Force`.</span></span> <span data-ttu-id="16f8b-115">En este código, el tipo de `result` es `Lazy<int>`y el `Force` método devuelve un `int`.</span><span class="sxs-lookup"><span data-stu-id="16f8b-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="16f8b-116">La evaluación diferida, pero no la `Lazy` escriba, también se usa para las secuencias.</span><span class="sxs-lookup"><span data-stu-id="16f8b-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="16f8b-117">Para obtener más información, consulte [secuencias](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="16f8b-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="16f8b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="16f8b-118">See also</span></span>

- [<span data-ttu-id="16f8b-119">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="16f8b-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="16f8b-120">LazyExtensions (módulo)</span><span class="sxs-lookup"><span data-stu-id="16f8b-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
