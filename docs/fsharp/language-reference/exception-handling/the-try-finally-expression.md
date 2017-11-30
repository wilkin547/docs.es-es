---
title: "Excepciones: la expresión try...finally (F#)"
description: "Obtenga información acerca de cómo la F # ' try... finally' expresión le permite ejecutar código de limpieza aunque un bloque de código produce una excepción."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: af06b20c-8d87-4496-a0aa-6fdfe8b3a786
ms.openlocfilehash: 2e2445c42bf8129ea81beef56cb725ac0e37d202
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="4c7e1-104">Excepciones: expresión try...finally</span><span class="sxs-lookup"><span data-stu-id="4c7e1-104">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="4c7e1-105">El `try...finally` expresión le permite ejecutar código de limpieza aunque un bloque de código produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="4c7e1-105">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>


## <a name="syntax"></a><span data-ttu-id="4c7e1-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c7e1-106">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="4c7e1-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4c7e1-107">Remarks</span></span>
<span data-ttu-id="4c7e1-108">El `try...finally` expresión puede utilizarse para ejecutar el código en *expression2* en la sintaxis anterior, independientemente de si se genera una excepción durante la ejecución de *expression1*.</span><span class="sxs-lookup"><span data-stu-id="4c7e1-108">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="4c7e1-109">El tipo de *expression2* no contribuyen al valor de la expresión completa; el tipo devuelto cuando no se produce una excepción es el último valor en *expression1*.</span><span class="sxs-lookup"><span data-stu-id="4c7e1-109">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="4c7e1-110">Cuando se produce una excepción, se devuelve ningún valor y el flujo de control se transfiere al siguiente controlador de excepción coincidente por la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="4c7e1-110">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="4c7e1-111">Si no se encuentra ningún controlador de excepción, el programa se cierra.</span><span class="sxs-lookup"><span data-stu-id="4c7e1-111">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="4c7e1-112">Antes de que se ejecuta el código en un controlador coincidente o el programa finaliza, el código en el `finally` se ejecuta la bifurcación.</span><span class="sxs-lookup"><span data-stu-id="4c7e1-112">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="4c7e1-113">El código siguiente muestra el uso de la `try...finally` expresión.</span><span class="sxs-lookup"><span data-stu-id="4c7e1-113">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="4c7e1-114">La salida en la consola es como sigue.</span><span class="sxs-lookup"><span data-stu-id="4c7e1-114">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="4c7e1-115">Como puede ver desde la salida, la secuencia se cerró antes de que se controló la excepción exterior y el archivo `test.txt` contiene el texto `test1`, lo que indica que los búferes se vacían y escritos en el disco, aunque se transfiere de la excepción el control a controlador de excepciones exterior.</span><span class="sxs-lookup"><span data-stu-id="4c7e1-115">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="4c7e1-116">Tenga en cuenta que la `try...with` es una construcción independiente de la `try...finally` construir.</span><span class="sxs-lookup"><span data-stu-id="4c7e1-116">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="4c7e1-117">Por lo tanto, si el código requiere tanto un `with` bloque y un `finally` bloque, se deben anidar las dos construcciones, como en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="4c7e1-117">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="4c7e1-118">En el contexto de las expresiones de cálculo, incluyendo expresiones de secuencia y flujos de trabajo asincrónicos, **try... finally** las expresiones pueden tener una implementación personalizada.</span><span class="sxs-lookup"><span data-stu-id="4c7e1-118">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="4c7e1-119">Para obtener más información, consulte [expresiones de cálculo](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4c7e1-119">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="4c7e1-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c7e1-120">See Also</span></span>
[<span data-ttu-id="4c7e1-121">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="4c7e1-121">Exception Handling</span></span>](index.md)

<span data-ttu-id="4c7e1-122">[Exceptions: The `try...with` Expression](the-try-with-expression.md) (Excepciones: la expresión `try...with`)</span><span class="sxs-lookup"><span data-stu-id="4c7e1-122">[Exceptions: The `try...with` Expression](the-try-with-expression.md)</span></span>
