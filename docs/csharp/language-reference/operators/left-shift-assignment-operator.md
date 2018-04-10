---
title: Operador &lt;&lt;= (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b5c2a177182561075442afc3f1b76603c6646bd6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="ab509-102">Operador &lt;&lt;= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ab509-102">&lt;&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="ab509-103">Operador de asignación de desplazamiento a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="ab509-103">The left-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab509-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ab509-104">Remarks</span></span>  
 <span data-ttu-id="ab509-105">Una expresión con el formato</span><span class="sxs-lookup"><span data-stu-id="ab509-105">An expression of the form</span></span>  
  
```  
x <<= y  
```  
  
 <span data-ttu-id="ab509-106">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="ab509-106">is evaluated as</span></span>  
  
```  
x = x << y  
```  
  
 <span data-ttu-id="ab509-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="ab509-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="ab509-108">El [operador <<](../../../csharp/language-reference/operators/left-shift-operator.md) desplaza `x` hacia la izquierda el número de bits especificado por `y`.</span><span class="sxs-lookup"><span data-stu-id="ab509-108">The [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>  
  
 <span data-ttu-id="ab509-109">El operador `<<=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador <<](../../../csharp/language-reference/operators/left-shift-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="ab509-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab509-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ab509-110">Example</span></span>  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ab509-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab509-111">See Also</span></span>  
 [<span data-ttu-id="ab509-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="ab509-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ab509-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ab509-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ab509-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="ab509-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
