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
ms.openlocfilehash: 0b3baf6eb4843ff67a3d76af06ca86ca9ec2db03
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690599"
---
# <a name="continue-c-reference"></a><span data-ttu-id="5d286-102">continue (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5d286-102">continue (C# Reference)</span></span>

<span data-ttu-id="5d286-103">La instrucción `continue` transfiere el control a la siguiente iteración de la instrucción envolvente [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) o [foreach](../../../csharp/language-reference/keywords/foreach-in.md) en la que aparece.</span><span class="sxs-lookup"><span data-stu-id="5d286-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="5d286-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d286-104">Example</span></span>

<span data-ttu-id="5d286-105">En este ejemplo se inicializa un contador para contar del 1 al 10.</span><span class="sxs-lookup"><span data-stu-id="5d286-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="5d286-106">Si se usa la instrucción `continue` junto con la expresión `(i < 9)`, se omiten las instrucciones comprendidas entre `continue` y el final del cuerpo de `for`.</span><span class="sxs-lookup"><span data-stu-id="5d286-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="5d286-107">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5d286-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5d286-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d286-108">See also</span></span>

- [<span data-ttu-id="5d286-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="5d286-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="5d286-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5d286-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="5d286-111">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="5d286-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="5d286-112">break (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="5d286-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
- [<span data-ttu-id="5d286-113">Instrucciones de salto</span><span class="sxs-lookup"><span data-stu-id="5d286-113">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
