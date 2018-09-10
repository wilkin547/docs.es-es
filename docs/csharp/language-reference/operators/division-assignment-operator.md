---
title: /= (operador) (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: 8fff048cc441181aa3f0e3c0c638d501aaf9de3f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526313"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="57cac-102">/= (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="57cac-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="57cac-103">Operador de asignación y división.</span><span class="sxs-lookup"><span data-stu-id="57cac-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57cac-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="57cac-104">Remarks</span></span>  
 <span data-ttu-id="57cac-105">Una expresión que use el operador de asignación `/=`, como</span><span class="sxs-lookup"><span data-stu-id="57cac-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```csharp  
x /= y  
```  
  
 <span data-ttu-id="57cac-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="57cac-106">is equivalent to</span></span>  
  
```csharp  
x = x / y  
```  
  
 <span data-ttu-id="57cac-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="57cac-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="57cac-108">El [operador /](../../../csharp/language-reference/operators/division-operator.md) está predefinido en tipos numéricos para realizar la división.</span><span class="sxs-lookup"><span data-stu-id="57cac-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="57cac-109">El operador `/=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador /](../../../csharp/language-reference/operators/division-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md) [Operador]).</span><span class="sxs-lookup"><span data-stu-id="57cac-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="57cac-110">En todos los operadores de asignación compuesta, al sobrecargar el operador binario implícitamente se sobrecarga la asignación compuesta equivalente.</span><span class="sxs-lookup"><span data-stu-id="57cac-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57cac-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57cac-111">Example</span></span>  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="57cac-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="57cac-112">See Also</span></span>

- [<span data-ttu-id="57cac-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="57cac-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="57cac-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="57cac-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="57cac-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="57cac-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
