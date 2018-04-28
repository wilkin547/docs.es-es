---
title: Control de excepciones (F#)
description: 'Obtenga información acerca de los conceptos básicos del control de excepciones en F # y busque vínculos a expresiones y funciones de control de excepciones.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 37b33f9387956ee462ff4977dd4ba34a82e89ec6
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="exception-handling"></a><span data-ttu-id="19d09-103">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="19d09-103">Exception Handling</span></span>

<span data-ttu-id="19d09-104">Esta sección contiene información sobre la compatibilidad con el control de excepciones del lenguaje F#.</span><span class="sxs-lookup"><span data-stu-id="19d09-104">This section contains information about exception handling support in the F# language.</span></span>


## <a name="exception-handling-basics"></a><span data-ttu-id="19d09-105">Fundamentos del control de excepciones</span><span class="sxs-lookup"><span data-stu-id="19d09-105">Exception Handling Basics</span></span>
<span data-ttu-id="19d09-106">El control de excepciones es la manera estándar de controlar las condiciones de error en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="19d09-106">Exception handling is the standard way of handling error conditions in the .NET Framework.</span></span> <span data-ttu-id="19d09-107">Por tanto, cualquier lenguaje de .NET debe admitir este mecanismo, incluso F#.</span><span class="sxs-lookup"><span data-stu-id="19d09-107">Thus, any .NET language must support this mechanism, including F#.</span></span> <span data-ttu-id="19d09-108">Una *excepción* es un objeto que encapsula la información sobre un error.</span><span class="sxs-lookup"><span data-stu-id="19d09-108">An *exception* is an object that encapsulates information about an error.</span></span> <span data-ttu-id="19d09-109">Cuando se producen errores, se generan excepciones y se detiene la ejecución regular.</span><span class="sxs-lookup"><span data-stu-id="19d09-109">When errors occur, exceptions are raised and regular execution stops.</span></span> <span data-ttu-id="19d09-110">En su lugar, el tiempo de ejecución busca un controlador adecuado para la excepción.</span><span class="sxs-lookup"><span data-stu-id="19d09-110">Instead, the runtime searches for an appropriate handler for the exception.</span></span> <span data-ttu-id="19d09-111">La búsqueda se inicia en la función actual y continúa hasta la pila a través de los niveles de llamadores hasta que se encuentra un controlador coincidente.</span><span class="sxs-lookup"><span data-stu-id="19d09-111">The search starts in the current function, and proceeds up the stack through the layers of callers until a matching handler is found.</span></span> <span data-ttu-id="19d09-112">Después, se ejecuta el controlador.</span><span class="sxs-lookup"><span data-stu-id="19d09-112">Then the handler is executed.</span></span>

<span data-ttu-id="19d09-113">Además, cuando se desenreda la pila, el tiempo de ejecución ejecuta cualquier código en bloques `finally`, para garantizar que los objetos se limpien correctamente durante el proceso de desenredo.</span><span class="sxs-lookup"><span data-stu-id="19d09-113">In addition, as the stack is unwound, the runtime executes any code in `finally` blocks, to guarantee that objects are cleaned up correctly during the unwinding process.</span></span>


## <a name="related-topics"></a><span data-ttu-id="19d09-114">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="19d09-114">Related Topics</span></span>

|<span data-ttu-id="19d09-115">Título</span><span class="sxs-lookup"><span data-stu-id="19d09-115">Title</span></span>|<span data-ttu-id="19d09-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="19d09-116">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="19d09-117">Tipos de excepción</span><span class="sxs-lookup"><span data-stu-id="19d09-117">Exception Types</span></span>](exception-types.md)|<span data-ttu-id="19d09-118">Describe cómo declarar un tipo de excepción.</span><span class="sxs-lookup"><span data-stu-id="19d09-118">Describes how to declare an exception type.</span></span>|
|<span data-ttu-id="19d09-119">[Exceptions: The `try...with` Expression](the-try-with-expression.md) (Excepciones: la expresión `try...with`)</span><span class="sxs-lookup"><span data-stu-id="19d09-119">[Exceptions: The `try...with` Expression](the-try-with-expression.md)</span></span>|<span data-ttu-id="19d09-120">Describe la construcción de lenguaje que admite el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="19d09-120">Describes the language construct that supports exception handling.</span></span>|
|<span data-ttu-id="19d09-121">[Exceptions: The `try...finally` Expression](the-try-finally-expression.md) (Excepciones: la expresión `try...finally`)</span><span class="sxs-lookup"><span data-stu-id="19d09-121">[Exceptions: The `try...finally` Expression](the-try-finally-expression.md)</span></span>|<span data-ttu-id="19d09-122">Describe la construcción de lenguaje que permite ejecutar código de limpieza cuando se desenreda la pila al producirse una excepción.</span><span class="sxs-lookup"><span data-stu-id="19d09-122">Describes the language construct that enables you to execute clean-up code as the stack unwinds when an exception is thrown.</span></span>|
|<span data-ttu-id="19d09-123">[Exceptions: the `raise` Function](the-raise-Function.md) (Excepciones: la función `raise`)</span><span class="sxs-lookup"><span data-stu-id="19d09-123">[Exceptions: the `raise` Function](the-raise-Function.md)</span></span>|<span data-ttu-id="19d09-124">Describe cómo iniciar un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="19d09-124">Describes how to throw an exception object.</span></span>|
|<span data-ttu-id="19d09-125">[Exceptions: the `failwith` Function](the-failwith-function.md) (Excepciones: la función `failwith`)</span><span class="sxs-lookup"><span data-stu-id="19d09-125">[Exceptions: The `failwith` Function](the-failwith-function.md)</span></span>|<span data-ttu-id="19d09-126">Describe cómo generar una excepción general de F#.</span><span class="sxs-lookup"><span data-stu-id="19d09-126">Describes how to generate a general F# exception.</span></span>|
|<span data-ttu-id="19d09-127">[Exceptions: the `invalidArg` Function](the-invalidArg-function.md) (Excepciones: la función `invalidArg`)</span><span class="sxs-lookup"><span data-stu-id="19d09-127">[Exceptions: The `invalidArg` Function](the-invalidArg-function.md)</span></span>|<span data-ttu-id="19d09-128">Describe cómo generar una excepción de argumento no válido.</span><span class="sxs-lookup"><span data-stu-id="19d09-128">Describes how to generate an invalid argument exception.</span></span>|
