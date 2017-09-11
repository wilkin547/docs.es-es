---
title: Operador &gt;&gt;= (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>>=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
caps.latest.revision: 14
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
ms.openlocfilehash: 64f387e475681ffc76f113435ba090b40780dda3
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="ece01-102">Operador &gt;&gt;= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ece01-102">&gt;&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="ece01-103">Operador de asignación de desplazamiento a la derecha.</span><span class="sxs-lookup"><span data-stu-id="ece01-103">The right-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ece01-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ece01-104">Remarks</span></span>  
 <span data-ttu-id="ece01-105">Una expresión con el formato</span><span class="sxs-lookup"><span data-stu-id="ece01-105">An expression of the form</span></span>  
  
```  
x >>= y  
```  
  
 <span data-ttu-id="ece01-106">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="ece01-106">is evaluated as</span></span>  
  
```  
x = x >> y  
```  
  
 <span data-ttu-id="ece01-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="ece01-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="ece01-108">El [operador >>](../../../csharp/language-reference/operators/right-shift-operator.md) desplaza `x` hacia la derecha una cantidad especificada por `y`.</span><span class="sxs-lookup"><span data-stu-id="ece01-108">The [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>  
  
 <span data-ttu-id="ece01-109">El operador >>= no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador >>](../../../csharp/language-reference/operators/right-shift-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="ece01-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ece01-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ece01-110">Example</span></span>  
 <span data-ttu-id="ece01-111">[!code-cs[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ece01-111">[!code-cs[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ece01-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ece01-112">See Also</span></span>  
 <span data-ttu-id="ece01-113">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ece01-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ece01-114">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ece01-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="ece01-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="ece01-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

