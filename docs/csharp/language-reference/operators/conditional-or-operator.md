---
title: Operador || (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: d22e57d097edb0fe52b604e9c6431e167c410f0b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="745ff-102">Operador || (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="745ff-102">|| Operator (C# Reference)</span></span>
<span data-ttu-id="745ff-103">El operador OR condicional (`||`) realiza una operación OR lógica de sus operandos `bool`.</span><span class="sxs-lookup"><span data-stu-id="745ff-103">The conditional-OR operator (`||`) performs a logical-OR of its `bool` operands.</span></span> <span data-ttu-id="745ff-104">Si el primer operando se evalúa como `true`, no se evalúa el segundo operando.</span><span class="sxs-lookup"><span data-stu-id="745ff-104">If the first operand evaluates to `true`, the second operand isn't evaluated.</span></span> <span data-ttu-id="745ff-105">Si el primer operando se evalúa como `false`, el segundo operador determina si la expresión OR completa se evalúa como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="745ff-105">If the first operand evaluates to `false`, the second operator determines whether the OR expression as a whole evaluates to `true` or `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="745ff-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="745ff-106">Remarks</span></span>  
 <span data-ttu-id="745ff-107">La operación</span><span class="sxs-lookup"><span data-stu-id="745ff-107">The operation</span></span>  
  
```csharp  
x || y  
```  
  
 <span data-ttu-id="745ff-108">corresponde a la operación</span><span class="sxs-lookup"><span data-stu-id="745ff-108">corresponds to the operation</span></span>  
  
```csharp  
x | y  
```  
  
 <span data-ttu-id="745ff-109">salvo que si `x` es `true`, `y` no se evalúa porque la operación OR es `true` independientemente del valor de `y`.</span><span class="sxs-lookup"><span data-stu-id="745ff-109">except that if `x` is `true`, `y` is not evaluated because the OR operation is `true` regardless of the value of `y`.</span></span> <span data-ttu-id="745ff-110">Este concepto se conoce como evaluación "de cortocircuito".</span><span class="sxs-lookup"><span data-stu-id="745ff-110">This concept is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="745ff-111">El operador OR condicional no puede sobrecargarse, pero las sobrecargas de los operadores lógicos regulares y los operadores [true](../../../csharp/language-reference/keywords/true.md) y [false](../../../csharp/language-reference/keywords/false.md) se consideran también, con algunas restricciones, sobrecargas de los operadores lógicos condicionales.</span><span class="sxs-lookup"><span data-stu-id="745ff-111">The conditional-OR operator cannot be overloaded, but overloads of the regular logical operators and the [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) operators are, with certain restrictions, also considered to be overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="745ff-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="745ff-112">Example</span></span>  
 <span data-ttu-id="745ff-113">En los ejemplos siguientes, la expresión que usa `||` evalúa solo el primer operando.</span><span class="sxs-lookup"><span data-stu-id="745ff-113">In the following examples, the expression that uses `||` evaluates only the first operand.</span></span> <span data-ttu-id="745ff-114">La expresión que usa `|` evalúa ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="745ff-114">The expression that uses `|` evaluates both operands.</span></span> <span data-ttu-id="745ff-115">En el segundo ejemplo, se produce una excepción en tiempo de ejecución si se evalúan ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="745ff-115">In the second example, a run-time exception occurs if both operands are evaluated.</span></span>  
  
 [!code-csharp[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="745ff-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="745ff-116">See Also</span></span>  
 [<span data-ttu-id="745ff-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="745ff-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="745ff-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="745ff-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="745ff-119">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="745ff-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
