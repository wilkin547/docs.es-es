---
title: '%= (operador) (Referencia de C#)'
ms.date: 04/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: aadcb5ef969ff408cc1e738fc0f5b67152fdc78b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171972"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="084cf-102">%= (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="084cf-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="084cf-103">El operador de asignación y resto.</span><span class="sxs-lookup"><span data-stu-id="084cf-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="084cf-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="084cf-104">Remarks</span></span>  
 <span data-ttu-id="084cf-105">Una expresión que use el operador de asignación `%=`, como</span><span class="sxs-lookup"><span data-stu-id="084cf-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```csharp  
x %= y  
```  
  
 <span data-ttu-id="084cf-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="084cf-106">is equivalent to</span></span>  
  
```csharp  
x = x % y  
```  
  
 <span data-ttu-id="084cf-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="084cf-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="084cf-108">El [operador %](../../../csharp/language-reference/operators/remainder-operator.md) está predefinido en tipos numéricos para calcular el resto después de la división.</span><span class="sxs-lookup"><span data-stu-id="084cf-108">The [% operator](../../../csharp/language-reference/operators/remainder-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="084cf-109">El operador `%=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador %](../../../csharp/language-reference/operators/remainder-operator.md) (vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="084cf-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/remainder-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="084cf-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="084cf-110">Example</span></span>  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="084cf-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="084cf-111">See Also</span></span>  
 [<span data-ttu-id="084cf-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="084cf-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="084cf-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="084cf-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="084cf-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="084cf-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
