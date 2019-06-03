---
title: 'Instrucción continue: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: d5fd2f5edf85c3ac2c8f0367b85b37e76e2e856e
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422111"
---
# <a name="continue-c-reference"></a><span data-ttu-id="8e3bf-102">continue (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8e3bf-102">continue (C# Reference)</span></span>

<span data-ttu-id="8e3bf-103">La instrucción `continue` transfiere el control a la siguiente iteración de la instrucción envolvente [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) o [foreach](../../../csharp/language-reference/keywords/foreach-in.md) en la que aparece.</span><span class="sxs-lookup"><span data-stu-id="8e3bf-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="8e3bf-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8e3bf-104">Example</span></span>

<span data-ttu-id="8e3bf-105">En este ejemplo se inicializa un contador para contar del 1 al 10.</span><span class="sxs-lookup"><span data-stu-id="8e3bf-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="8e3bf-106">Si se usa la instrucción `continue` junto con la expresión `(i < 9)`, se omiten las instrucciones comprendidas entre `continue` y el final del cuerpo de `for`.</span><span class="sxs-lookup"><span data-stu-id="8e3bf-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="8e3bf-107">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="8e3bf-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="8e3bf-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e3bf-108">See also</span></span>

- [<span data-ttu-id="8e3bf-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="8e3bf-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="8e3bf-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8e3bf-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="8e3bf-111">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="8e3bf-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="8e3bf-112">break (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e3bf-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
