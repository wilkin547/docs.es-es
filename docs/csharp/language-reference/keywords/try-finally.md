---
description: 'try-finally: Referencia de C#'
title: 'try-finally: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- finally
- finally_CSharpKeyword
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
ms.openlocfilehash: 03e5fa46cef6b30a0af15c113ec6b141a61bee47
ms.sourcegitcommit: 456b3cd82a87b453fa737b4661295070d1b6d684
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "100639421"
---
# <a name="try-finally-c-reference"></a><span data-ttu-id="fd5d9-103">try-finally (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="fd5d9-103">try-finally (C# Reference)</span></span>

<span data-ttu-id="fd5d9-104">Mediante el uso de un bloque `finally`, puede limpiar todos los recursos asignados en un bloque [try](try-catch.md) y ejecutar código incluso si se produce una excepción en el bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-104">By using a `finally` block, you can clean up any resources that are allocated in a [try](try-catch.md) block, and you can run code even if an exception occurs in the `try` block.</span></span> <span data-ttu-id="fd5d9-105">Normalmente, las instrucciones de un bloque `finally` se ejecutan cuando el control abandona una instrucción `try`.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-105">Typically, the statements of a `finally` block run when control leaves a `try` statement.</span></span> <span data-ttu-id="fd5d9-106">La transferencia de control se puede producir como resultado de la ejecución normal, de la ejecución de una instrucción `break`, `continue`, `goto` o `return`, o de la propagación de una excepción fuera de la instrucción `try`.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-106">The transfer of control can occur as a result of normal execution, of execution of a `break`, `continue`, `goto`, or `return` statement, or of propagation of an exception out of the `try` statement.</span></span>

<span data-ttu-id="fd5d9-107">Dentro de una excepción controlada, se garantiza la ejecución del bloque `finally` asociado.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-107">Within a handled exception, the associated `finally` block is guaranteed to be run.</span></span> <span data-ttu-id="fd5d9-108">Pero en el caso de una excepción no controlada, la ejecución del bloque `finally` depende de la manera en que se desencadene la operación de desenredo de la excepción.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-108">However, if the exception is unhandled, execution of the `finally` block is dependent on how the exception unwind operation is triggered.</span></span> <span data-ttu-id="fd5d9-109">Esto, a su vez, depende de cómo esté configurado el equipo.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-109">That, in turn, is dependent on how your computer is set up.</span></span> <span data-ttu-id="fd5d9-110">Los únicos casos en los que no se ejecutan las cláusulas `finally` implican que un programa se detenga inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-110">The only cases where `finally` clauses don't run involve a program being immediately stopped.</span></span> <span data-ttu-id="fd5d9-111">Un ejemplo de esto sería cuando se produce <xref:System.InvalidProgramException> debido a que las instrucciones IL están dañadas.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-111">An example of this would be when <xref:System.InvalidProgramException> gets thrown because of the IL statements being corrupt.</span></span> <span data-ttu-id="fd5d9-112">En la mayoría de los sistemas operativos, la limpieza de recursos razonable tendrá lugar como parte de la detención y descarga del proceso.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-112">On most operating systems, reasonable resource cleanup will take place as part of stopping and unloading the process.</span></span>

<span data-ttu-id="fd5d9-113">Normalmente, cuando una excepción no controlada finaliza una aplicación, no es importante si el bloque `finally` se ejecuta o no.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-113">Usually, when an unhandled exception ends an application, whether or not the `finally` block is run is not important.</span></span> <span data-ttu-id="fd5d9-114">Pero si tiene instrucciones en un bloque `finally` que debe ejecutarse incluso en esa situación, una solución es agregar un bloque `catch` a la instrucción `try`-`finally`.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-114">However, if you have statements in a `finally` block that must be run even in that situation, one solution is to add a `catch` block to the `try`-`finally` statement.</span></span> <span data-ttu-id="fd5d9-115">Como alternativa, puede capturar la excepción que se podría producir en el bloque `try` de una instrucción `try`-`finally` más arriba en la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-115">Alternatively, you can catch the exception that might be thrown in the `try` block of a `try`-`finally` statement higher up the call stack.</span></span> <span data-ttu-id="fd5d9-116">Es decir, puede capturar la excepción en el método que llama al método que contiene la instrucción `try`-`finally`, en el método que llama a ese método o en cualquier método en la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-116">That is, you can catch the exception in the method that calls the method that contains the `try`-`finally` statement, or in the method that calls that method, or in any method in the call stack.</span></span> <span data-ttu-id="fd5d9-117">Si no se captura la excepción, la ejecución del bloque `finally` depende de si el sistema operativo decide desencadenar una operación de desenredo de la excepción.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-117">If the exception is not caught, execution of the `finally` block depends on whether the operating system chooses to trigger an exception unwind operation.</span></span>

## <a name="example"></a><span data-ttu-id="fd5d9-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fd5d9-118">Example</span></span>

<span data-ttu-id="fd5d9-119">En el ejemplo siguiente, una instrucción de conversión no válida provoca una excepción `System.InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-119">In the following example, an invalid conversion statement causes a `System.InvalidCastException` exception.</span></span> <span data-ttu-id="fd5d9-120">Se trata de una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-120">The exception is unhandled.</span></span>

[!code-csharp[csrefKeywordsExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#4)]

<span data-ttu-id="fd5d9-121">En el ejemplo siguiente, se captura una excepción del método `TryCast` en un método más arriba en la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-121">In the following example, an exception from the `TryCast` method is caught in a method farther up the call stack.</span></span>

[!code-csharp[csrefKeywordsExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#6)]

<span data-ttu-id="fd5d9-122">Para obtener más información sobre `finally`, vea [try-catch-finally](try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="fd5d9-122">For more information about `finally`, see [try-catch-finally](try-catch-finally.md).</span></span>

<span data-ttu-id="fd5d9-123">C# también contiene la [instrucción using](using-statement.md), que proporciona una función similar para objetos <xref:System.IDisposable> en una sintaxis adecuada.</span><span class="sxs-lookup"><span data-stu-id="fd5d9-123">C# also contains the [using statement](using-statement.md), which provides similar functionality for <xref:System.IDisposable> objects in a convenient syntax.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fd5d9-124">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="fd5d9-124">C# language specification</span></span>

<span data-ttu-id="fd5d9-125">Para obtener más información, vea la sección sobre la [instrucción try](~/_csharplang/spec/statements.md#the-try-statement) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="fd5d9-125">For more information, see [The try statement](~/_csharplang/spec/statements.md#the-try-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd5d9-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd5d9-126">See also</span></span>

- [<span data-ttu-id="fd5d9-127">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="fd5d9-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fd5d9-128">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fd5d9-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fd5d9-129">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="fd5d9-129">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="fd5d9-130">Instrucciones try, throw y catch (C++)</span><span class="sxs-lookup"><span data-stu-id="fd5d9-130">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="fd5d9-131">throw</span><span class="sxs-lookup"><span data-stu-id="fd5d9-131">throw</span></span>](throw.md)
- [<span data-ttu-id="fd5d9-132">try-catch</span><span class="sxs-lookup"><span data-stu-id="fd5d9-132">try-catch</span></span>](try-catch.md)
- [<span data-ttu-id="fd5d9-133">Cómo: Iniciar excepciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="fd5d9-133">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
