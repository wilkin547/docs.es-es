---
title: break (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b533d325be41683ed6f56e9e63b3c11ddde9cb17
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="break-c-reference"></a><span data-ttu-id="55768-102">break (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="55768-102">break (C# Reference)</span></span>
<span data-ttu-id="55768-103">La instrucción `break` finaliza la ejecución del bucle contenedor más próximo o de la instrucción [switch](../../../csharp/language-reference/keywords/switch.md) en la que aparezca.</span><span class="sxs-lookup"><span data-stu-id="55768-103">The `break` statement terminates the closest enclosing loop or [switch](../../../csharp/language-reference/keywords/switch.md) statement in which it appears.</span></span> <span data-ttu-id="55768-104">El control se pasa a la instrucción que hay a continuación de la instrucción finalizada, si existe.</span><span class="sxs-lookup"><span data-stu-id="55768-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55768-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="55768-105">Example</span></span>  
 <span data-ttu-id="55768-106">En este ejemplo, la instrucción condicional contiene un contador que se supone que cuenta de 1 a 100. Pero la instrucción `break` finaliza el bucle después de cuatro recuentos.</span><span class="sxs-lookup"><span data-stu-id="55768-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="55768-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="55768-107">Example</span></span>  
 <span data-ttu-id="55768-108">En este ejemplo, se usa la instrucción `break` para salir de un bucle anidado interno y devolver el control al bucle externo.</span><span class="sxs-lookup"><span data-stu-id="55768-108">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="55768-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="55768-109">Example</span></span>  
 <span data-ttu-id="55768-110">En este ejemplo se muestra el uso de `break` en una instrucción [switch](../../../csharp/language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="55768-110">This example demonstrates the use of `break` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_3.cs)]  
  
 <span data-ttu-id="55768-111">Si se escribió `4`, la salida será:</span><span class="sxs-lookup"><span data-stu-id="55768-111">If you entered `4`, the output would be:</span></span>  
  
```  
Enter your selection (1, 2, or 3): 4  
Sorry, invalid selection.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="55768-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="55768-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="55768-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="55768-113">See Also</span></span>  
 [<span data-ttu-id="55768-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="55768-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="55768-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="55768-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="55768-116">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="55768-116">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="55768-117">switch</span><span class="sxs-lookup"><span data-stu-id="55768-117">switch</span></span>](../../../csharp/language-reference/keywords/switch.md)  
 [<span data-ttu-id="55768-118">Instrucciones de salto</span><span class="sxs-lookup"><span data-stu-id="55768-118">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)  
 [<span data-ttu-id="55768-119">Instrucciones de iteración</span><span class="sxs-lookup"><span data-stu-id="55768-119">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
