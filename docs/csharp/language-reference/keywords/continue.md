---
title: continue (instrucción, Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 37315caf14ba829dfc91da065bc49982f21b947f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861411"
---
# <a name="continue-c-reference"></a><span data-ttu-id="f6366-102">continue (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f6366-102">continue (C# Reference)</span></span>

<span data-ttu-id="f6366-103">La instrucción `continue` transfiere el control a la siguiente iteración de la instrucción envolvente [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) o [foreach](../../../csharp/language-reference/keywords/foreach-in.md) en la que aparece.</span><span class="sxs-lookup"><span data-stu-id="f6366-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="f6366-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f6366-104">Example</span></span>

<span data-ttu-id="f6366-105">En este ejemplo se inicializa un contador para contar del 1 al 10.</span><span class="sxs-lookup"><span data-stu-id="f6366-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="f6366-106">Si se usa la instrucción `continue` junto con la expresión `(i < 9)`, se omiten las instrucciones comprendidas entre `continue` y el final del cuerpo de `for`.</span><span class="sxs-lookup"><span data-stu-id="f6366-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="f6366-107">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f6366-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f6366-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6366-108">See also</span></span>

- [<span data-ttu-id="f6366-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f6366-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="f6366-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f6366-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f6366-111">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="f6366-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="f6366-112">break (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="f6366-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)  
- [<span data-ttu-id="f6366-113">Instrucciones de salto</span><span class="sxs-lookup"><span data-stu-id="f6366-113">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)