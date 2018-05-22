---
title: Operador += (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: bcd56acad8e2b08585e5ae60f1c3cf8183b5664a
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="9afcf-102">Operador += (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9afcf-102">+= Operator (C# Reference)</span></span>
<span data-ttu-id="9afcf-103">El operador de asignación y suma.</span><span class="sxs-lookup"><span data-stu-id="9afcf-103">The addition assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9afcf-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9afcf-104">Remarks</span></span>  
 <span data-ttu-id="9afcf-105">Una expresión que use el operador de asignación `+=`, como</span><span class="sxs-lookup"><span data-stu-id="9afcf-105">An expression using the `+=` assignment operator, such as</span></span>  
  
```csharp  
x += y  
```  
  
 <span data-ttu-id="9afcf-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="9afcf-106">is equivalent to</span></span>  
  
```csharp  
x = x + y  
```  
  
 <span data-ttu-id="9afcf-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="9afcf-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="9afcf-108">El significado del [operador +](../../../csharp/language-reference/operators/addition-operator.md) depende de los tipos de `x` y `y` (suma para los operandos numéricos, concatenación para los operandos de cadenas y así sucesivamente).</span><span class="sxs-lookup"><span data-stu-id="9afcf-108">The meaning of the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) depends on the types of `x` and `y` (addition for numeric operands, concatenation for string operands, and so forth).</span></span>  
  
 <span data-ttu-id="9afcf-109">El operador `+=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador +](../../../csharp/language-reference/operators/addition-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="9afcf-109">The `+=` operator cannot be overloaded directly, but user-defined types can overload the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="9afcf-110">El operador `+=` también se usa para especificar un método al que se llamará en respuesta a un evento; dichos métodos se denominan controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="9afcf-110">The `+=` operator is also used to specify a method that will be called in response to an event; such methods are called event handlers.</span></span> <span data-ttu-id="9afcf-111">El uso del operador `+=` en este contexto se conoce como *suscripción a un evento*.</span><span class="sxs-lookup"><span data-stu-id="9afcf-111">The use of the `+=` operator in this context is referred to as *subscribing to an event*.</span></span> <span data-ttu-id="9afcf-112">Para más información, vea [Cómo: Suscribir y cancelar la suscripción a eventos (Guía de programación de C#)](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) y [Delegados](../../../csharp/programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="9afcf-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9afcf-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9afcf-113">Example</span></span>  
 [!code-csharp[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="9afcf-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9afcf-114">See Also</span></span>  
 [<span data-ttu-id="9afcf-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9afcf-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9afcf-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9afcf-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9afcf-117">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="9afcf-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
