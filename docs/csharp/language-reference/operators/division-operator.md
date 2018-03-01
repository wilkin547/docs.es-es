---
title: Operador / (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9e12e5c472266ea75d3f572a2091bd0784ea5dcf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="80a2f-102">Operador / (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="80a2f-102">/ Operator (C# Reference)</span></span>
<span data-ttu-id="80a2f-103">El operador de división (`/`) divide su primer operando por su segundo operando.</span><span class="sxs-lookup"><span data-stu-id="80a2f-103">The division operator (`/`) divides its first operand by its second operand.</span></span> <span data-ttu-id="80a2f-104">Todos los tipos numéricos tienen operadores de división predefinidos.</span><span class="sxs-lookup"><span data-stu-id="80a2f-104">All numeric types have predefined division operators.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80a2f-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80a2f-105">Remarks</span></span>  
 <span data-ttu-id="80a2f-106">Los tipos definidos por el usuario pueden sobrecargar el operador `/` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="80a2f-106">User-defined types can overload the `/` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="80a2f-107">Una sobrecarga del operador `/` sobrecarga implícitamente el [operador /=](division-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="80a2f-107">An overload of the `/` operator implicitly overloads the [/= operator](division-assignment-operator.md).</span></span>  
  
 <span data-ttu-id="80a2f-108">Cuando se dividen dos números enteros, el resultado siempre es un entero.</span><span class="sxs-lookup"><span data-stu-id="80a2f-108">When you divide two integers, the result is always an integer.</span></span> <span data-ttu-id="80a2f-109">Por ejemplo, el resultado de 7 / 3 es 2.</span><span class="sxs-lookup"><span data-stu-id="80a2f-109">For example, the result of 7 / 3 is 2.</span></span> <span data-ttu-id="80a2f-110">Para determinar el resto de 7 / 3, use el operador de resto ([%](../../../csharp/language-reference/operators/modulus-operator.md)).</span><span class="sxs-lookup"><span data-stu-id="80a2f-110">To determine the remainder of 7 / 3, use the remainder operator ([%](../../../csharp/language-reference/operators/modulus-operator.md)).</span></span> <span data-ttu-id="80a2f-111">Para obtener un cociente como un número racional o fracción, asigne al dividendo o al divisor el tipo `float` o el tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="80a2f-111">To obtain a quotient as a rational number or fraction, give the dividend or divisor type `float` or type `double`.</span></span> <span data-ttu-id="80a2f-112">Puede asignar el tipo de forma implícita si expresa el dividendo o el divisor como decimal. Para ello, coloque un dígito a la derecha del separador decimal, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="80a2f-112">You can assign the type implicitly if you express the dividend or divisor as a decimal by putting a digit to the right side of the decimal point, as the following example shows.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80a2f-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="80a2f-113">Example</span></span>  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="80a2f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="80a2f-114">See Also</span></span>  
 [<span data-ttu-id="80a2f-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="80a2f-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="80a2f-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="80a2f-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="80a2f-117">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="80a2f-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
