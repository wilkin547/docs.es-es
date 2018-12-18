---
title: 'try-catch-finally: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 3419ad46d5bbe13bb4308ad15b7819d615cdbe86
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244731"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="5dbb5-102">try-catch-finally (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5dbb5-102">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="5dbb5-103">Un uso habitual de `catch` y `finally` juntos es obtener y usar recursos de un bloque `try`, lidiar con circunstancias excepcionales de un bloque `catch` y liberar los recursos del bloque `finally`.</span><span class="sxs-lookup"><span data-stu-id="5dbb5-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="5dbb5-104">Para más información y ejemplos sobre cómo volver a iniciar excepciones, vea [try-catch](try-catch.md) y [Generación de excepciones](../../../standard/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="5dbb5-104">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="5dbb5-105">Para más información sobre el bloque `finally`, vea [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="5dbb5-105">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="5dbb5-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5dbb5-106">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="5dbb5-107">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5dbb5-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5dbb5-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="5dbb5-108">See also</span></span>

- [<span data-ttu-id="5dbb5-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="5dbb5-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5dbb5-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5dbb5-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5dbb5-111">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="5dbb5-111">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="5dbb5-112">Instrucciones try, throw y catch (C++)</span><span class="sxs-lookup"><span data-stu-id="5dbb5-112">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="5dbb5-113">Instrucciones para el control de excepciones</span><span class="sxs-lookup"><span data-stu-id="5dbb5-113">Exception Handling Statements</span></span>](exception-handling-statements.md)
- [<span data-ttu-id="5dbb5-114">throw</span><span class="sxs-lookup"><span data-stu-id="5dbb5-114">throw</span></span>](throw.md)
- [<span data-ttu-id="5dbb5-115">Cómo: Iniciar excepciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="5dbb5-115">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="5dbb5-116">using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5dbb5-116">using Statement</span></span>](using-statement.md)