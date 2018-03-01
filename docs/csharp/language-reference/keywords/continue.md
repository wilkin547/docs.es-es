---
title: continue (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1ace2c90d03593b51b9ea461a47e122c5da1ab81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="continue-c-reference"></a><span data-ttu-id="5749e-102">continue (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5749e-102">continue (C# Reference)</span></span>
<span data-ttu-id="5749e-103">La instrucción `continue` transfiere el control a la siguiente iteración de la instrucción envolvente [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) o [foreach](../../../csharp/language-reference/keywords/foreach-in.md) en la que aparece.</span><span class="sxs-lookup"><span data-stu-id="5749e-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5749e-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5749e-104">Example</span></span>  
 <span data-ttu-id="5749e-105">En este ejemplo se inicializa un contador para contar del 1 al 10.</span><span class="sxs-lookup"><span data-stu-id="5749e-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="5749e-106">Si se usa la instrucción `continue` junto con la expresión `(i < 9)`, se omiten las instrucciones comprendidas entre `continue` y el final del cuerpo de `for`.</span><span class="sxs-lookup"><span data-stu-id="5749e-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/continue_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="5749e-107">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5749e-107">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5749e-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="5749e-108">See Also</span></span>  
 [<span data-ttu-id="5749e-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="5749e-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5749e-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5749e-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5749e-111">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="5749e-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="5749e-112">break (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="5749e-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)  
 [<span data-ttu-id="5749e-113">Instrucciones de salto</span><span class="sxs-lookup"><span data-stu-id="5749e-113">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
