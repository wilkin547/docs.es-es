---
title: '%= (operador) (Referencia de C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- modulus assignment operator (=%) [C#]
- '%= assignment operator (modulus assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
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
ms.openlocfilehash: 48484a0593102c92304803e5c0697501b0e26e0e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="72b91-102">%= (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="72b91-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="72b91-103">El operador de asignación y resto.</span><span class="sxs-lookup"><span data-stu-id="72b91-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72b91-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="72b91-104">Remarks</span></span>  
 <span data-ttu-id="72b91-105">Una expresión que use el operador de asignación `%=`, como</span><span class="sxs-lookup"><span data-stu-id="72b91-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```  
x %= y  
```  
  
 <span data-ttu-id="72b91-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="72b91-106">is equivalent to</span></span>  
  
```  
x = x % y  
```  
  
 <span data-ttu-id="72b91-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="72b91-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="72b91-108">El [operador %](../../../csharp/language-reference/operators/modulus-operator.md) está predefinido en tipos numéricos para calcular el resto después de la división.</span><span class="sxs-lookup"><span data-stu-id="72b91-108">The [% operator](../../../csharp/language-reference/operators/modulus-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="72b91-109">El operador `%=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador %](../../../csharp/language-reference/operators/modulus-operator.md) (vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="72b91-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/modulus-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="72b91-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="72b91-110">Example</span></span>  
 <span data-ttu-id="72b91-111">[!code-cs[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="72b91-111">[!code-cs[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72b91-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="72b91-112">See Also</span></span>  
 <span data-ttu-id="72b91-113">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="72b91-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="72b91-114">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="72b91-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="72b91-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="72b91-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

