---
title: 'try-catch-finally: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 5d98f6967595c7c32b23ba5422a8d9ca79f7f54c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713045"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="4f937-102">try-catch-finally (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4f937-102">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="4f937-103">Un uso habitual de `catch` y `finally` juntos es obtener y usar recursos de un bloque `try`, lidiar con circunstancias excepcionales de un bloque `catch` y liberar los recursos del bloque `finally`.</span><span class="sxs-lookup"><span data-stu-id="4f937-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="4f937-104">Para más información y ejemplos sobre cómo volver a iniciar excepciones, vea [try-catch](try-catch.md) y [Generación de excepciones](../../../standard/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="4f937-104">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="4f937-105">Para más información sobre el bloque `finally`, vea [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="4f937-105">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="4f937-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f937-106">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="4f937-107">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4f937-107">C# language specification</span></span>

<span data-ttu-id="4f937-108">Para obtener más información, vea la sección sobre la [instrucción try](~/_csharplang/spec/statements.md#the-try-statement) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="4f937-108">For more information, see [The try statement](~/_csharplang/spec/statements.md#the-try-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4f937-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f937-109">See also</span></span>

- [<span data-ttu-id="4f937-110">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="4f937-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4f937-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4f937-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4f937-112">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="4f937-112">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="4f937-113">Instrucciones try, throw y catch (C++)</span><span class="sxs-lookup"><span data-stu-id="4f937-113">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="4f937-114">throw</span><span class="sxs-lookup"><span data-stu-id="4f937-114">throw</span></span>](throw.md)
- [<span data-ttu-id="4f937-115">Cómo: Iniciar excepciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="4f937-115">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="4f937-116">using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4f937-116">using Statement</span></span>](using-statement.md)
