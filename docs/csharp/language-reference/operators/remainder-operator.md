---
title: Operador % (Referencia de C#)
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 796b4a40347fc5881db27a8a8a28404c7c4e8c5b
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="efc22-102">Operador % (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="efc22-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="efc22-103">El operador de resto (`%`) calcula el resto después de dividir su primer operando por el segundo.</span><span class="sxs-lookup"><span data-stu-id="efc22-103">The remainder operator (`%`) computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="efc22-104">Todos los tipos numéricos tienen operadores restantes predefinidos.</span><span class="sxs-lookup"><span data-stu-id="efc22-104">All numeric types have predefined remainder operators.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="efc22-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="efc22-105">Remarks</span></span>  
 <span data-ttu-id="efc22-106">La fórmula `a % b` siempre devuelve un valor en el intervalo `(-b, b)`, exclusivo (nunca puede devolver `b` o `-b`), manteniendo el signo del dividendo.</span><span class="sxs-lookup"><span data-stu-id="efc22-106">The formula `a % b` will always return a value on the range `(-b, b)`, exclusive (it can never return `b` or `-b`), keeping the sign of the dividend.</span></span> <span data-ttu-id="efc22-107">En la división de enteros, el operador de resto cumple la regla `a % b = a - (a / b) * b`.</span><span class="sxs-lookup"><span data-stu-id="efc22-107">For integer division, the remainder operator satisfies the rule `a % b = a - (a / b) * b`.</span></span>
  
 <span data-ttu-id="efc22-108">No debe confundirse con el módulo canónico, que satisface una regla similar pero con división por pisos y devuelve valores en el intervalo `[0, b)`.</span><span class="sxs-lookup"><span data-stu-id="efc22-108">This is not to be confused with canonical modulus, which satisfies a similar rule but with floored division and returns values on the range `[0, b)`.</span></span> <span data-ttu-id="efc22-109">C# no tiene ningún operador para el módulo canónico.</span><span class="sxs-lookup"><span data-stu-id="efc22-109">C# does not have an operator for canonical modulus.</span></span> <span data-ttu-id="efc22-110">Pero el comportamiento es el mismo para dividendos positivos.</span><span class="sxs-lookup"><span data-stu-id="efc22-110">However, the behavior is the same for positive dividends.</span></span>
  
 <span data-ttu-id="efc22-111">Los tipos definidos por el usuario pueden sobrecargar el operador `%` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="efc22-111">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="efc22-112">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="efc22-112">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efc22-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="efc22-113">Example</span></span>  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/remainder-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="efc22-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="efc22-114">Comments</span></span>  
 <span data-ttu-id="efc22-115">Observe los errores de redondeo asociados con el tipo double.</span><span class="sxs-lookup"><span data-stu-id="efc22-115">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc22-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="efc22-116">See Also</span></span>  
 [<span data-ttu-id="efc22-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="efc22-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="efc22-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="efc22-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="efc22-119">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="efc22-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
