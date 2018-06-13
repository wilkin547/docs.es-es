---
title: Operador &gt; (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- '>_CSharpKeyword'
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
ms.openlocfilehash: 1589c5e785b33db6106a0ef0a58202e771db9fa0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273503"
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="7eb84-102">Operador &gt; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="7eb84-102">&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="7eb84-103">Todos los tipos de enumeración y numéricos definen un operador relacional "mayor que" (`>`) que devuelve `true` si el primer operando es mayor que el segundo, `false` de otro modo.</span><span class="sxs-lookup"><span data-stu-id="7eb84-103">All numeric and enumeration types define a "greater than" relational operator (`>`) that returns `true` if the first operand is greater than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7eb84-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7eb84-104">Remarks</span></span>  
 <span data-ttu-id="7eb84-105">Los tipos definidos por el usuario pueden sobrecargar el operador `>` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="7eb84-105">User-defined types can overload the `>` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="7eb84-106">Si `>` está sobrecargado, [<](../../../csharp/language-reference/operators/less-than-operator.md) también debe estar sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="7eb84-106">If `>` is overloaded, [<](../../../csharp/language-reference/operators/less-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="7eb84-107">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="7eb84-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7eb84-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7eb84-108">Example</span></span>  
 [!code-csharp[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7eb84-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="7eb84-109">See Also</span></span>  
 [<span data-ttu-id="7eb84-110">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="7eb84-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7eb84-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7eb84-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7eb84-112">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="7eb84-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="7eb84-113">explicit</span><span class="sxs-lookup"><span data-stu-id="7eb84-113">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
