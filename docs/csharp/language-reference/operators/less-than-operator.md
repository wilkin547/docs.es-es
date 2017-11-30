---
title: Operador &lt; (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 76d53d4c943c886f6b8c8a68e2b8bb12bc9a9d6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="fd69f-102">Operador &lt; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="fd69f-102">&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="fd69f-103">Todos los tipos de enumeración y numéricos definen un operador relacional "menor que" (`<`) que devuelve `true` si el primer operando es menor que el segundo; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="fd69f-103">All numeric and enumeration types define a "less than" relational operator (`<`) that returns `true` if the first operand is less than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd69f-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd69f-104">Remarks</span></span>  
 <span data-ttu-id="fd69f-105">Los tipos definidos por el usuario pueden sobrecargar el operador `<` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="fd69f-105">User-defined types can overload the `<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="fd69f-106">Si `<` está sobrecargado, [>](../../../csharp/language-reference/operators/greater-than-operator.md) también debe estar sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="fd69f-106">If `<` is overloaded, [>](../../../csharp/language-reference/operators/greater-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="fd69f-107">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="fd69f-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd69f-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fd69f-108">Example</span></span>  
 [!code-csharp[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fd69f-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd69f-109">See Also</span></span>  
 [<span data-ttu-id="fd69f-110">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="fd69f-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="fd69f-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fd69f-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fd69f-112">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="fd69f-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
