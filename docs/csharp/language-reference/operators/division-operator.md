---
title: Operador / (Referencia de C#)
ms.date: 04/04/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: bddf6d234f3536ad64f0cd876cc7ade4494916d9
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43800760"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="f20a7-102">Operador / (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f20a7-102">/ Operator (C# Reference)</span></span>
<span data-ttu-id="f20a7-103">El operador de división (`/`) divide su primer operando por su segundo operando.</span><span class="sxs-lookup"><span data-stu-id="f20a7-103">The division operator (`/`) divides its first operand by its second operand.</span></span> <span data-ttu-id="f20a7-104">Todos los tipos numéricos tienen operadores de división predefinidos.</span><span class="sxs-lookup"><span data-stu-id="f20a7-104">All numeric types have predefined division operators.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f20a7-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f20a7-105">Remarks</span></span>  
 <span data-ttu-id="f20a7-106">Los tipos definidos por el usuario pueden sobrecargar el operador `/` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="f20a7-106">User-defined types can overload the `/` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="f20a7-107">Una sobrecarga del operador `/` sobrecarga implícitamente el [operador /=](division-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f20a7-107">An overload of the `/` operator implicitly overloads the [/= operator](division-assignment-operator.md).</span></span>  
  
 <span data-ttu-id="f20a7-108">Cuando se dividen dos números enteros, el resultado siempre es un entero.</span><span class="sxs-lookup"><span data-stu-id="f20a7-108">When you divide two integers, the result is always an integer.</span></span> <span data-ttu-id="f20a7-109">Por ejemplo, el resultado de 7 / 3 es 2.</span><span class="sxs-lookup"><span data-stu-id="f20a7-109">For example, the result of 7 / 3 is 2.</span></span> <span data-ttu-id="f20a7-110">No debe confundirse con la división por pisos, ya que el operador `/` redondea hacia cero: -7 / 3 es -2.</span><span class="sxs-lookup"><span data-stu-id="f20a7-110">This is not to be confused with floored division, as the `/` operator rounds towards zero: -7 / 3 is -2.</span></span>  
  
 <span data-ttu-id="f20a7-111">Para obtener un cociente como un número racional, use los tipos `float`, `double` o `decimal`.</span><span class="sxs-lookup"><span data-stu-id="f20a7-111">To obtain a quotient as a rational number, use the `float`, `double`, or `decimal` types.</span></span> <span data-ttu-id="f20a7-112">Hay muchas maneras de convertir entre [los tipos numéricos integrados](../../../csharp/language-reference/keywords/reference-tables-for-types.md).</span><span class="sxs-lookup"><span data-stu-id="f20a7-112">There are many ways to convert between [built in numeric types](../../../csharp/language-reference/keywords/reference-tables-for-types.md).</span></span>  
  
 <span data-ttu-id="f20a7-113">Para determinar el resto, use el [operador de resto](../../../csharp/language-reference/operators/remainder-operator.md) `%`.</span><span class="sxs-lookup"><span data-stu-id="f20a7-113">To determine the remainder, use the [remainder operator](../../../csharp/language-reference/operators/remainder-operator.md) `%`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f20a7-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f20a7-114">Example</span></span>  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f20a7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f20a7-115">See Also</span></span>

- [<span data-ttu-id="f20a7-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f20a7-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="f20a7-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f20a7-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f20a7-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="f20a7-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
