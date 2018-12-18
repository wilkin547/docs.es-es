---
title: 'Operador -=: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: dc3cedafc57e1c6ec9bc34ca4e2c2aa9c604848c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239591"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="6edc1-102">-= Operador (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6edc1-102">-= Operator (C# Reference)</span></span>
<span data-ttu-id="6edc1-103">Operador de asignación y resta.</span><span class="sxs-lookup"><span data-stu-id="6edc1-103">The subtraction assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6edc1-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6edc1-104">Remarks</span></span>  
 <span data-ttu-id="6edc1-105">Una expresión que use el operador de asignación `-=`, como</span><span class="sxs-lookup"><span data-stu-id="6edc1-105">An expression using the `-=` assignment operator, such as</span></span>  
  
```csharp  
x -= y  
```  
  
 <span data-ttu-id="6edc1-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="6edc1-106">is equivalent to</span></span>  
  
```csharp  
x = x - y  
```  
  
 <span data-ttu-id="6edc1-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="6edc1-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="6edc1-108">El significado del [operador -](../../../csharp/language-reference/operators/subtraction-operator.md) depende de los tipos de `x` e `y` (resta de operandos numéricos, eliminación de delegados en operandos de delegado, etc.).</span><span class="sxs-lookup"><span data-stu-id="6edc1-108">The meaning of the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) is dependent on the types of `x` and `y` (subtraction for numeric operands, delegate removal for delegate operands, and so forth).</span></span>  
  
 <span data-ttu-id="6edc1-109">El operador `-=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador -](../../../csharp/language-reference/operators/subtraction-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md) [Operador]).</span><span class="sxs-lookup"><span data-stu-id="6edc1-109">The `-=` operator cannot be overloaded directly, but user-defined types can overload the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="6edc1-110">El operador -= también se usa en C# para cancelar la suscripción a un evento.</span><span class="sxs-lookup"><span data-stu-id="6edc1-110">The -= operator is also used in C# to unsubscribe from an event.</span></span> <span data-ttu-id="6edc1-111">Para obtener más información, vea [Cómo: Suscribir y cancelar la suscripción a eventos](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)</span><span class="sxs-lookup"><span data-stu-id="6edc1-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6edc1-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6edc1-112">Example</span></span>  
 [!code-csharp[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6edc1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6edc1-113">See Also</span></span>

- [<span data-ttu-id="6edc1-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6edc1-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="6edc1-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6edc1-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="6edc1-116">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="6edc1-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
