---
title: /= (operador) (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 26096d9b5dfc565c9933f1ed8ffb241dc900d9ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="987c1-102">/= (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="987c1-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="987c1-103">Operador de asignación y división.</span><span class="sxs-lookup"><span data-stu-id="987c1-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="987c1-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="987c1-104">Remarks</span></span>  
 <span data-ttu-id="987c1-105">Una expresión que use el operador de asignación `/=`, como</span><span class="sxs-lookup"><span data-stu-id="987c1-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```  
x /= y  
```  
  
 <span data-ttu-id="987c1-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="987c1-106">is equivalent to</span></span>  
  
```  
x = x / y  
```  
  
 <span data-ttu-id="987c1-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="987c1-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="987c1-108">El [operador /](../../../csharp/language-reference/operators/division-operator.md) está predefinido en tipos numéricos para realizar la división.</span><span class="sxs-lookup"><span data-stu-id="987c1-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="987c1-109">El operador `/=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador /](../../../csharp/language-reference/operators/division-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md) [Operador]).</span><span class="sxs-lookup"><span data-stu-id="987c1-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="987c1-110">En todos los operadores de asignación compuesta, al sobrecargar el operador binario implícitamente se sobrecarga la asignación compuesta equivalente.</span><span class="sxs-lookup"><span data-stu-id="987c1-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="987c1-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="987c1-111">Example</span></span>  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="987c1-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="987c1-112">See Also</span></span>  
 [<span data-ttu-id="987c1-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="987c1-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="987c1-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="987c1-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="987c1-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="987c1-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
