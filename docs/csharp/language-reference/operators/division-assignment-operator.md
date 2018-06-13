---
title: /= (operador) (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: c31ff374e6af4c08c329a971fdd8af169e239395
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171627"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6d816-102">/= (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6d816-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="6d816-103">Operador de asignación y división.</span><span class="sxs-lookup"><span data-stu-id="6d816-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d816-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d816-104">Remarks</span></span>  
 <span data-ttu-id="6d816-105">Una expresión que use el operador de asignación `/=`, como</span><span class="sxs-lookup"><span data-stu-id="6d816-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```csharp  
x /= y  
```  
  
 <span data-ttu-id="6d816-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="6d816-106">is equivalent to</span></span>  
  
```csharp  
x = x / y  
```  
  
 <span data-ttu-id="6d816-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="6d816-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="6d816-108">El [operador /](../../../csharp/language-reference/operators/division-operator.md) está predefinido en tipos numéricos para realizar la división.</span><span class="sxs-lookup"><span data-stu-id="6d816-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="6d816-109">El operador `/=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador /](../../../csharp/language-reference/operators/division-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md) [Operador]).</span><span class="sxs-lookup"><span data-stu-id="6d816-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="6d816-110">En todos los operadores de asignación compuesta, al sobrecargar el operador binario implícitamente se sobrecarga la asignación compuesta equivalente.</span><span class="sxs-lookup"><span data-stu-id="6d816-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d816-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d816-111">Example</span></span>  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6d816-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d816-112">See Also</span></span>  
 [<span data-ttu-id="6d816-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6d816-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6d816-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6d816-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6d816-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="6d816-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
