---
title: Operador &gt;= (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
caps.latest.revision: 16
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
ms.openlocfilehash: 59b134ce1e1169b0a5f4583374148d39ceb8326a
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="f1ea0-102">Operador &gt;= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f1ea0-102">&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="f1ea0-103">Todos los tipos de enumeración y numéricos definen un operador relacional "mayor o igual que", `>=`, que devuelve `true` si el primer operando es mayor o igual que el segundo, `false` de otro modo.</span><span class="sxs-lookup"><span data-stu-id="f1ea0-103">All numeric and enumeration types define a "greater than or equal" relational operator, `>=` that returns `true` if the first operand is greater than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1ea0-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f1ea0-104">Remarks</span></span>  
 <span data-ttu-id="f1ea0-105">Los tipos definidos por el usuario pueden sobrecargar el operador `>=`.</span><span class="sxs-lookup"><span data-stu-id="f1ea0-105">User-defined types can overload the `>=` operator.</span></span> <span data-ttu-id="f1ea0-106">Para obtener más información, vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="f1ea0-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="f1ea0-107">Si `>=` está sobrecargado, [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) también debe estar sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="f1ea0-107">If `>=` is overloaded, [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="f1ea0-108">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="f1ea0-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1ea0-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1ea0-109">Example</span></span>  
 <span data-ttu-id="f1ea0-110">[!code-cs[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f1ea0-110">[!code-cs[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1ea0-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1ea0-111">See Also</span></span>  
 <span data-ttu-id="f1ea0-112">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f1ea0-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f1ea0-113">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f1ea0-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="f1ea0-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="f1ea0-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

