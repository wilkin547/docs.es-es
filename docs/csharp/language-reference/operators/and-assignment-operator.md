---
title: Operador &amp;= (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: 092f46ddd8ca52e2d705200768c93a3473f1520f
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="8ddb3-102">Operador &amp;= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8ddb3-102">&amp;= Operator (C# Reference)</span></span>
<span data-ttu-id="8ddb3-103">El operador de asignación AND.</span><span class="sxs-lookup"><span data-stu-id="8ddb3-103">The AND assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ddb3-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8ddb3-104">Remarks</span></span>  
 <span data-ttu-id="8ddb3-105">Una expresión que use el operador de asignación `&=`, como</span><span class="sxs-lookup"><span data-stu-id="8ddb3-105">An expression using the `&=` assignment operator, such as</span></span>  
  
```csharp  
x &= y  
```  
  
 <span data-ttu-id="8ddb3-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="8ddb3-106">is equivalent to</span></span>  
  
```csharp  
x = x & y  
```  
  
 <span data-ttu-id="8ddb3-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="8ddb3-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="8ddb3-108">El [operador &](../../../csharp/language-reference/operators/and-operator.md) realiza una operación de AND bit a bit lógica en operandos enteros y una AND lógica en operandos `bool`.</span><span class="sxs-lookup"><span data-stu-id="8ddb3-108">The [& operator](../../../csharp/language-reference/operators/and-operator.md) performs a bitwise logical AND operation on integral operands and logical AND on `bool` operands.</span></span>  
  
 <span data-ttu-id="8ddb3-109">El operador `&=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador &](../../../csharp/language-reference/operators/and-operator.md) binario (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="8ddb3-109">The `&=` operator cannot be overloaded directly, but user-defined types can overload the binary [& operator](../../../csharp/language-reference/operators/and-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ddb3-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ddb3-110">Example</span></span>  
 [!code-csharp[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8ddb3-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ddb3-111">See Also</span></span>  
 [<span data-ttu-id="8ddb3-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="8ddb3-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8ddb3-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8ddb3-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8ddb3-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="8ddb3-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
