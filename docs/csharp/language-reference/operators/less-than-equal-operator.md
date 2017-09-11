---
title: Operador &lt;= (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
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
ms.openlocfilehash: 931843783888a844d9f90f273b2362d327e8ccbc
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="c854e-102">Operador &lt;= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c854e-102">&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="c854e-103">Todos los tipos de enumeración y numéricos definen un operador relacional "menor o igual que" (`<=`), que devuelve `true` si el primer operando es menor o igual que el segundo; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c854e-103">All numeric and enumeration types define a "less than or equal" relational operator (`<=`) that returns `true` if the first operand is less than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c854e-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c854e-104">Remarks</span></span>  
 <span data-ttu-id="c854e-105">Los tipos definidos por el usuario pueden sobrecargar el operador `<=`.</span><span class="sxs-lookup"><span data-stu-id="c854e-105">User-defined types can overload the `<=` operator.</span></span> <span data-ttu-id="c854e-106">Para obtener más información, vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="c854e-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="c854e-107">Si `<=` está sobrecargado, [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) también debe estar sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="c854e-107">If `<=` is overloaded, [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="c854e-108">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="c854e-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c854e-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c854e-109">Example</span></span>  
 <span data-ttu-id="c854e-110">[!code-cs[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c854e-110">[!code-cs[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c854e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c854e-111">See Also</span></span>  
 <span data-ttu-id="c854e-112">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c854e-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c854e-113">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c854e-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c854e-114">[Operadores de C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="c854e-114">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="c854e-115">explicit</span><span class="sxs-lookup"><span data-stu-id="c854e-115">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)

