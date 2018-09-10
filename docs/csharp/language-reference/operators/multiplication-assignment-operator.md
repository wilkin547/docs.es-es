---
title: Operador *= (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: e47bc5c681c94ac3fc5c345c56b3814350ffa5ec
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517173"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="04e3c-102">Operador \*= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="04e3c-102">\*= Operator (C# Reference)</span></span>
<span data-ttu-id="04e3c-103">El operador de asignación y multiplicación binaria.</span><span class="sxs-lookup"><span data-stu-id="04e3c-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04e3c-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04e3c-104">Remarks</span></span>  
 <span data-ttu-id="04e3c-105">Una expresión que use el operador de asignación `*=`, como</span><span class="sxs-lookup"><span data-stu-id="04e3c-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```csharp  
x *= y  
```  
  
 <span data-ttu-id="04e3c-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="04e3c-106">is equivalent to</span></span>  
  
```csharp  
x = x * y  
```  
  
 <span data-ttu-id="04e3c-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="04e3c-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="04e3c-108">El [operador \*](../../../csharp/language-reference/operators/multiplication-operator.md) está predefinido en tipos numéricos para realizar la multiplicación.</span><span class="sxs-lookup"><span data-stu-id="04e3c-108">The [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="04e3c-109">El operador `*=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador \*](../../../csharp/language-reference/operators/multiplication-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="04e3c-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="04e3c-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04e3c-110">Example</span></span>  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="04e3c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="04e3c-111">See Also</span></span>

- [<span data-ttu-id="04e3c-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="04e3c-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="04e3c-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="04e3c-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="04e3c-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="04e3c-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
