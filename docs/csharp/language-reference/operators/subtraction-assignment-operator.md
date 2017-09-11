---
title: -= Operador (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- -=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d7f26ae1fce54eb0d03a314a83ce523baeb3f348
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="--operator-c-reference"></a><span data-ttu-id="b83df-102">-= Operador (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b83df-102">-= Operator (C# Reference)</span></span>
<span data-ttu-id="b83df-103">Operador de asignación y resta.</span><span class="sxs-lookup"><span data-stu-id="b83df-103">The subtraction assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b83df-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b83df-104">Remarks</span></span>  
 <span data-ttu-id="b83df-105">Una expresión que use el operador de asignación `-=`, como</span><span class="sxs-lookup"><span data-stu-id="b83df-105">An expression using the `-=` assignment operator, such as</span></span>  
  
```  
x -= y  
```  
  
 <span data-ttu-id="b83df-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="b83df-106">is equivalent to</span></span>  
  
```  
x = x - y  
```  
  
 <span data-ttu-id="b83df-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="b83df-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="b83df-108">El significado del [operador -](../../../csharp/language-reference/operators/subtraction-operator.md) depende de los tipos de `x` e `y` (resta de operandos numéricos, eliminación de delegados en operandos de delegado, etc.).</span><span class="sxs-lookup"><span data-stu-id="b83df-108">The meaning of the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) is dependent on the types of `x` and `y` (subtraction for numeric operands, delegate removal for delegate operands, and so forth).</span></span>  
  
 <span data-ttu-id="b83df-109">El operador `-=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador -](../../../csharp/language-reference/operators/subtraction-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md) [Operador]).</span><span class="sxs-lookup"><span data-stu-id="b83df-109">The `-=` operator cannot be overloaded directly, but user-defined types can overload the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="b83df-110">El operador -= también se usa en C# para cancelar la suscripción a un evento.</span><span class="sxs-lookup"><span data-stu-id="b83df-110">The -= operator is also used in C# to unsubscribe from an event.</span></span> <span data-ttu-id="b83df-111">Para obtener más información, vea [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) (Cómo: Suscribir y cancelar la suscripción a eventos [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="b83df-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b83df-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b83df-112">Example</span></span>  
 <span data-ttu-id="b83df-113">[!code-cs[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b83df-113">[!code-cs[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b83df-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b83df-114">See Also</span></span>  
 <span data-ttu-id="b83df-115">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b83df-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b83df-116">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b83df-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b83df-117">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="b83df-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

