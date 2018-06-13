---
title: Expresiones con procesamiento diferido (F#)
description: 'Obtenga información acerca de cómo F # con procesamiento diferido puede mejorar el rendimiento de sus aplicaciones y bibliotecas.'
ms.date: 05/16/2016
ms.openlocfilehash: 1c4eb6ab247c44a04a9d145185e2de7ec01b8e0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563937"
---
# <a name="lazy-computations"></a><span data-ttu-id="1e335-103">Expresiones con procesamiento diferido</span><span class="sxs-lookup"><span data-stu-id="1e335-103">Lazy Computations</span></span>

<span data-ttu-id="1e335-104">*Expresiones con procesamiento diferidas* son cálculos que no se evalúan inmediatamente, pero en su lugar se evalúan cuando se necesita el resultado.</span><span class="sxs-lookup"><span data-stu-id="1e335-104">*Lazy computations* are computations that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="1e335-105">Esto puede ayudar a mejorar el rendimiento del código.</span><span class="sxs-lookup"><span data-stu-id="1e335-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="1e335-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e335-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="1e335-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1e335-107">Remarks</span></span>

<span data-ttu-id="1e335-108">En la sintaxis anterior, *expresión* es código que se evalúa solo cuando sea necesario, un resultado y *identificador* es un valor que almacena el resultado.</span><span class="sxs-lookup"><span data-stu-id="1e335-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="1e335-109">El valor es de tipo [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), donde el tipo real que se utiliza para `'T` se determina a partir del resultado de la expresión.</span><span class="sxs-lookup"><span data-stu-id="1e335-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="1e335-110">Expresiones con procesamiento diferidas permiten mejorar el rendimiento mediante la restricción de la ejecución de un cálculo a solo aquellas situaciones en que se necesita un resultado.</span><span class="sxs-lookup"><span data-stu-id="1e335-110">Lazy computations enable you to improve performance by restricting the execution of a computation to only those situations in which a result is needed.</span></span>

<span data-ttu-id="1e335-111">Para forzar el cálculo que se realice, llame al método `Force`.</span><span class="sxs-lookup"><span data-stu-id="1e335-111">To force the computation to be performed, you call the method `Force`.</span></span> <span data-ttu-id="1e335-112">`Force` hace que la ejecución realizar solo una vez.</span><span class="sxs-lookup"><span data-stu-id="1e335-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="1e335-113">Las llamadas subsiguientes a `Force` devuelven el mismo resultado, pero no ejecute ningún código.</span><span class="sxs-lookup"><span data-stu-id="1e335-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="1e335-114">El código siguiente muestra el uso de expresiones con procesamiento diferido y el uso de `Force`.</span><span class="sxs-lookup"><span data-stu-id="1e335-114">The following code illustrates the use of lazy computation and the use of `Force`.</span></span> <span data-ttu-id="1e335-115">En este código, el tipo de `result` es `Lazy<int>`y el `Force` método devuelve un `int`.</span><span class="sxs-lookup"><span data-stu-id="1e335-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="1e335-116">La evaluación diferida, pero no el `Lazy` escriba, también se utiliza para las secuencias.</span><span class="sxs-lookup"><span data-stu-id="1e335-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="1e335-117">Para obtener más información, consulte [secuencias](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="1e335-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1e335-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e335-118">See Also</span></span>

[<span data-ttu-id="1e335-119">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="1e335-119">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="1e335-120">LazyExtensions (módulo)</span><span class="sxs-lookup"><span data-stu-id="1e335-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
