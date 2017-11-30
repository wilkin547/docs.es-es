---
title: Operador &amp; (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eceee8e01ba46f65c6b182a40d14e62aaba5dd53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="c17ee-102">Operador &amp; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c17ee-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="c17ee-103">El operador & puede funcionar como un operador unario o binario.</span><span class="sxs-lookup"><span data-stu-id="c17ee-103">The & operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c17ee-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c17ee-104">Remarks</span></span>  
 <span data-ttu-id="c17ee-105">El operador & unario devuelve la dirección de su operando (necesita un contexto [no seguro](../../../csharp/language-reference/keywords/unsafe.md)).</span><span class="sxs-lookup"><span data-stu-id="c17ee-105">The unary & operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="c17ee-106">Los operadores & binarios están predefinidos para los tipos enteros y `bool`.</span><span class="sxs-lookup"><span data-stu-id="c17ee-106">Binary & operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="c17ee-107">Para los tipos enteros, & calcula el AND bit a bit lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="c17ee-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="c17ee-108">Para operandos `bool`, & calcula el AND lógico de sus operandos; es decir, el resultado es `true` si y solo si ambos operandos son `true`.</span><span class="sxs-lookup"><span data-stu-id="c17ee-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="c17ee-109">El operador `&` evalúa ambos operadores independientemente del valor del primero.</span><span class="sxs-lookup"><span data-stu-id="c17ee-109">The `&` operator evaluates both operators regardless of the first one's value.</span></span> <span data-ttu-id="c17ee-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c17ee-110">For example:</span></span>  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 <span data-ttu-id="c17ee-111">Los tipos definidos por el usuario pueden sobrecargar el operador binario `&` (consulte [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="c17ee-111">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="c17ee-112">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="c17ee-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="c17ee-113">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="c17ee-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c17ee-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c17ee-114">Example</span></span>  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c17ee-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c17ee-115">See Also</span></span>  
 [<span data-ttu-id="c17ee-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c17ee-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c17ee-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c17ee-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c17ee-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="c17ee-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
