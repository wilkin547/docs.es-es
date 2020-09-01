---
description: 'try-catch-finally: Referencia de C#'
title: 'try-catch-finally: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 6e85330e12c53e0728ef671530709748090ebe02
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142016"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="659e3-103">try-catch-finally (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="659e3-103">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="659e3-104">Un uso habitual de `catch` y `finally` juntos es obtener y usar recursos de un bloque `try`, lidiar con circunstancias excepcionales de un bloque `catch` y liberar los recursos del bloque `finally`.</span><span class="sxs-lookup"><span data-stu-id="659e3-104">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="659e3-105">Para más información y ejemplos sobre cómo volver a iniciar excepciones, vea [try-catch](try-catch.md) y [Generación de excepciones](../../../standard/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="659e3-105">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="659e3-106">Para más información sobre el bloque `finally`, vea [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="659e3-106">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="659e3-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="659e3-107">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="659e3-108">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="659e3-108">C# language specification</span></span>

<span data-ttu-id="659e3-109">Para obtener más información, vea la sección sobre la [instrucción try](~/_csharplang/spec/statements.md#the-try-statement) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="659e3-109">For more information, see [The try statement](~/_csharplang/spec/statements.md#the-try-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="659e3-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="659e3-110">See also</span></span>

- [<span data-ttu-id="659e3-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="659e3-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="659e3-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="659e3-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="659e3-113">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="659e3-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="659e3-114">Instrucciones try, throw y catch (C++)</span><span class="sxs-lookup"><span data-stu-id="659e3-114">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="659e3-115">throw</span><span class="sxs-lookup"><span data-stu-id="659e3-115">throw</span></span>](throw.md)
- [<span data-ttu-id="659e3-116">Cómo: Iniciar excepciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="659e3-116">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="659e3-117">using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="659e3-117">using Statement</span></span>](using-statement.md)
