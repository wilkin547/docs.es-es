---
title: Operador *= (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
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
ms.openlocfilehash: 2969ba3ce303da591353fd0114dccf752e63f2c3
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="d6206-102">Operador *= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d6206-102">*= Operator (C# Reference)</span></span>
<span data-ttu-id="d6206-103">El operador de asignación y multiplicación binaria.</span><span class="sxs-lookup"><span data-stu-id="d6206-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6206-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6206-104">Remarks</span></span>  
 <span data-ttu-id="d6206-105">Una expresión que use el operador de asignación `*=`, como</span><span class="sxs-lookup"><span data-stu-id="d6206-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```  
x *= y  
```  
  
 <span data-ttu-id="d6206-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="d6206-106">is equivalent to</span></span>  
  
```  
x = x * y  
```  
  
 <span data-ttu-id="d6206-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="d6206-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="d6206-108">El [operador *](../../../csharp/language-reference/operators/multiplication-operator.md) está predefinido en tipos numéricos para realizar la multiplicación.</span><span class="sxs-lookup"><span data-stu-id="d6206-108">The [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="d6206-109">El operador `*=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador *](../../../csharp/language-reference/operators/multiplication-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="d6206-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6206-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d6206-110">Example</span></span>  
 <span data-ttu-id="d6206-111">[!code-cs[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d6206-111">[!code-cs[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6206-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6206-112">See Also</span></span>  
 <span data-ttu-id="d6206-113">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d6206-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d6206-114">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d6206-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="d6206-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="d6206-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

