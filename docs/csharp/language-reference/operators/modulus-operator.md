---
title: Operador % (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- modulus operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
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
ms.openlocfilehash: 658b04f4bee952a20a7b0a740aa931fe4fad9cdf
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="32ad0-102">Operador % (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="32ad0-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="32ad0-103">El operador `%` calcula el resto después de dividir el primer operando por el segundo.</span><span class="sxs-lookup"><span data-stu-id="32ad0-103">The `%` operator computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="32ad0-104">Todos los tipos numéricos tienen operadores restantes predefinidos.</span><span class="sxs-lookup"><span data-stu-id="32ad0-104">All numeric types have predefined remainder operators.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32ad0-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="32ad0-105">Remarks</span></span>  
 <span data-ttu-id="32ad0-106">Los tipos definidos por el usuario pueden sobrecargar el operador `%` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="32ad0-106">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="32ad0-107">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="32ad0-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32ad0-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="32ad0-108">Example</span></span>  
 <span data-ttu-id="32ad0-109">[!code-cs[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="32ad0-109">[!code-cs[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-operator_1.cs)]</span></span>  
  
## <a name="comments"></a><span data-ttu-id="32ad0-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="32ad0-110">Comments</span></span>  
 <span data-ttu-id="32ad0-111">Observe los errores de redondeo asociados con el tipo double.</span><span class="sxs-lookup"><span data-stu-id="32ad0-111">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32ad0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="32ad0-112">See Also</span></span>  
 <span data-ttu-id="32ad0-113">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="32ad0-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="32ad0-114">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="32ad0-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="32ad0-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="32ad0-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

