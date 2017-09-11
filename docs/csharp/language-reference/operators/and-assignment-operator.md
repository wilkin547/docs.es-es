---
title: Operador &amp;= (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
caps.latest.revision: 15
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
ms.openlocfilehash: 6dec8de5077c07150ea37b88979e7b59b231d610
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="92735-102">Operador &amp;= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="92735-102">&amp;= Operator (C# Reference)</span></span>
<span data-ttu-id="92735-103">El operador de asignación AND.</span><span class="sxs-lookup"><span data-stu-id="92735-103">The AND assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92735-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="92735-104">Remarks</span></span>  
 <span data-ttu-id="92735-105">Una expresión que use el operador de asignación `&=`, como</span><span class="sxs-lookup"><span data-stu-id="92735-105">An expression using the `&=` assignment operator, such as</span></span>  
  
```  
x &= y  
```  
  
 <span data-ttu-id="92735-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="92735-106">is equivalent to</span></span>  
  
```  
x = x & y  
```  
  
 <span data-ttu-id="92735-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="92735-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="92735-108">El [operador &](../../../csharp/language-reference/operators/and-operator.md) realiza una operación de AND bit a bit lógica en operandos enteros y una AND lógica en operandos `bool`.</span><span class="sxs-lookup"><span data-stu-id="92735-108">The [& operator](../../../csharp/language-reference/operators/and-operator.md) performs a bitwise logical AND operation on integral operands and logical AND on `bool` operands.</span></span>  
  
 <span data-ttu-id="92735-109">El operador `&=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador &](../../../csharp/language-reference/operators/and-operator.md) binario (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="92735-109">The `&=` operator cannot be overloaded directly, but user-defined types can overload the binary [& operator](../../../csharp/language-reference/operators/and-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="92735-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="92735-110">Example</span></span>  
 <span data-ttu-id="92735-111">[!code-cs[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="92735-111">[!code-cs[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92735-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="92735-112">See Also</span></span>  
 <span data-ttu-id="92735-113">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="92735-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="92735-114">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="92735-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="92735-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="92735-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

