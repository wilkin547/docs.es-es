---
title: 'Excepciones: la expresión try...finally (F#)'
description: "Obtenga información acerca de cómo la F # ' try... finally' expresión le permite ejecutar código de limpieza aunque un bloque de código produce una excepción."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 588e4edb4d25c6d25ef103ba724613db997f68d7
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="3d5eb-103">Excepciones: expresión try...finally</span><span class="sxs-lookup"><span data-stu-id="3d5eb-103">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="3d5eb-104">El `try...finally` expresión le permite ejecutar código de limpieza aunque un bloque de código produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="3d5eb-104">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>


## <a name="syntax"></a><span data-ttu-id="3d5eb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d5eb-105">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="3d5eb-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3d5eb-106">Remarks</span></span>
<span data-ttu-id="3d5eb-107">El `try...finally` expresión puede utilizarse para ejecutar el código en *expression2* en la sintaxis anterior, independientemente de si se genera una excepción durante la ejecución de *expression1*.</span><span class="sxs-lookup"><span data-stu-id="3d5eb-107">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="3d5eb-108">El tipo de *expression2* no contribuyen al valor de la expresión completa; el tipo devuelto cuando no se produce una excepción es el último valor en *expression1*.</span><span class="sxs-lookup"><span data-stu-id="3d5eb-108">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="3d5eb-109">Cuando se produce una excepción, se devuelve ningún valor y el flujo de control se transfiere al siguiente controlador de excepción coincidente por la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3d5eb-109">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="3d5eb-110">Si no se encuentra ningún controlador de excepción, el programa se cierra.</span><span class="sxs-lookup"><span data-stu-id="3d5eb-110">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="3d5eb-111">Antes de que se ejecuta el código en un controlador coincidente o el programa finaliza, el código en el `finally` se ejecuta la bifurcación.</span><span class="sxs-lookup"><span data-stu-id="3d5eb-111">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="3d5eb-112">El código siguiente muestra el uso de la `try...finally` expresión.</span><span class="sxs-lookup"><span data-stu-id="3d5eb-112">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="3d5eb-113">La salida en la consola es como sigue.</span><span class="sxs-lookup"><span data-stu-id="3d5eb-113">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="3d5eb-114">Como puede ver desde la salida, la secuencia se cerró antes de que se controló la excepción exterior y el archivo `test.txt` contiene el texto `test1`, lo que indica que los búferes se vacían y escritos en el disco, aunque se transfiere de la excepción el control a controlador de excepciones exterior.</span><span class="sxs-lookup"><span data-stu-id="3d5eb-114">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="3d5eb-115">Tenga en cuenta que la `try...with` es una construcción independiente de la `try...finally` construir.</span><span class="sxs-lookup"><span data-stu-id="3d5eb-115">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="3d5eb-116">Por lo tanto, si el código requiere tanto un `with` bloque y un `finally` bloque, se deben anidar las dos construcciones, como en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3d5eb-116">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="3d5eb-117">En el contexto de las expresiones de cálculo, incluyendo expresiones de secuencia y flujos de trabajo asincrónicos, **try... finally** las expresiones pueden tener una implementación personalizada.</span><span class="sxs-lookup"><span data-stu-id="3d5eb-117">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="3d5eb-118">Para obtener más información, consulte [expresiones de cálculo](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3d5eb-118">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="3d5eb-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d5eb-119">See Also</span></span>
[<span data-ttu-id="3d5eb-120">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="3d5eb-120">Exception Handling</span></span>](index.md)

<span data-ttu-id="3d5eb-121">[Exceptions: The `try...with` Expression](the-try-with-expression.md) (Excepciones: la expresión `try...with`)</span><span class="sxs-lookup"><span data-stu-id="3d5eb-121">[Exceptions: The `try...with` Expression](the-try-with-expression.md)</span></span>
