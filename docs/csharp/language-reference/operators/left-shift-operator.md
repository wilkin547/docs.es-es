---
title: Operador &lt;&lt; (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 400dbc799c68bb9e1bc00695954115f2eb6af7c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="3784c-102">Operador &lt;&lt; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="3784c-102">&lt;&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="3784c-103">El operador de desplazamiento a la izquierda (`<<`) desplaza su primer operando a la izquierda el número de bits especificado por su segundo operando.</span><span class="sxs-lookup"><span data-stu-id="3784c-103">The left-shift operator (`<<`) shifts its first operand left by the number of bits specified by its second operand.</span></span> <span data-ttu-id="3784c-104">El tipo del segundo operando debe ser [int](../../../csharp/language-reference/keywords/int.md) o un tipo que tiene una conversión numérica implícita predefinida en `int`.</span><span class="sxs-lookup"><span data-stu-id="3784c-104">The type of the second operand must be an [int](../../../csharp/language-reference/keywords/int.md) or a type that has a predefined implicit numeric conversion to `int`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3784c-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3784c-105">Remarks</span></span>  
 <span data-ttu-id="3784c-106">Si el primer operando es [int](../../../csharp/language-reference/keywords/int.md) o [uint](../../../csharp/language-reference/keywords/uint.md) (cantidad de 32 bits), el valor de desplazamiento viene dado por los cinco bits de orden inferior del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="3784c-106">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [uint](../../../csharp/language-reference/keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand.</span></span> <span data-ttu-id="3784c-107">Es decir, el recuento de desplazamiento real es de 0 a 31 bits.</span><span class="sxs-lookup"><span data-stu-id="3784c-107">That is, the actual shift count is 0 to 31 bits.</span></span>  
  
 <span data-ttu-id="3784c-108">Si el primer operando es [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) (cantidad de 64 bits), el valor de desplazamiento viene dado por los seis bits de orden inferior del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="3784c-108">If the first operand is a [long](../../../csharp/language-reference/keywords/long.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand.</span></span> <span data-ttu-id="3784c-109">Es decir, el recuento de desplazamiento real es de 0 a 63 bits.</span><span class="sxs-lookup"><span data-stu-id="3784c-109">That is, the actual shift count is 0 to 63 bits.</span></span>  
  
 <span data-ttu-id="3784c-110">Se descartan los bits de orden superior que no están dentro del intervalo del tipo del primer operando después del desplazamiento y se rellenan con ceros los bits vacíos de orden inferior.</span><span class="sxs-lookup"><span data-stu-id="3784c-110">Any high-order bits that are not within the range of the type of the first operand after the shift are discarded, and the low-order empty bits are zero-filled.</span></span> <span data-ttu-id="3784c-111">Las operaciones de desplazamiento nunca producen desbordamientos.</span><span class="sxs-lookup"><span data-stu-id="3784c-111">Shift operations never cause overflows.</span></span>  
  
 <span data-ttu-id="3784c-112">Los tipos definidos por el usuario pueden sobrecargar el operador `<<` (vea [operator](../../../csharp/language-reference/keywords/operator.md)); el tipo del primer operando debe ser el tipo definido por el usuario y el tipo del segundo operando debe ser `int`.</span><span class="sxs-lookup"><span data-stu-id="3784c-112">User-defined types can overload the `<<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)); the type of the first operand must be the user-defined type, and the type of the second operand must be `int`.</span></span> <span data-ttu-id="3784c-113">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="3784c-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3784c-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3784c-114">Example</span></span>  
 [!code-csharp[csRefOperators#14](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="3784c-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3784c-115">Comments</span></span>  
 <span data-ttu-id="3784c-116">Tenga en cuenta que `i<<1` y `i<<33` dan el mismo resultado, ya que 1 y 33 tienen los mismos cinco bits de orden inferior.</span><span class="sxs-lookup"><span data-stu-id="3784c-116">Note that `i<<1` and `i<<33` give the same result, because 1 and 33 have the same low-order five bits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3784c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3784c-117">See Also</span></span>  
 [<span data-ttu-id="3784c-118">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="3784c-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="3784c-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3784c-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3784c-120">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="3784c-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
