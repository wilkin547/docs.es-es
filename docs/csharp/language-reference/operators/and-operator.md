---
title: Operador &amp; (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d92a860df6fcc9acf14aab4ec558556735ac8aac
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="9e4e6-102">Operador &amp; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9e4e6-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="9e4e6-103">El operador & puede funcionar como un operador unario o binario.</span><span class="sxs-lookup"><span data-stu-id="9e4e6-103">The & operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e4e6-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9e4e6-104">Remarks</span></span>  
 <span data-ttu-id="9e4e6-105">El operador & unario devuelve la dirección de su operando (necesita un contexto [no seguro](../../../csharp/language-reference/keywords/unsafe.md)).</span><span class="sxs-lookup"><span data-stu-id="9e4e6-105">The unary & operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="9e4e6-106">Los operadores & binarios están predefinidos para los tipos enteros y `bool`.</span><span class="sxs-lookup"><span data-stu-id="9e4e6-106">Binary & operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="9e4e6-107">Para los tipos enteros, & calcula el AND bit a bit lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="9e4e6-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="9e4e6-108">Para operandos `bool`, & calcula el AND lógico de sus operandos; es decir, el resultado es `true` si y solo si ambos operandos son `true`.</span><span class="sxs-lookup"><span data-stu-id="9e4e6-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="9e4e6-109">El operador `&` evalúa ambos operadores independientemente del valor del primero.</span><span class="sxs-lookup"><span data-stu-id="9e4e6-109">The `&` operator evaluates both operators regardless of the first one's value.</span></span> <span data-ttu-id="9e4e6-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9e4e6-110">For example:</span></span>  
  
 <span data-ttu-id="9e4e6-111">[!code-cs[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9e4e6-111">[!code-cs[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="9e4e6-112">Los tipos definidos por el usuario pueden sobrecargar el operador binario `&` (consulte [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="9e4e6-112">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="9e4e6-113">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="9e4e6-113">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="9e4e6-114">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="9e4e6-114">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e4e6-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e4e6-115">Example</span></span>  
 <span data-ttu-id="9e4e6-116">[!code-cs[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9e4e6-116">[!code-cs[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e4e6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e4e6-117">See Also</span></span>  
 <span data-ttu-id="9e4e6-118">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9e4e6-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9e4e6-119">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9e4e6-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="9e4e6-120">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="9e4e6-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

