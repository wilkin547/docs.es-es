---
title: Operador &gt;&gt; (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 7a2992befcacfdc1d9bb968b611051e15702cca8
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924829"
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="9a6c3-102">Operador &gt;&gt; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-102">&gt;&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="9a6c3-103">El operador de desplazamiento a la derecha (`>>`) desplaza su primer operando a la derecha el número de bits especificado por su segundo operando.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-103">The right-shift operator (`>>`) shifts its first operand right by the number of bits specified by its second operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a6c3-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a6c3-104">Remarks</span></span>  
 <span data-ttu-id="9a6c3-105">Si el primer operando es [int](../../../csharp/language-reference/keywords/int.md) o [uint](../../../csharp/language-reference/keywords/uint.md) (cantidad de 32 bits), el valor de desplazamiento viene dado por los cinco bits de orden inferior del segundo operando (segundo operando y 0x1f).</span><span class="sxs-lookup"><span data-stu-id="9a6c3-105">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [uint](../../../csharp/language-reference/keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand (second operand & 0x1f).</span></span>  
  
 <span data-ttu-id="9a6c3-106">Si el primer operando es [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) (cantidad de 64 bits), el valor de desplazamiento viene dado por los seis bits de orden inferior del segundo operando (segundo operando y 0x3f).</span><span class="sxs-lookup"><span data-stu-id="9a6c3-106">If the first operand is a [long](../../../csharp/language-reference/keywords/long.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand (second operand & 0x3f).</span></span>  
  
 <span data-ttu-id="9a6c3-107">Si el primer operando es [int](../../../csharp/language-reference/keywords/int.md) o [long](../../../csharp/language-reference/keywords/long.md), el desplazamiento a la derecha es un desplazamiento aritmético (los bits vacíos de orden superior se establecen en el bit de signo).</span><span class="sxs-lookup"><span data-stu-id="9a6c3-107">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [long](../../../csharp/language-reference/keywords/long.md), the right-shift is an arithmetic shift (high-order empty bits are set to the sign bit).</span></span> <span data-ttu-id="9a6c3-108">Si el primer operando es de tipo [uint](../../../csharp/language-reference/keywords/uint.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md), el desplazamiento a la derecha es un desplazamiento lógico (los bits de orden superior se rellenan con ceros).</span><span class="sxs-lookup"><span data-stu-id="9a6c3-108">If the first operand is of type [uint](../../../csharp/language-reference/keywords/uint.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md), the right-shift is a logical shift (high-order bits are zero-filled).</span></span>  
  
 <span data-ttu-id="9a6c3-109">Los tipos definidos por el usuario pueden sobrecargar el operador `>>`; el tipo del primer operando debe ser el tipo definido por el usuario y el tipo del segundo operando debe ser [int](../../../csharp/language-reference/keywords/int.md). Para obtener más información, vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="9a6c3-109">User-defined types can overload the `>>` operator; the type of the first operand must be the user-defined type, and the type of the second operand must be [int](../../../csharp/language-reference/keywords/int.md). For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="9a6c3-110">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-110">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a6c3-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a6c3-111">Example</span></span>  
 [!code-csharp[csRefOperators#26](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="9a6c3-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a6c3-112">See Also</span></span>

- [<span data-ttu-id="9a6c3-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9a6c3-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="9a6c3-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9a6c3-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="9a6c3-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="9a6c3-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
