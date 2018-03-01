---
title: Operador *= (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dc2201f78e1e05bd0ccdea04522896c00294bdd6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="9c3a4-102">Operador \*= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9c3a4-102">\*= Operator (C# Reference)</span></span>
<span data-ttu-id="9c3a4-103">El operador de asignación y multiplicación binaria.</span><span class="sxs-lookup"><span data-stu-id="9c3a4-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c3a4-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9c3a4-104">Remarks</span></span>  
 <span data-ttu-id="9c3a4-105">Una expresión que use el operador de asignación `*=`, como</span><span class="sxs-lookup"><span data-stu-id="9c3a4-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```  
x *= y  
```  
  
 <span data-ttu-id="9c3a4-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="9c3a4-106">is equivalent to</span></span>  
  
```  
x = x * y  
```  
  
 <span data-ttu-id="9c3a4-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="9c3a4-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="9c3a4-108">El [operador \*](../../../csharp/language-reference/operators/multiplication-operator.md) está predefinido en tipos numéricos para realizar la multiplicación.</span><span class="sxs-lookup"><span data-stu-id="9c3a4-108">The [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="9c3a4-109">El operador `*=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador *](../../../csharp/language-reference/operators/multiplication-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="9c3a4-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c3a4-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c3a4-110">Example</span></span>  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="9c3a4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c3a4-111">See Also</span></span>  
 [<span data-ttu-id="9c3a4-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9c3a4-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9c3a4-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9c3a4-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9c3a4-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="9c3a4-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
