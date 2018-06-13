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
ms.openlocfilehash: 7b62af53f0d8b7cba29f4496887717f1726eabf9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33265692"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="5fb12-102">Operador | (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5fb12-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="5fb12-103">Los operadores binarios `|` están predefinidos para los tipos enteros y `bool`.</span><span class="sxs-lookup"><span data-stu-id="5fb12-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="5fb12-104">Para los tipos enteros, `|` calcula OR bit a bit de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="5fb12-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="5fb12-105">Para operandos `bool`, `|` calcula el OR lógico de sus operandos; es decir, el resultado es `false` si y solo si ambos operandos son `false`.</span><span class="sxs-lookup"><span data-stu-id="5fb12-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fb12-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5fb12-106">Remarks</span></span>  
 <span data-ttu-id="5fb12-107">Los tipos definidos por el usuario pueden sobrecargar el operador `|` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="5fb12-107">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fb12-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5fb12-108">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="5fb12-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fb12-109">See Also</span></span>  
 [<span data-ttu-id="5fb12-110">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="5fb12-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5fb12-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5fb12-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5fb12-112">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="5fb12-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
