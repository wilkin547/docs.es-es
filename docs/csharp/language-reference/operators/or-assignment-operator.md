---
title: '|= (operador) (Referencia de C#)'
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: 18246d013275c8d6c8ad7e05409387457afc3442
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6b3e0-102">|= (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6b3e0-102">|= Operator (C# Reference)</span></span>
<span data-ttu-id="6b3e0-103">El operador de asignación OR.</span><span class="sxs-lookup"><span data-stu-id="6b3e0-103">The OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b3e0-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b3e0-104">Remarks</span></span>  
 <span data-ttu-id="6b3e0-105">Una expresión que use el operador de asignación `|=`, como</span><span class="sxs-lookup"><span data-stu-id="6b3e0-105">An expression using the `|=` assignment operator, such as</span></span>  
  
```csharp  
x |= y  
```  
  
 <span data-ttu-id="6b3e0-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="6b3e0-106">is equivalent to</span></span>  
  
```csharp  
x = x | y  
```  
  
 <span data-ttu-id="6b3e0-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="6b3e0-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="6b3e0-108">El [operador &#124;](../../../csharp/language-reference/operators/or-operator.md) realiza una operación lógica OR bit a bit sobre operandos integrales y una operación lógica OR sobre operandos de tipo bool.</span><span class="sxs-lookup"><span data-stu-id="6b3e0-108">The [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>  
  
 <span data-ttu-id="6b3e0-109">El operador `|=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador &#124;](../../../csharp/language-reference/operators/or-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="6b3e0-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b3e0-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b3e0-110">Example</span></span>  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6b3e0-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b3e0-111">See Also</span></span>  
 [<span data-ttu-id="6b3e0-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6b3e0-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6b3e0-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6b3e0-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6b3e0-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="6b3e0-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
