---
title: Operador &gt;= (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
ms.openlocfilehash: 8749d1dc0670a5a76bda5ee0d69a4a142671c1e6
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "43000290"
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="542ff-102">Operador &gt;= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="542ff-102">&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="542ff-103">Todos los tipos de enumeración y numéricos definen un operador relacional "mayor o igual que", `>=`, que devuelve `true` si el primer operando es mayor o igual que el segundo, `false` de otro modo.</span><span class="sxs-lookup"><span data-stu-id="542ff-103">All numeric and enumeration types define a "greater than or equal" relational operator, `>=` that returns `true` if the first operand is greater than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="542ff-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="542ff-104">Remarks</span></span>  
 <span data-ttu-id="542ff-105">Los tipos definidos por el usuario pueden sobrecargar el operador `>=`.</span><span class="sxs-lookup"><span data-stu-id="542ff-105">User-defined types can overload the `>=` operator.</span></span> <span data-ttu-id="542ff-106">Para obtener más información, vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="542ff-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="542ff-107">Si `>=` está sobrecargado, [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) también debe estar sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="542ff-107">If `>=` is overloaded, [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="542ff-108">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="542ff-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="542ff-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="542ff-109">Example</span></span>  
 [!code-csharp[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="542ff-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="542ff-110">See Also</span></span>

- [<span data-ttu-id="542ff-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="542ff-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="542ff-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="542ff-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="542ff-113">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="542ff-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
