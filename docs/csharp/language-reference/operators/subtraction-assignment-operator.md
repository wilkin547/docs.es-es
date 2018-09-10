---
title: -= Operador (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: 7cade0811536d836480f80a56cf8c4d09e089a0b
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43773996"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="3a446-102">-= Operador (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="3a446-102">-= Operator (C# Reference)</span></span>
<span data-ttu-id="3a446-103">Operador de asignación y resta.</span><span class="sxs-lookup"><span data-stu-id="3a446-103">The subtraction assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a446-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a446-104">Remarks</span></span>  
 <span data-ttu-id="3a446-105">Una expresión que use el operador de asignación `-=`, como</span><span class="sxs-lookup"><span data-stu-id="3a446-105">An expression using the `-=` assignment operator, such as</span></span>  
  
```csharp  
x -= y  
```  
  
 <span data-ttu-id="3a446-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="3a446-106">is equivalent to</span></span>  
  
```csharp  
x = x - y  
```  
  
 <span data-ttu-id="3a446-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="3a446-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="3a446-108">El significado del [operador -](../../../csharp/language-reference/operators/subtraction-operator.md) depende de los tipos de `x` e `y` (resta de operandos numéricos, eliminación de delegados en operandos de delegado, etc.).</span><span class="sxs-lookup"><span data-stu-id="3a446-108">The meaning of the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) is dependent on the types of `x` and `y` (subtraction for numeric operands, delegate removal for delegate operands, and so forth).</span></span>  
  
 <span data-ttu-id="3a446-109">El operador `-=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador -](../../../csharp/language-reference/operators/subtraction-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md) [Operador]).</span><span class="sxs-lookup"><span data-stu-id="3a446-109">The `-=` operator cannot be overloaded directly, but user-defined types can overload the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="3a446-110">El operador -= también se usa en C# para cancelar la suscripción a un evento.</span><span class="sxs-lookup"><span data-stu-id="3a446-110">The -= operator is also used in C# to unsubscribe from an event.</span></span> <span data-ttu-id="3a446-111">Para obtener más información, vea [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) (Cómo: Suscribir y cancelar la suscripción a eventos [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="3a446-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a446-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a446-112">Example</span></span>  
 [!code-csharp[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="3a446-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a446-113">See Also</span></span>

- [<span data-ttu-id="3a446-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="3a446-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="3a446-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3a446-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3a446-116">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="3a446-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
