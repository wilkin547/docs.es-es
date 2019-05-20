---
title: 'try-finally: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- finally
- finally_CSharpKeyword
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
ms.openlocfilehash: 20a608c208a7c5e6f00b85dfc10cf14202a78446
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633133"
---
# <a name="try-finally-c-reference"></a><span data-ttu-id="97c17-102">try-finally (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="97c17-102">try-finally (C# Reference)</span></span>

<span data-ttu-id="97c17-103">Mediante el uso de un bloque `finally`, puede limpiar todos los recursos asignados en un bloque [try](try-catch.md) y ejecutar código incluso si se produce una excepción en el bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="97c17-103">By using a `finally` block, you can clean up any resources that are allocated in a [try](try-catch.md) block, and you can run code even if an exception occurs in the `try` block.</span></span> <span data-ttu-id="97c17-104">Normalmente, las instrucciones de un bloque `finally` se ejecutan cuando el control abandona una instrucción `try`.</span><span class="sxs-lookup"><span data-stu-id="97c17-104">Typically, the statements of a `finally` block run when control leaves a `try` statement.</span></span> <span data-ttu-id="97c17-105">La transferencia de control se puede producir como resultado de la ejecución normal, de la ejecución de una instrucción `break`, `continue`, `goto` o `return`, o de la propagación de una excepción fuera de la instrucción `try`.</span><span class="sxs-lookup"><span data-stu-id="97c17-105">The transfer of control can occur as a result of normal execution, of execution of a `break`, `continue`, `goto`, or `return` statement, or of propagation of an exception out of the `try` statement.</span></span>

<span data-ttu-id="97c17-106">Dentro de una excepción controlada, se garantiza la ejecución del bloque `finally` asociado.</span><span class="sxs-lookup"><span data-stu-id="97c17-106">Within a handled exception, the associated `finally` block is guaranteed to be run.</span></span> <span data-ttu-id="97c17-107">Pero en el caso de una excepción no controlada, la ejecución del bloque `finally` depende de la manera en que se desencadene la operación de desenredo de la excepción.</span><span class="sxs-lookup"><span data-stu-id="97c17-107">However, if the exception is unhandled, execution of the `finally` block is dependent on how the exception unwind operation is triggered.</span></span> <span data-ttu-id="97c17-108">Esto, a su vez, depende de cómo esté configurado el equipo.</span><span class="sxs-lookup"><span data-stu-id="97c17-108">That, in turn, is dependent on how your computer is set up.</span></span>

<span data-ttu-id="97c17-109">Normalmente, cuando una excepción no controlada finaliza una aplicación, no es importante si el bloque `finally` se ejecuta o no.</span><span class="sxs-lookup"><span data-stu-id="97c17-109">Usually, when an unhandled exception ends an application, whether or not the `finally` block is run is not important.</span></span> <span data-ttu-id="97c17-110">Pero si tiene instrucciones en un bloque `finally` que debe ejecutarse incluso en esa situación, una solución es agregar un bloque `catch` a la instrucción `try`-`finally`.</span><span class="sxs-lookup"><span data-stu-id="97c17-110">However, if you have statements in a `finally` block that must be run even in that situation, one solution is to add a `catch` block to the `try`-`finally` statement.</span></span> <span data-ttu-id="97c17-111">Como alternativa, puede capturar la excepción que se podría producir en el bloque `try` de una instrucción `try`-`finally` más arriba en la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="97c17-111">Alternatively, you can catch the exception that might be thrown in the `try` block of a `try`-`finally` statement higher up the call stack.</span></span> <span data-ttu-id="97c17-112">Es decir, puede capturar la excepción en el método que llama al método que contiene la instrucción `try`-`finally`, en el método que llama a ese método o en cualquier método en la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="97c17-112">That is, you can catch the exception in the method that calls the method that contains the `try`-`finally` statement, or in the method that calls that method, or in any method in the call stack.</span></span> <span data-ttu-id="97c17-113">Si no se captura la excepción, la ejecución del bloque `finally` depende de si el sistema operativo decide desencadenar una operación de desenredo de la excepción.</span><span class="sxs-lookup"><span data-stu-id="97c17-113">If the exception is not caught, execution of the `finally` block depends on whether the operating system chooses to trigger an exception unwind operation.</span></span>

## <a name="example"></a><span data-ttu-id="97c17-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97c17-114">Example</span></span>

<span data-ttu-id="97c17-115">En el ejemplo siguiente, una instrucción de conversión no válida provoca una excepción `System.InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="97c17-115">In the following example, an invalid conversion statement causes a `System.InvalidCastException` exception.</span></span> <span data-ttu-id="97c17-116">Se trata de una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="97c17-116">The exception is unhandled.</span></span>

[!code-csharp[csrefKeywordsExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#4)]

<span data-ttu-id="97c17-117">En el ejemplo siguiente, se captura una excepción del método `TryCast` en un método más arriba en la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="97c17-117">In the following example, an exception from the `TryCast` method is caught in a method farther up the call stack.</span></span>

[!code-csharp[csrefKeywordsExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#6)]

<span data-ttu-id="97c17-118">Para obtener más información sobre `finally`, vea [try-catch-finally](try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="97c17-118">For more information about `finally`, see [try-catch-finally](try-catch-finally.md).</span></span>

<span data-ttu-id="97c17-119">C# también contiene la [instrucción using](using-statement.md), que proporciona una función similar para objetos <xref:System.IDisposable> en una sintaxis adecuada.</span><span class="sxs-lookup"><span data-stu-id="97c17-119">C# also contains the [using statement](using-statement.md), which provides similar functionality for <xref:System.IDisposable> objects in a convenient syntax.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="97c17-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="97c17-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="97c17-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="97c17-121">See also</span></span>

- [<span data-ttu-id="97c17-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="97c17-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="97c17-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="97c17-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="97c17-124">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="97c17-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="97c17-125">Instrucciones try, throw y catch (C++)</span><span class="sxs-lookup"><span data-stu-id="97c17-125">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="97c17-126">Instrucciones para el control de excepciones</span><span class="sxs-lookup"><span data-stu-id="97c17-126">Exception Handling Statements</span></span>](exception-handling-statements.md)
- [<span data-ttu-id="97c17-127">throw</span><span class="sxs-lookup"><span data-stu-id="97c17-127">throw</span></span>](throw.md)
- [<span data-ttu-id="97c17-128">try-catch</span><span class="sxs-lookup"><span data-stu-id="97c17-128">try-catch</span></span>](try-catch.md)
- [<span data-ttu-id="97c17-129">Cómo: Iniciar excepciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="97c17-129">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
