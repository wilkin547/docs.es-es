---
title: "Excepciones: función raise (F#)"
description: "Obtenga información acerca de cómo se utiliza la función 'raise' de F # para indicar que hubo un error o una condición excepcional."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b00da469-4789-4cdd-9f77-7a2e29f28637
ms.openlocfilehash: dc524a06d075b982a6aa1fd266769bfc7d883517
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="a578a-104">Excepciones: función raise</span><span class="sxs-lookup"><span data-stu-id="a578a-104">Exceptions: the raise Function</span></span>

<span data-ttu-id="a578a-105">El `raise` función se utiliza para indicar que hubo un error o una condición excepcional.</span><span class="sxs-lookup"><span data-stu-id="a578a-105">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="a578a-106">Información sobre el error se captura en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="a578a-106">Information about the error is captured in an exception object.</span></span>


## <a name="syntax"></a><span data-ttu-id="a578a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a578a-107">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="a578a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a578a-108">Remarks</span></span>
<span data-ttu-id="a578a-109">El `raise` función genera un objeto de excepción e inicia una proceso de desenredo de pila.</span><span class="sxs-lookup"><span data-stu-id="a578a-109">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="a578a-110">El proceso de desenredo de pila es administrado por common language runtime (CLR), por lo que el comportamiento de este proceso es el mismo como en cualquier otro lenguaje. NET.</span><span class="sxs-lookup"><span data-stu-id="a578a-110">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="a578a-111">El proceso de desenredo de pila es una búsqueda de un controlador de excepciones que coincida con la excepción generada.</span><span class="sxs-lookup"><span data-stu-id="a578a-111">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="a578a-112">La búsqueda comienza en el actual `try...with` expresión, si hay alguno.</span><span class="sxs-lookup"><span data-stu-id="a578a-112">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="a578a-113">Cada modelo en el `with` se activa el bloque, en orden.</span><span class="sxs-lookup"><span data-stu-id="a578a-113">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="a578a-114">Cuando se encuentra un controlador de excepción coincidente, la excepción se considera controlada; en caso contrario, se desenreda la pila y `with` se comprueban los bloques de la cadena de llamadas hasta que encuentra un controlador coincidente.</span><span class="sxs-lookup"><span data-stu-id="a578a-114">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="a578a-115">Cualquier `finally` bloques que se encuentran en la cadena de llamadas también se ejecutan en la secuencia que se desenreda la pila.</span><span class="sxs-lookup"><span data-stu-id="a578a-115">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="a578a-116">El `raise` función es el equivalente de `throw` en C# o C++.</span><span class="sxs-lookup"><span data-stu-id="a578a-116">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="a578a-117">Use `reraise` en un controlador de tipo catch para propagar la misma excepción por la cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a578a-117">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="a578a-118">Ejemplos de código siguientes muestran el uso de la `raise` función puede generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="a578a-118">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="a578a-119">El `raise` función también puede utilizarse para generar excepciones de. NET, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a578a-119">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]
    
## <a name="see-also"></a><span data-ttu-id="a578a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a578a-120">See Also</span></span>
[<span data-ttu-id="a578a-121">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="a578a-121">Exception Handling</span></span>](index.md)

[<span data-ttu-id="a578a-122">Tipos de excepción</span><span class="sxs-lookup"><span data-stu-id="a578a-122">Exception Types</span></span>](exception-types.md)

<span data-ttu-id="a578a-123">[Exceptions: The `try...with` Expression](the-try-with-expression.md) (Excepciones: la expresión `try...with`)</span><span class="sxs-lookup"><span data-stu-id="a578a-123">[Exceptions: The `try...with` Expression](the-try-with-expression.md)</span></span>

<span data-ttu-id="a578a-124">[Exceptions: The `try...finally` Expression](the-try-finally-expression.md) (Excepciones: la expresión `try...finally`)</span><span class="sxs-lookup"><span data-stu-id="a578a-124">[Exceptions: The `try...finally` Expression](the-try-finally-expression.md)</span></span>

<span data-ttu-id="a578a-125">[Exceptions: the `failwith` Function](the-failwith-function.md) (Excepciones: la función `failwith`)</span><span class="sxs-lookup"><span data-stu-id="a578a-125">[Exceptions: The `failwith` Function](the-failwith-function.md)</span></span>

<span data-ttu-id="a578a-126">[Exceptions: the `invalidArg` Function](the-invalidArg-function.md) (Excepciones: la función `invalidArg`)</span><span class="sxs-lookup"><span data-stu-id="a578a-126">[Exceptions: The `invalidArg` Function](the-invalidArg-function.md)</span></span>
