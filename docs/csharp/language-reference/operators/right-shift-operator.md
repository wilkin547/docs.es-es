---
title: 'Operador &gt;&gt;: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 80e38d8e75b9ad573b635d544d6381950f107583
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333696"
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="c87d1-102">Operador &gt;&gt; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c87d1-102">&gt;&gt; operator (C# Reference)</span></span>

<span data-ttu-id="c87d1-103">El operador de desplazamiento a la derecha (`>>`) desplaza su primer operando a la derecha el número de bits especificado por su segundo operando.</span><span class="sxs-lookup"><span data-stu-id="c87d1-103">The right-shift operator (`>>`) shifts its first operand right by the number of bits specified by its second operand.</span></span>

## <a name="remarks"></a><span data-ttu-id="c87d1-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c87d1-104">Remarks</span></span>

<span data-ttu-id="c87d1-105">Si el primer operando es [int](../keywords/int.md) o [uint](../keywords/uint.md) (cantidad de 32 bits), el valor de desplazamiento viene dado por los cinco bits de orden inferior del segundo operando (segundo operando y 0x1f).</span><span class="sxs-lookup"><span data-stu-id="c87d1-105">If the first operand is an [int](../keywords/int.md) or [uint](../keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand (second operand & 0x1f).</span></span>

<span data-ttu-id="c87d1-106">Si el primer operando es [long](../keywords/long.md) o [ulong](../keywords/ulong.md) (cantidad de 64 bits), el valor de desplazamiento viene dado por los seis bits de orden inferior del segundo operando (segundo operando y 0x3f).</span><span class="sxs-lookup"><span data-stu-id="c87d1-106">If the first operand is a [long](../keywords/long.md) or [ulong](../keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand (second operand & 0x3f).</span></span>

<span data-ttu-id="c87d1-107">Si el primer operando es [int](../keywords/int.md) o [long](../keywords/long.md), el desplazamiento a la derecha es un desplazamiento aritmético (los bits vacíos de orden superior se establecen en el bit de signo).</span><span class="sxs-lookup"><span data-stu-id="c87d1-107">If the first operand is an [int](../keywords/int.md) or [long](../keywords/long.md), the right-shift is an arithmetic shift (high-order empty bits are set to the sign bit).</span></span> <span data-ttu-id="c87d1-108">Si el primer operando es de tipo [uint](../keywords/uint.md) o [ulong](../keywords/ulong.md), el desplazamiento a la derecha es un desplazamiento lógico (los bits de orden superior se rellenan con ceros).</span><span class="sxs-lookup"><span data-stu-id="c87d1-108">If the first operand is of type [uint](../keywords/uint.md) or [ulong](../keywords/ulong.md), the right-shift is a logical shift (high-order bits are zero-filled).</span></span>

<span data-ttu-id="c87d1-109">Los tipos definidos por el usuario pueden sobrecargar el operador `>>`; el tipo del primer operando debe ser el tipo definido por el usuario y el tipo del segundo operando debe ser [int](../keywords/int.md). Para obtener más información, vea [operator (Referencia de C#)](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="c87d1-109">User-defined types can overload the `>>` operator; the type of the first operand must be the user-defined type, and the type of the second operand must be [int](../keywords/int.md). For more information, see [operator](../keywords/operator.md).</span></span> <span data-ttu-id="c87d1-110">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="c87d1-110">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>

## <a name="example"></a><span data-ttu-id="c87d1-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c87d1-111">Example</span></span>

[!code-csharp[csRefOperators#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#26)]

## <a name="see-also"></a><span data-ttu-id="c87d1-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c87d1-112">See Also</span></span>

- [<span data-ttu-id="c87d1-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c87d1-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c87d1-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c87d1-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c87d1-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="c87d1-115">C# operators</span></span>](index.md)