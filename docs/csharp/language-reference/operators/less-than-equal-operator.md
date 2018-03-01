---
title: Operador &lt;= (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <=_CSharpKeyword
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a74af852451a193aaee70fea2a68ca8ff29cc215
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="fed8a-102">Operador &lt;= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="fed8a-102">&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="fed8a-103">Todos los tipos de enumeración y numéricos definen un operador relacional "menor o igual que" (`<=`), que devuelve `true` si el primer operando es menor o igual que el segundo; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="fed8a-103">All numeric and enumeration types define a "less than or equal" relational operator (`<=`) that returns `true` if the first operand is less than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fed8a-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fed8a-104">Remarks</span></span>  
 <span data-ttu-id="fed8a-105">Los tipos definidos por el usuario pueden sobrecargar el operador `<=`.</span><span class="sxs-lookup"><span data-stu-id="fed8a-105">User-defined types can overload the `<=` operator.</span></span> <span data-ttu-id="fed8a-106">Para obtener más información, vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="fed8a-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="fed8a-107">Si `<=` está sobrecargado, [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) también debe estar sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="fed8a-107">If `<=` is overloaded, [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="fed8a-108">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="fed8a-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fed8a-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fed8a-109">Example</span></span>  
 [!code-csharp[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fed8a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="fed8a-110">See Also</span></span>  
 [<span data-ttu-id="fed8a-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="fed8a-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="fed8a-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fed8a-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fed8a-113">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="fed8a-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="fed8a-114">explicit</span><span class="sxs-lookup"><span data-stu-id="fed8a-114">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
