---
title: 'Excepciones: función raise (F#)'
description: Obtenga información sobre cómo se utiliza la función 'raise' de F# para indicar que se ha producido un error o una condición excepcional.
ms.date: 05/16/2016
ms.openlocfilehash: 537d274659d29404380bfdd56310ac267372bb98
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "43778264"
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="f9020-103">Excepciones: función raise</span><span class="sxs-lookup"><span data-stu-id="f9020-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="f9020-104">El `raise` función se utiliza para indicar que se ha producido un error o una condición excepcional.</span><span class="sxs-lookup"><span data-stu-id="f9020-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="f9020-105">Información sobre el error se captura en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="f9020-105">Information about the error is captured in an exception object.</span></span>

## <a name="syntax"></a><span data-ttu-id="f9020-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9020-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="f9020-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f9020-107">Remarks</span></span>

<span data-ttu-id="f9020-108">El `raise` función genera un objeto de excepción e inicia una proceso de desenredo de pila.</span><span class="sxs-lookup"><span data-stu-id="f9020-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="f9020-109">El proceso de desenredo de pila es administrado por common language runtime (CLR), por lo que el comportamiento de este proceso es el mismo, como en cualquier otro lenguaje. NET.</span><span class="sxs-lookup"><span data-stu-id="f9020-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="f9020-110">El proceso de desenredo de pila es una búsqueda de un controlador de excepciones que coincida con la excepción generada.</span><span class="sxs-lookup"><span data-stu-id="f9020-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="f9020-111">La búsqueda comienza en el actual `try...with` expresión, si hay alguno.</span><span class="sxs-lookup"><span data-stu-id="f9020-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="f9020-112">Cada patrón en el `with` se activa el bloque, en orden.</span><span class="sxs-lookup"><span data-stu-id="f9020-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="f9020-113">Cuando se encuentra un controlador de excepción coincidente, la excepción se considera controlado; en caso contrario, se desenreda la pila y `with` se comprueban los bloques de la cadena de llamada hasta que se encuentra un controlador coincidente.</span><span class="sxs-lookup"><span data-stu-id="f9020-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="f9020-114">Cualquier `finally` bloques que se encuentran en la cadena de llamadas también se ejecutan en secuencia desenreda la pila.</span><span class="sxs-lookup"><span data-stu-id="f9020-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="f9020-115">El `raise` función es el equivalente de `throw` en C# o C++.</span><span class="sxs-lookup"><span data-stu-id="f9020-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="f9020-116">Use `reraise` en un controlador catch para propagar la misma excepción de la cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="f9020-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="f9020-117">Ejemplos de código siguientes ilustran el uso de la `raise` función para generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="f9020-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="f9020-118">El `raise` función también se puede utilizar para generar excepciones de. NET, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f9020-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a><span data-ttu-id="f9020-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9020-119">See also</span></span>

- [<span data-ttu-id="f9020-120">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="f9020-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="f9020-121">Tipos de excepción</span><span class="sxs-lookup"><span data-stu-id="f9020-121">Exception Types</span></span>](exception-types.md)
- <span data-ttu-id="f9020-122">[Exceptions: The `try...with` Expression](the-try-with-expression.md) (Excepciones: la expresión `try...with`)</span><span class="sxs-lookup"><span data-stu-id="f9020-122">[Exceptions: The `try...with` Expression](the-try-with-expression.md)</span></span>
- <span data-ttu-id="f9020-123">[Exceptions: The `try...finally` Expression](the-try-finally-expression.md) (Excepciones: la expresión `try...finally`)</span><span class="sxs-lookup"><span data-stu-id="f9020-123">[Exceptions: The `try...finally` Expression](the-try-finally-expression.md)</span></span>
- <span data-ttu-id="f9020-124">[Exceptions: the `failwith` Function](the-failwith-function.md) (Excepciones: la función `failwith`)</span><span class="sxs-lookup"><span data-stu-id="f9020-124">[Exceptions: The `failwith` Function](the-failwith-function.md)</span></span>
- <span data-ttu-id="f9020-125">[Exceptions: the `invalidArg` Function](the-invalidArg-function.md) (Excepciones: la función `invalidArg`)</span><span class="sxs-lookup"><span data-stu-id="f9020-125">[Exceptions: The `invalidArg` Function](the-invalidArg-function.md)</span></span>
