---
title: 'Excepciones: función raise'
description: Obtenga información sobre cómo el F# 'raise' función se utiliza para indicar que se ha producido un error o una condición excepcional.
ms.date: 05/16/2016
ms.openlocfilehash: 87773ead7773c62a325c7e7ff105c729e10dd69c
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610156"
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="f7f2f-103">Excepciones: función raise</span><span class="sxs-lookup"><span data-stu-id="f7f2f-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="f7f2f-104">El `raise` función se utiliza para indicar que se ha producido un error o una condición excepcional.</span><span class="sxs-lookup"><span data-stu-id="f7f2f-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="f7f2f-105">Información sobre el error se captura en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="f7f2f-105">Information about the error is captured in an exception object.</span></span>

## <a name="syntax"></a><span data-ttu-id="f7f2f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7f2f-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="f7f2f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7f2f-107">Remarks</span></span>

<span data-ttu-id="f7f2f-108">El `raise` función genera un objeto de excepción e inicia una proceso de desenredo de pila.</span><span class="sxs-lookup"><span data-stu-id="f7f2f-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="f7f2f-109">El proceso de desenredo de pila es administrado por common language runtime (CLR), por lo que el comportamiento de este proceso es el mismo, como en cualquier otro lenguaje. NET.</span><span class="sxs-lookup"><span data-stu-id="f7f2f-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="f7f2f-110">El proceso de desenredo de pila es una búsqueda de un controlador de excepciones que coincida con la excepción generada.</span><span class="sxs-lookup"><span data-stu-id="f7f2f-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="f7f2f-111">La búsqueda comienza en el actual `try...with` expresión, si hay alguno.</span><span class="sxs-lookup"><span data-stu-id="f7f2f-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="f7f2f-112">Cada patrón en el `with` se activa el bloque, en orden.</span><span class="sxs-lookup"><span data-stu-id="f7f2f-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="f7f2f-113">Cuando se encuentra un controlador de excepción coincidente, la excepción se considera controlado; en caso contrario, se desenreda la pila y `with` se comprueban los bloques de la cadena de llamada hasta que se encuentra un controlador coincidente.</span><span class="sxs-lookup"><span data-stu-id="f7f2f-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="f7f2f-114">Cualquier `finally` bloques que se encuentran en la cadena de llamadas también se ejecutan en secuencia desenreda la pila.</span><span class="sxs-lookup"><span data-stu-id="f7f2f-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="f7f2f-115">El `raise` función es el equivalente de `throw` en C# o C++.</span><span class="sxs-lookup"><span data-stu-id="f7f2f-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="f7f2f-116">Use `reraise` en un controlador catch para propagar la misma excepción de la cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="f7f2f-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="f7f2f-117">Ejemplos de código siguientes ilustran el uso de la `raise` función para generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="f7f2f-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="f7f2f-118">El `raise` función también se puede utilizar para generar excepciones de. NET, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f7f2f-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a><span data-ttu-id="f7f2f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7f2f-119">See also</span></span>

- [<span data-ttu-id="f7f2f-120">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="f7f2f-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="f7f2f-121">Tipos de excepción</span><span class="sxs-lookup"><span data-stu-id="f7f2f-121">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="f7f2f-122">Excepciones: El `try...with` expresión</span><span class="sxs-lookup"><span data-stu-id="f7f2f-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
- [<span data-ttu-id="f7f2f-123">Excepciones: El `try...finally` expresión</span><span class="sxs-lookup"><span data-stu-id="f7f2f-123">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
- [<span data-ttu-id="f7f2f-124">Excepciones: El `failwith` (función)</span><span class="sxs-lookup"><span data-stu-id="f7f2f-124">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)
- [<span data-ttu-id="f7f2f-125">Excepciones: El `invalidArg` (función)</span><span class="sxs-lookup"><span data-stu-id="f7f2f-125">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)