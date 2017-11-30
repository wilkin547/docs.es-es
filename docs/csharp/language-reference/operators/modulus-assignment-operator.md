---
title: '%= (operador) (Referencia de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '%=_CSharpKeyword'
helpviewer_keywords:
- modulus assignment operator (=%) [C#]
- '%= assignment operator (modulus assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9bafd0078153e29fbf923948d9b380d4795c3d35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="706b3-102">%= (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="706b3-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="706b3-103">El operador de asignación y resto.</span><span class="sxs-lookup"><span data-stu-id="706b3-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="706b3-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="706b3-104">Remarks</span></span>  
 <span data-ttu-id="706b3-105">Una expresión que use el operador de asignación `%=`, como</span><span class="sxs-lookup"><span data-stu-id="706b3-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```  
x %= y  
```  
  
 <span data-ttu-id="706b3-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="706b3-106">is equivalent to</span></span>  
  
```  
x = x % y  
```  
  
 <span data-ttu-id="706b3-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="706b3-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="706b3-108">El [operador %](../../../csharp/language-reference/operators/modulus-operator.md) está predefinido en tipos numéricos para calcular el resto después de la división.</span><span class="sxs-lookup"><span data-stu-id="706b3-108">The [% operator](../../../csharp/language-reference/operators/modulus-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="706b3-109">El operador `%=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador %](../../../csharp/language-reference/operators/modulus-operator.md) (vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="706b3-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/modulus-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="706b3-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="706b3-110">Example</span></span>  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="706b3-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="706b3-111">See Also</span></span>  
 [<span data-ttu-id="706b3-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="706b3-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="706b3-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="706b3-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="706b3-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="706b3-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
