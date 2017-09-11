---
title: Operador &lt;&lt; (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <<_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4e6ad17232ec4eb087ca300342331af6a30789b1
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="f59b1-102">Operador &lt;&lt; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f59b1-102">&lt;&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="f59b1-103">El operador de desplazamiento a la izquierda (`<<`) desplaza su primer operando a la izquierda el número de bits especificado por su segundo operando.</span><span class="sxs-lookup"><span data-stu-id="f59b1-103">The left-shift operator (`<<`) shifts its first operand left by the number of bits specified by its second operand.</span></span> <span data-ttu-id="f59b1-104">El tipo del segundo operando debe ser [int](../../../csharp/language-reference/keywords/int.md) o un tipo que tiene una conversión numérica implícita predefinida en `int`.</span><span class="sxs-lookup"><span data-stu-id="f59b1-104">The type of the second operand must be an [int](../../../csharp/language-reference/keywords/int.md) or a type that has a predefined implicit numeric conversion to `int`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f59b1-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f59b1-105">Remarks</span></span>  
 <span data-ttu-id="f59b1-106">Si el primer operando es [int](../../../csharp/language-reference/keywords/int.md) o [uint](../../../csharp/language-reference/keywords/uint.md) (cantidad de 32 bits), el valor de desplazamiento viene dado por los cinco bits de orden inferior del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="f59b1-106">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [uint](../../../csharp/language-reference/keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand.</span></span> <span data-ttu-id="f59b1-107">Es decir, el recuento de desplazamiento real es de 0 a 31 bits.</span><span class="sxs-lookup"><span data-stu-id="f59b1-107">That is, the actual shift count is 0 to 31 bits.</span></span>  
  
 <span data-ttu-id="f59b1-108">Si el primer operando es [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) (cantidad de 64 bits), el valor de desplazamiento viene dado por los seis bits de orden inferior del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="f59b1-108">If the first operand is a [long](../../../csharp/language-reference/keywords/long.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand.</span></span> <span data-ttu-id="f59b1-109">Es decir, el recuento de desplazamiento real es de 0 a 63 bits.</span><span class="sxs-lookup"><span data-stu-id="f59b1-109">That is, the actual shift count is 0 to 63 bits.</span></span>  
  
 <span data-ttu-id="f59b1-110">Se descartan los bits de orden superior que no están dentro del intervalo del tipo del primer operando después del desplazamiento y se rellenan con ceros los bits vacíos de orden inferior.</span><span class="sxs-lookup"><span data-stu-id="f59b1-110">Any high-order bits that are not within the range of the type of the first operand after the shift are discarded, and the low-order empty bits are zero-filled.</span></span> <span data-ttu-id="f59b1-111">Las operaciones de desplazamiento nunca producen desbordamientos.</span><span class="sxs-lookup"><span data-stu-id="f59b1-111">Shift operations never cause overflows.</span></span>  
  
 <span data-ttu-id="f59b1-112">Los tipos definidos por el usuario pueden sobrecargar el operador `<<` (vea [operator](../../../csharp/language-reference/keywords/operator.md)); el tipo del primer operando debe ser el tipo definido por el usuario y el tipo del segundo operando debe ser `int`.</span><span class="sxs-lookup"><span data-stu-id="f59b1-112">User-defined types can overload the `<<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)); the type of the first operand must be the user-defined type, and the type of the second operand must be `int`.</span></span> <span data-ttu-id="f59b1-113">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="f59b1-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f59b1-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f59b1-114">Example</span></span>  
 <span data-ttu-id="f59b1-115">[!code-cs[csRefOperators#14](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f59b1-115">[!code-cs[csRefOperators#14](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-operator_1.cs)]</span></span>  
  
## <a name="comments"></a><span data-ttu-id="f59b1-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f59b1-116">Comments</span></span>  
 <span data-ttu-id="f59b1-117">Tenga en cuenta que `i<<1` y `i<<33` dan el mismo resultado, ya que 1 y 33 tienen los mismos cinco bits de orden inferior.</span><span class="sxs-lookup"><span data-stu-id="f59b1-117">Note that `i<<1` and `i<<33` give the same result, because 1 and 33 have the same low-order five bits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f59b1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f59b1-118">See Also</span></span>  
 <span data-ttu-id="f59b1-119">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f59b1-119">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f59b1-120">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f59b1-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="f59b1-121">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="f59b1-121">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

