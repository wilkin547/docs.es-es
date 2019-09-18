---
title: 'Excepciones: Expresión try...finally'
description: Obtenga información sobre F# cómo la instrucción "Try... Finalmente, la expresión permite ejecutar código de limpieza incluso si un bloque de código produce una excepción.
ms.date: 05/16/2016
ms.openlocfilehash: 0ddb64ac13b307404864ec5b54f26fd8a7a3d7d8
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083006"
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="7156b-103">Excepciones: Expresión try...finally</span><span class="sxs-lookup"><span data-stu-id="7156b-103">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="7156b-104">La `try...finally` expresión permite ejecutar código de limpieza incluso si un bloque de código produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="7156b-104">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="7156b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7156b-105">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="7156b-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7156b-106">Remarks</span></span>

<span data-ttu-id="7156b-107">La `try...finally` expresión se puede utilizar para ejecutar el código de *expresión2* en la sintaxis anterior, independientemente de si se genera una excepción durante la ejecución de *expression1*.</span><span class="sxs-lookup"><span data-stu-id="7156b-107">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="7156b-108">El tipo de *expresión2* no contribuye al valor de la expresión completa; el tipo devuelto cuando una excepción no se produce es el último valor de *expression1*.</span><span class="sxs-lookup"><span data-stu-id="7156b-108">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="7156b-109">Cuando se produce una excepción, no se devuelve ningún valor y el flujo de control se transfiere al siguiente controlador de excepción coincidente en la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="7156b-109">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="7156b-110">Si no se encuentra ningún controlador de excepciones, el programa finaliza.</span><span class="sxs-lookup"><span data-stu-id="7156b-110">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="7156b-111">Antes de que se ejecute el código de un controlador coincidente o finalice el programa, se ejecuta el `finally` código de la bifurcación.</span><span class="sxs-lookup"><span data-stu-id="7156b-111">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="7156b-112">En el código siguiente se muestra el uso `try...finally` de la expresión.</span><span class="sxs-lookup"><span data-stu-id="7156b-112">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="7156b-113">La salida a la consola es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="7156b-113">The output to the console is as follows.</span></span>

```console
Closing stream
Exception handled.
```

<span data-ttu-id="7156b-114">Como puede ver en la salida, la secuencia se cerró antes de que se administrara la excepción externa y el `test.txt` archivo contiene el `test1`texto, lo que indica que los búferes se vaciaron y escribieron en el disco aunque la excepción se haya transferido. control al controlador de excepciones externo.</span><span class="sxs-lookup"><span data-stu-id="7156b-114">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="7156b-115">Tenga en cuenta `try...with` que la construcción es una construcción independiente `try...finally` de la construcción.</span><span class="sxs-lookup"><span data-stu-id="7156b-115">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="7156b-116">Por lo tanto, si el código requiere `with` un bloque y `finally` un bloque, debe anidar las dos construcciones, como en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="7156b-116">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="7156b-117">En el contexto de las expresiones de cálculo, incluidas las expresiones de secuencia y los flujos de trabajo asincrónicos, **pruebe... las expresiones Finally** pueden tener una implementación personalizada.</span><span class="sxs-lookup"><span data-stu-id="7156b-117">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="7156b-118">Para obtener más información, vea [expresiones de cálculo](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7156b-118">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7156b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7156b-119">See also</span></span>

- [<span data-ttu-id="7156b-120">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="7156b-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="7156b-121">Excepciones: La `try...with` expresión</span><span class="sxs-lookup"><span data-stu-id="7156b-121">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
