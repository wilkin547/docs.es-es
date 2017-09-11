---
title: Operador &amp;&amp; (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&&_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
caps.latest.revision: 18
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
ms.openlocfilehash: 1da61947cbc85e5b3045513e99e013d1e4fae4b3
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="43649-102">Operador &amp;&amp; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="43649-102">&amp;&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="43649-103">El operador AND condicional (`&&`) realiza una operación lógica AND con sus operandos `bool`, pero solo evalúa el segundo operando si es necesario.</span><span class="sxs-lookup"><span data-stu-id="43649-103">The conditional-AND operator (`&&`) performs a logical-AND of its `bool` operands, but only evaluates its second operand if necessary.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43649-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43649-104">Remarks</span></span>  
 <span data-ttu-id="43649-105">La operación</span><span class="sxs-lookup"><span data-stu-id="43649-105">The operation</span></span>  
  
```  
x && y  
```  
  
 <span data-ttu-id="43649-106">corresponde a la operación</span><span class="sxs-lookup"><span data-stu-id="43649-106">corresponds to the operation</span></span>  
  
```  
x & y  
```  
  
 <span data-ttu-id="43649-107">salvo que si `x` es `false`, `y` no se evalúa porque el resultado de la operación AND es `false` independientemente del valor de `y`.</span><span class="sxs-lookup"><span data-stu-id="43649-107">except that if `x` is `false`, `y` is not evaluated, because the result of the AND operation is `false` no matter what the value of `y`  is.</span></span> <span data-ttu-id="43649-108">Esto se conoce como evaluación "de cortocircuito".</span><span class="sxs-lookup"><span data-stu-id="43649-108">This is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="43649-109">El operador AND condicional no puede sobrecargarse, pero las sobrecargas de los operadores lógicos regulares y los operadores [true](../../../csharp/language-reference/keywords/true.md) y [false](../../../csharp/language-reference/keywords/false.md) se consideran también, con algunas restricciones, sobrecargas de los operadores lógicos condicionales.</span><span class="sxs-lookup"><span data-stu-id="43649-109">The conditional-AND operator cannot be overloaded, but overloads of the regular logical operators and operators [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) are, with certain restrictions, also considered overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43649-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43649-110">Example</span></span>  
 <span data-ttu-id="43649-111">En el ejemplo siguiente, la expresión condicional de la segunda instrucción `if` evalúa solo el primer operando porque este devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="43649-111">In the following example, the conditional expression in the second `if` statement evaluates only the first operand because the operand returns `false`.</span></span>  
  
 <span data-ttu-id="43649-112">[!code-cs[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="43649-112">[!code-cs[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="43649-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="43649-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="43649-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="43649-114">See Also</span></span>  
 <span data-ttu-id="43649-115">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="43649-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="43649-116">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="43649-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="43649-117">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="43649-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

