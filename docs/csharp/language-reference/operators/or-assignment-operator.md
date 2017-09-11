---
title: '|= (operador) (Referencia de C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '|=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
caps.latest.revision: 16
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
ms.openlocfilehash: f1c0a92414739efc2ab091871e80852737fdf931
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="0d1c8-102">|= (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0d1c8-102">|= Operator (C# Reference)</span></span>
<span data-ttu-id="0d1c8-103">El operador de asignación OR.</span><span class="sxs-lookup"><span data-stu-id="0d1c8-103">The OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d1c8-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0d1c8-104">Remarks</span></span>  
 <span data-ttu-id="0d1c8-105">Una expresión que use el operador de asignación `|=`, como</span><span class="sxs-lookup"><span data-stu-id="0d1c8-105">An expression using the `|=` assignment operator, such as</span></span>  
  
```  
x |= y  
```  
  
 <span data-ttu-id="0d1c8-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="0d1c8-106">is equivalent to</span></span>  
  
```  
x = x | y  
```  
  
 <span data-ttu-id="0d1c8-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="0d1c8-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="0d1c8-108">El [operador &#124;](../../../csharp/language-reference/operators/or-operator.md) realiza una operación lógica OR bit a bit sobre operandos integrales y una operación lógica OR sobre operandos de tipo bool.</span><span class="sxs-lookup"><span data-stu-id="0d1c8-108">The [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>  
  
 <span data-ttu-id="0d1c8-109">El operador `|=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador &#124;](../../../csharp/language-reference/operators/or-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="0d1c8-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d1c8-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d1c8-110">Example</span></span>  
 <span data-ttu-id="0d1c8-111">[!code-cs[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0d1c8-111">[!code-cs[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d1c8-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d1c8-112">See Also</span></span>  
 <span data-ttu-id="0d1c8-113">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0d1c8-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0d1c8-114">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0d1c8-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="0d1c8-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="0d1c8-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

