---
title: Operador &amp; (Referencia de C#)
ms.date: 04/04/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: b257c7d41618464e26ab3b54bcfb1f1e2c2e420e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510983"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="69405-102">Operador &amp; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="69405-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="69405-103">El operador `&` puede funcionar como un operador unario o binario.</span><span class="sxs-lookup"><span data-stu-id="69405-103">The `&` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69405-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="69405-104">Remarks</span></span>  
 <span data-ttu-id="69405-105">El operador `&` unario devuelve la dirección de su operando (necesita un contexto [no seguro](../../../csharp/language-reference/keywords/unsafe.md)).</span><span class="sxs-lookup"><span data-stu-id="69405-105">The unary `&` operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="69405-106">Los operadores binarios `&` están predefinidos para los tipos enteros y `bool`.</span><span class="sxs-lookup"><span data-stu-id="69405-106">Binary `&` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="69405-107">Para los tipos enteros, & calcula el AND bit a bit lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="69405-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="69405-108">Para operandos `bool`, & calcula el AND lógico de sus operandos; es decir, el resultado es `true` si y solo si ambos operandos son `true`.</span><span class="sxs-lookup"><span data-stu-id="69405-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="69405-109">El operador `&` binario evalúa ambos operandos con independencia del valor del primero, a diferencia del [operador AND condicional](../../../csharp/language-reference/operators/conditional-and-operator.md) `&&`.</span><span class="sxs-lookup"><span data-stu-id="69405-109">The binary `&` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional AND operator](../../../csharp/language-reference/operators/conditional-and-operator.md) `&&`.</span></span> <span data-ttu-id="69405-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="69405-110">For example:</span></span>  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 <span data-ttu-id="69405-111">Los tipos definidos por el usuario pueden sobrecargar el operador binario `&` (consulte [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="69405-111">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="69405-112">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="69405-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="69405-113">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="69405-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69405-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69405-114">Example</span></span>  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="69405-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="69405-115">See Also</span></span>

- [<span data-ttu-id="69405-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="69405-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="69405-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="69405-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="69405-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="69405-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
