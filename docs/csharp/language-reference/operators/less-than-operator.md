---
title: Operador &lt; (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
caps.latest.revision: 14
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
ms.openlocfilehash: 5d90a8e549b54fc229ac3ae5bb8f30ce3b55c0d4
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="62c53-102">Operador &lt; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="62c53-102">&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="62c53-103">Todos los tipos de enumeración y numéricos definen un operador relacional "menor que" (`<`) que devuelve `true` si el primer operando es menor que el segundo; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="62c53-103">All numeric and enumeration types define a "less than" relational operator (`<`) that returns `true` if the first operand is less than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62c53-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="62c53-104">Remarks</span></span>  
 <span data-ttu-id="62c53-105">Los tipos definidos por el usuario pueden sobrecargar el operador `<` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="62c53-105">User-defined types can overload the `<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="62c53-106">Si `<` está sobrecargado, [>](../../../csharp/language-reference/operators/greater-than-operator.md) también debe estar sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="62c53-106">If `<` is overloaded, [>](../../../csharp/language-reference/operators/greater-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="62c53-107">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="62c53-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62c53-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="62c53-108">Example</span></span>  
 <span data-ttu-id="62c53-109">[!code-cs[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="62c53-109">[!code-cs[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62c53-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="62c53-110">See Also</span></span>  
 <span data-ttu-id="62c53-111">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="62c53-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="62c53-112">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="62c53-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="62c53-113">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="62c53-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

