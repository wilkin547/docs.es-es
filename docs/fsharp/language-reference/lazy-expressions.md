---
title: Expresiones diferidas
description: Obtenga información sobre cómo F# expresiones diferidas pueden mejorar el rendimiento de las aplicaciones y bibliotecas.
ms.date: 03/13/2019
ms.openlocfilehash: 6d53d53093f4e93f53e1c956b94e2f1e4a1bbd55
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2019
ms.locfileid: "57853333"
---
# <a name="lazy-expressions"></a><span data-ttu-id="9aced-103">Expresiones diferidas</span><span class="sxs-lookup"><span data-stu-id="9aced-103">Lazy Expressions</span></span>

<span data-ttu-id="9aced-104">*Expresiones diferidas* son expresiones que no se evaluarán inmediatamente, pero en su lugar se evalúan cuando se necesita el resultado.</span><span class="sxs-lookup"><span data-stu-id="9aced-104">*Lazy expressions* are expressions that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="9aced-105">Esto puede ayudar a mejorar el rendimiento del código.</span><span class="sxs-lookup"><span data-stu-id="9aced-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="9aced-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9aced-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="9aced-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9aced-107">Remarks</span></span>

<span data-ttu-id="9aced-108">En la sintaxis anterior, *expresión* es código que se evalúa solo cuando es necesario, un resultado y *identificador* es un valor que almacena el resultado.</span><span class="sxs-lookup"><span data-stu-id="9aced-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="9aced-109">El valor es de tipo [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), donde el tipo real que se usa para `'T` se determina a partir del resultado de la expresión.</span><span class="sxs-lookup"><span data-stu-id="9aced-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="9aced-110">Las expresiones diferidas permiten mejorar el rendimiento mediante la restricción de la ejecución de una expresión a sólo aquellas situaciones en que se necesita un resultado.</span><span class="sxs-lookup"><span data-stu-id="9aced-110">Lazy expressions enable you to improve performance by restricting the execution of an expressions to only those situations in which a result is needed.</span></span>

<span data-ttu-id="9aced-111">Para forzar las expresiones que se va a realizarse, se llama al método `Force`.</span><span class="sxs-lookup"><span data-stu-id="9aced-111">To force the expressions to be performed, you call the method `Force`.</span></span> <span data-ttu-id="9aced-112">`Force` hace que la ejecución se realiza solo una vez.</span><span class="sxs-lookup"><span data-stu-id="9aced-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="9aced-113">Las llamadas subsiguientes a `Force` devuelven el mismo resultado, pero no ejecute ningún código.</span><span class="sxs-lookup"><span data-stu-id="9aced-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="9aced-114">El código siguiente ilustra el uso de expresiones diferidas y el uso de `Force`.</span><span class="sxs-lookup"><span data-stu-id="9aced-114">The following code illustrates the use of lazy expressions and the use of `Force`.</span></span> <span data-ttu-id="9aced-115">En este código, el tipo de `result` es `Lazy<int>`y el `Force` método devuelve un `int`.</span><span class="sxs-lookup"><span data-stu-id="9aced-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="9aced-116">La evaluación diferida, pero no la `Lazy` escriba, también se usa para las secuencias.</span><span class="sxs-lookup"><span data-stu-id="9aced-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="9aced-117">Para obtener más información, consulte [secuencias](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="9aced-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9aced-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9aced-118">See also</span></span>

- [<span data-ttu-id="9aced-119">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="9aced-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="9aced-120">LazyExtensions (módulo)</span><span class="sxs-lookup"><span data-stu-id="9aced-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
