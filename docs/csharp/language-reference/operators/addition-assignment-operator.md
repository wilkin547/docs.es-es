---
title: Operador += (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
caps.latest.revision: 20
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
ms.openlocfilehash: 42567b2d8e7d9b694ce64ccb88e0fd4bfe05b020
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="b362b-102">Operador += (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b362b-102">+= Operator (C# Reference)</span></span>
<span data-ttu-id="b362b-103">El operador de asignación y suma.</span><span class="sxs-lookup"><span data-stu-id="b362b-103">The addition assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b362b-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b362b-104">Remarks</span></span>  
 <span data-ttu-id="b362b-105">Una expresión que use el operador de asignación `+=`, como</span><span class="sxs-lookup"><span data-stu-id="b362b-105">An expression using the `+=` assignment operator, such as</span></span>  
  
```  
x += y  
```  
  
 <span data-ttu-id="b362b-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="b362b-106">is equivalent to</span></span>  
  
```  
x = x + y  
```  
  
 <span data-ttu-id="b362b-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="b362b-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="b362b-108">El significado del [operador +](../../../csharp/language-reference/operators/addition-operator.md) depende de los tipos de `x` y `y` (suma para los operandos numéricos, concatenación para los operandos de cadenas y así sucesivamente).</span><span class="sxs-lookup"><span data-stu-id="b362b-108">The meaning of the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) depends on the types of `x` and `y` (addition for numeric operands, concatenation for string operands, and so forth).</span></span>  
  
 <span data-ttu-id="b362b-109">El operador `+=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador +](../../../csharp/language-reference/operators/addition-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="b362b-109">The `+=` operator cannot be overloaded directly, but user-defined types can overload the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="b362b-110">El operador `+=` también se usa para especificar un método al que se llamará en respuesta a un evento; dichos métodos se denominan controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="b362b-110">The `+=` operator is also used to specify a method that will be called in response to an event; such methods are called event handlers.</span></span> <span data-ttu-id="b362b-111">El uso del operador `+=` en este contexto se conoce como *suscripción a un evento*.</span><span class="sxs-lookup"><span data-stu-id="b362b-111">The use of the `+=` operator in this context is referred to as *subscribing to an event*.</span></span> <span data-ttu-id="b362b-112">Para obtener más información, vea [Cómo: Suscribir y cancelar la suscripción a eventos (Guía de programación de C#)](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)</span><span class="sxs-lookup"><span data-stu-id="b362b-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span> <span data-ttu-id="b362b-113">y [Delegados](../../../csharp/programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="b362b-113">and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b362b-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b362b-114">Example</span></span>  
 <span data-ttu-id="b362b-115">[!code-cs[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b362b-115">[!code-cs[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b362b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b362b-116">See Also</span></span>  
 <span data-ttu-id="b362b-117">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b362b-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b362b-118">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b362b-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b362b-119">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="b362b-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

