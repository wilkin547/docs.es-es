---
title: Expresiones diferidas
description: 'Obtenga información sobre cómo las expresiones de F # Lazy pueden mejorar el rendimiento de las aplicaciones y las bibliotecas.'
ms.date: 08/15/2020
ms.openlocfilehash: 0b8496467295ce6793f80c341af88bb1819f4a47
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100425508"
---
# <a name="lazy-expressions"></a><span data-ttu-id="73f70-103">Expresiones diferidas</span><span class="sxs-lookup"><span data-stu-id="73f70-103">Lazy Expressions</span></span>

<span data-ttu-id="73f70-104">Las *expresiones diferidas* son expresiones que no se evalúan inmediatamente, pero se evalúan en su lugar cuando se necesita el resultado.</span><span class="sxs-lookup"><span data-stu-id="73f70-104">*Lazy expressions* are expressions that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="73f70-105">Esto puede ayudar a mejorar el rendimiento del código.</span><span class="sxs-lookup"><span data-stu-id="73f70-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="73f70-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73f70-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="73f70-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="73f70-107">Remarks</span></span>

<span data-ttu-id="73f70-108">En la sintaxis anterior, *Expression* es un código que solo se evalúa cuando se requiere un resultado y *Identifier* es un valor que almacena el resultado.</span><span class="sxs-lookup"><span data-stu-id="73f70-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="73f70-109">El valor es de tipo `Lazy<'T>` , donde el tipo real que se utiliza para `'T` se determina a partir del resultado de la expresión.</span><span class="sxs-lookup"><span data-stu-id="73f70-109">The value is of type `Lazy<'T>`, where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="73f70-110">Las expresiones diferidas permiten mejorar el rendimiento mediante la restricción de la ejecución de una expresión a solo aquellas situaciones en las que se necesita un resultado.</span><span class="sxs-lookup"><span data-stu-id="73f70-110">Lazy expressions enable you to improve performance by restricting the execution of an expressions to only those situations in which a result is needed.</span></span>

<span data-ttu-id="73f70-111">Para forzar que se realicen las expresiones, llame al método `Force` .</span><span class="sxs-lookup"><span data-stu-id="73f70-111">To force the expressions to be performed, you call the method `Force`.</span></span> <span data-ttu-id="73f70-112">`Force` hace que la ejecución se realice solo una vez.</span><span class="sxs-lookup"><span data-stu-id="73f70-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="73f70-113">Las siguientes llamadas a `Force` devuelven el mismo resultado, pero no ejecutan ningún código.</span><span class="sxs-lookup"><span data-stu-id="73f70-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="73f70-114">En el código siguiente se muestra el uso de expresiones diferidas y el uso de `Force` .</span><span class="sxs-lookup"><span data-stu-id="73f70-114">The following code illustrates the use of lazy expressions and the use of `Force`.</span></span> <span data-ttu-id="73f70-115">En este código, el tipo de `result` es `Lazy<int>` y el `Force` método devuelve un `int` .</span><span class="sxs-lookup"><span data-stu-id="73f70-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="73f70-116">La evaluación diferida, pero no el `Lazy` tipo, también se usa para las secuencias.</span><span class="sxs-lookup"><span data-stu-id="73f70-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="73f70-117">Para obtener más información, vea [secuencias](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="73f70-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="73f70-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="73f70-118">See also</span></span>

- [<span data-ttu-id="73f70-119">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="73f70-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="73f70-120">Módulo LazyExtensions</span><span class="sxs-lookup"><span data-stu-id="73f70-120">LazyExtensions module</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-lazyextensions.html)
