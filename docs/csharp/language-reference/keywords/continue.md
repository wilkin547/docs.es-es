---
title: continue (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: b3a9a17bb16ded19330cbc880b2e5e7271f269c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="continue-c-reference"></a><span data-ttu-id="fbcfa-102">continue (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="fbcfa-102">continue (C# Reference)</span></span>
<span data-ttu-id="fbcfa-103">La instrucción `continue` transfiere el control a la siguiente iteración de la instrucción envolvente [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) o [foreach](../../../csharp/language-reference/keywords/foreach-in.md) en la que aparece.</span><span class="sxs-lookup"><span data-stu-id="fbcfa-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbcfa-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fbcfa-104">Example</span></span>  
 <span data-ttu-id="fbcfa-105">En este ejemplo se inicializa un contador para contar del 1 al 10.</span><span class="sxs-lookup"><span data-stu-id="fbcfa-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="fbcfa-106">Si se usa la instrucción `continue` junto con la expresión `(i < 9)`, se omiten las instrucciones comprendidas entre `continue` y el final del cuerpo de `for`.</span><span class="sxs-lookup"><span data-stu-id="fbcfa-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/continue_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="fbcfa-107">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="fbcfa-107">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fbcfa-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbcfa-108">See Also</span></span>  
 [<span data-ttu-id="fbcfa-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="fbcfa-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="fbcfa-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fbcfa-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fbcfa-111">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="fbcfa-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="fbcfa-112">break (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="fbcfa-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)  
 [<span data-ttu-id="fbcfa-113">Instrucciones de salto</span><span class="sxs-lookup"><span data-stu-id="fbcfa-113">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
