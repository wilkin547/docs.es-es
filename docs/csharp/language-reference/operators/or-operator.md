---
title: Operador | (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: d95fe29aa7ffab9938e8edc57999445268fe41a8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085710"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6f49b-102">Operador | (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6f49b-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="6f49b-103">Los operadores binarios `|` están predefinidos para los tipos enteros y `bool`.</span><span class="sxs-lookup"><span data-stu-id="6f49b-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="6f49b-104">Para los tipos enteros, `|` calcula OR bit a bit de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="6f49b-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="6f49b-105">Para operandos `bool`, `|` calcula el OR lógico de sus operandos; es decir, el resultado es `false` si y solo si ambos operandos son `false`.</span><span class="sxs-lookup"><span data-stu-id="6f49b-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f49b-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6f49b-106">Remarks</span></span>  
 <span data-ttu-id="6f49b-107">El operador `|` binario evalúa ambos operadores con independencia del valor del primero, a diferencia del [operador OR condicional]     (conditional-or-operator.md) `||`.</span><span class="sxs-lookup"><span data-stu-id="6f49b-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator]     (conditional-or-operator.md) `||`.</span></span>
 
 <span data-ttu-id="6f49b-108">Los tipos definidos por el usuario pueden sobrecargar el operador `|` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="6f49b-108">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f49b-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f49b-109">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6f49b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f49b-110">See Also</span></span>

- [<span data-ttu-id="6f49b-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6f49b-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="6f49b-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6f49b-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="6f49b-113">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="6f49b-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
