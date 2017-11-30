---
title: Operador % (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '%_CSharpKeyword'
helpviewer_keywords:
- modulus operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cea4aa03424e93f3ec144126d73c63931a737b54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="be9cf-102">Operador % (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="be9cf-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="be9cf-103">El operador `%` calcula el resto después de dividir el primer operando por el segundo.</span><span class="sxs-lookup"><span data-stu-id="be9cf-103">The `%` operator computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="be9cf-104">Todos los tipos numéricos tienen operadores restantes predefinidos.</span><span class="sxs-lookup"><span data-stu-id="be9cf-104">All numeric types have predefined remainder operators.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be9cf-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="be9cf-105">Remarks</span></span>  
 <span data-ttu-id="be9cf-106">Los tipos definidos por el usuario pueden sobrecargar el operador `%` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="be9cf-106">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="be9cf-107">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="be9cf-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be9cf-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="be9cf-108">Example</span></span>  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="be9cf-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="be9cf-109">Comments</span></span>  
 <span data-ttu-id="be9cf-110">Observe los errores de redondeo asociados con el tipo double.</span><span class="sxs-lookup"><span data-stu-id="be9cf-110">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be9cf-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="be9cf-111">See Also</span></span>  
 [<span data-ttu-id="be9cf-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="be9cf-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="be9cf-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="be9cf-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="be9cf-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="be9cf-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
