---
title: '%= (operador) (Referencia de C#)'
ms.date: 04/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: 009c162b13fab05ba349d0535fe8dfae206502f3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43399496"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ba5bb-102">%= (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ba5bb-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="ba5bb-103">El operador de asignación y resto.</span><span class="sxs-lookup"><span data-stu-id="ba5bb-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba5bb-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ba5bb-104">Remarks</span></span>  
 <span data-ttu-id="ba5bb-105">Una expresión que use el operador de asignación `%=`, como</span><span class="sxs-lookup"><span data-stu-id="ba5bb-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```csharp  
x %= y  
```  
  
 <span data-ttu-id="ba5bb-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="ba5bb-106">is equivalent to</span></span>  
  
```csharp  
x = x % y  
```  
  
 <span data-ttu-id="ba5bb-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="ba5bb-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="ba5bb-108">El [operador %](../../../csharp/language-reference/operators/remainder-operator.md) está predefinido en tipos numéricos para calcular el resto después de la división.</span><span class="sxs-lookup"><span data-stu-id="ba5bb-108">The [% operator](../../../csharp/language-reference/operators/remainder-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="ba5bb-109">El operador `%=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador %](../../../csharp/language-reference/operators/remainder-operator.md) (vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="ba5bb-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/remainder-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba5bb-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba5bb-110">Example</span></span>  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ba5bb-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba5bb-111">See Also</span></span>

- [<span data-ttu-id="ba5bb-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="ba5bb-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ba5bb-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ba5bb-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ba5bb-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="ba5bb-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
