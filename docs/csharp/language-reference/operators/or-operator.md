---
title: Operador | (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 374adc30e6937a68d67bfae152f2546c854b829b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a06b4-102">Operador | (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a06b4-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="a06b4-103">Los operadores binarios `|` están predefinidos para los tipos enteros y `bool`.</span><span class="sxs-lookup"><span data-stu-id="a06b4-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="a06b4-104">Para los tipos enteros, `|` calcula OR bit a bit de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="a06b4-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="a06b4-105">Para operandos `bool`, `|` calcula el OR lógico de sus operandos; es decir, el resultado es `false` si y solo si ambos operandos son `false`.</span><span class="sxs-lookup"><span data-stu-id="a06b4-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a06b4-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a06b4-106">Remarks</span></span>  
 <span data-ttu-id="a06b4-107">Los tipos definidos por el usuario pueden sobrecargar el operador `|` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="a06b4-107">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a06b4-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a06b4-108">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a06b4-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="a06b4-109">See Also</span></span>  
 [<span data-ttu-id="a06b4-110">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a06b4-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a06b4-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a06b4-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a06b4-112">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="a06b4-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
