---
title: Operador &amp;&amp; (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: 459b791fde3e4d3940dbd3d916f940e81f365da6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43388298"
---
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="7a4af-102">Operador &amp;&amp; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="7a4af-102">&amp;&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="7a4af-103">El operador AND condicional (`&&`) realiza una operación lógica AND con sus operandos `bool`, pero solo evalúa el segundo operando si es necesario.</span><span class="sxs-lookup"><span data-stu-id="7a4af-103">The conditional-AND operator (`&&`) performs a logical-AND of its `bool` operands, but only evaluates its second operand if necessary.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a4af-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7a4af-104">Remarks</span></span>  
 <span data-ttu-id="7a4af-105">La operación</span><span class="sxs-lookup"><span data-stu-id="7a4af-105">The operation</span></span>  
  
```csharp  
x && y  
```  
  
 <span data-ttu-id="7a4af-106">corresponde a la operación</span><span class="sxs-lookup"><span data-stu-id="7a4af-106">corresponds to the operation</span></span>  
  
```csharp  
x & y  
```  
  
 <span data-ttu-id="7a4af-107">salvo que si `x` es `false`, `y` no se evalúa porque el resultado de la operación AND es `false` independientemente del valor de `y`.</span><span class="sxs-lookup"><span data-stu-id="7a4af-107">except that if `x` is `false`, `y` is not evaluated, because the result of the AND operation is `false` no matter what the value of `y`  is.</span></span> <span data-ttu-id="7a4af-108">Esto se conoce como evaluación "de cortocircuito".</span><span class="sxs-lookup"><span data-stu-id="7a4af-108">This is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="7a4af-109">El operador AND condicional no puede sobrecargarse, pero las sobrecargas de los operadores lógicos regulares y los operadores [true](../../../csharp/language-reference/keywords/true.md) y [false](../../../csharp/language-reference/keywords/false.md) se consideran también, con algunas restricciones, sobrecargas de los operadores lógicos condicionales.</span><span class="sxs-lookup"><span data-stu-id="7a4af-109">The conditional-AND operator cannot be overloaded, but overloads of the regular logical operators and operators [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) are, with certain restrictions, also considered overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a4af-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a4af-110">Example</span></span>  
 <span data-ttu-id="7a4af-111">En el ejemplo siguiente, la expresión condicional de la segunda instrucción `if` evalúa solo el primer operando porque este devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="7a4af-111">In the following example, the conditional expression in the second `if` statement evaluates only the first operand because the operand returns `false`.</span></span>  
  
 [!code-csharp[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="7a4af-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="7a4af-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7a4af-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a4af-113">See Also</span></span>

- [<span data-ttu-id="7a4af-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="7a4af-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="7a4af-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7a4af-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="7a4af-116">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="7a4af-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
