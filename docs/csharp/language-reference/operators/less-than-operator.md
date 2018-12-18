---
title: 'Operador &lt;: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
ms.openlocfilehash: 3cc125471eee7bf0002e9844c2a1cdc05e8d4a03
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241242"
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="e9b31-102">Operador &lt; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="e9b31-102">&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="e9b31-103">Todos los tipos de enumeración y numéricos definen un operador relacional "menor que" (`<`) que devuelve `true` si el primer operando es menor que el segundo; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="e9b31-103">All numeric and enumeration types define a "less than" relational operator (`<`) that returns `true` if the first operand is less than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9b31-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e9b31-104">Remarks</span></span>  
 <span data-ttu-id="e9b31-105">Los tipos definidos por el usuario pueden sobrecargar el operador `<` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="e9b31-105">User-defined types can overload the `<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="e9b31-106">Si `<` está sobrecargado, [>](../../../csharp/language-reference/operators/greater-than-operator.md) también debe estar sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="e9b31-106">If `<` is overloaded, [>](../../../csharp/language-reference/operators/greater-than-operator.md) must also be overloaded.</span></span>
  
## <a name="example"></a><span data-ttu-id="e9b31-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9b31-107">Example</span></span>  
 [!code-csharp[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e9b31-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9b31-108">See Also</span></span>

- [<span data-ttu-id="e9b31-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="e9b31-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="e9b31-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e9b31-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="e9b31-111">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="e9b31-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
