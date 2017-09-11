---
title: Operador | (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '|_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
caps.latest.revision: 15
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
ms.openlocfilehash: 7524e246df35154ac04e46f2b43edded71be34b1
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="8552f-102">Operador | (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8552f-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="8552f-103">Los operadores `|` binarios están predefinidos para los tipos enteros y `bool`.</span><span class="sxs-lookup"><span data-stu-id="8552f-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="8552f-104">Para los tipos enteros, `|` calcula OR bit a bit de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="8552f-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="8552f-105">Para operandos `bool`, `|` calcula el OR lógico de sus operandos; es decir, el resultado es `false` si y solo si ambos operandos son `false`.</span><span class="sxs-lookup"><span data-stu-id="8552f-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8552f-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8552f-106">Remarks</span></span>  
 <span data-ttu-id="8552f-107">Los tipos definidos por el usuario pueden sobrecargar el operador `|` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="8552f-107">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8552f-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8552f-108">Example</span></span>  
 <span data-ttu-id="8552f-109">[!code-cs[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8552f-109">[!code-cs[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8552f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8552f-110">See Also</span></span>  
 <span data-ttu-id="8552f-111">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="8552f-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="8552f-112">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8552f-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="8552f-113">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="8552f-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

