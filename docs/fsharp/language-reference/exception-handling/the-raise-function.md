---
title: 'Excepciones: función raise'
description: Obtenga información sobre F# cómo se usa la función ' raise ' para indicar que se ha producido un error o una condición excepcional.
ms.date: 05/16/2016
ms.openlocfilehash: e0cc8da8310203c537b8081af8a225671bd8c6a3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630287"
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="3819e-103">Excepciones: función raise</span><span class="sxs-lookup"><span data-stu-id="3819e-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="3819e-104">La `raise` función se usa para indicar que se ha producido un error o una condición excepcional.</span><span class="sxs-lookup"><span data-stu-id="3819e-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="3819e-105">La información sobre el error se captura en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="3819e-105">Information about the error is captured in an exception object.</span></span>

## <a name="syntax"></a><span data-ttu-id="3819e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3819e-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="3819e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3819e-107">Remarks</span></span>

<span data-ttu-id="3819e-108">La `raise` función genera un objeto de excepción e inicia un proceso de desenredado de la pila.</span><span class="sxs-lookup"><span data-stu-id="3819e-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="3819e-109">El proceso de desenredado de la pila se administra mediante el Common Language Runtime (CLR), por lo que el comportamiento de este proceso es el mismo que en cualquier otro lenguaje de .NET.</span><span class="sxs-lookup"><span data-stu-id="3819e-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="3819e-110">El proceso de desenredado de la pila es una búsqueda de un controlador de excepciones que coincide con la excepción generada.</span><span class="sxs-lookup"><span data-stu-id="3819e-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="3819e-111">La búsqueda se inicia en la `try...with` expresión actual, si hay alguna.</span><span class="sxs-lookup"><span data-stu-id="3819e-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="3819e-112">Cada patrón del `with` bloque se comprueba en orden.</span><span class="sxs-lookup"><span data-stu-id="3819e-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="3819e-113">Cuando se encuentra un controlador de excepciones coincidente, la excepción se considera controlada; de lo contrario, la pila se desenreda `with` y se bloquea la cadena de llamadas hasta que se encuentra un controlador coincidente.</span><span class="sxs-lookup"><span data-stu-id="3819e-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="3819e-114">Los `finally` bloques que se encuentran en la cadena de llamadas también se ejecutan en secuencia cuando se desenreda la pila.</span><span class="sxs-lookup"><span data-stu-id="3819e-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="3819e-115">La `raise` función es el equivalente de `throw` en C# o C++.</span><span class="sxs-lookup"><span data-stu-id="3819e-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="3819e-116">Use `reraise` en un controlador catch para propagar la misma excepción hacia arriba en la cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3819e-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="3819e-117">En los siguientes ejemplos de código se muestra el `raise` uso de la función para generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="3819e-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="3819e-118">La `raise` función también se puede utilizar para generar excepciones de .net, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3819e-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a><span data-ttu-id="3819e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3819e-119">See also</span></span>

- [<span data-ttu-id="3819e-120">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="3819e-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="3819e-121">Tipos de excepción</span><span class="sxs-lookup"><span data-stu-id="3819e-121">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="3819e-122">Excepciones: La `try...with` expresión</span><span class="sxs-lookup"><span data-stu-id="3819e-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
- [<span data-ttu-id="3819e-123">Excepciones: La `try...finally` expresión</span><span class="sxs-lookup"><span data-stu-id="3819e-123">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
- [<span data-ttu-id="3819e-124">Excepciones: La `failwith` función</span><span class="sxs-lookup"><span data-stu-id="3819e-124">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)
- [<span data-ttu-id="3819e-125">Excepciones: La `invalidArg` función</span><span class="sxs-lookup"><span data-stu-id="3819e-125">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)
