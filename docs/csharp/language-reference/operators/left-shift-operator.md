---
title: 'Operador &lt;&lt;: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: 79a48d88e2c83b5ad78804367ee3c07f78622c08
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333530"
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="e3861-102">Operador &lt;&lt; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="e3861-102">&lt;&lt; operator (C# Reference)</span></span>

<span data-ttu-id="e3861-103">El operador de desplazamiento a la izquierda (`<<`) desplaza su primer operando a la izquierda el número de bits especificado por su segundo operando.</span><span class="sxs-lookup"><span data-stu-id="e3861-103">The left-shift operator (`<<`) shifts its first operand left by the number of bits specified by its second operand.</span></span> <span data-ttu-id="e3861-104">El tipo del segundo operando debe ser [int](../keywords/int.md) o un tipo que tiene una conversión numérica implícita predefinida en `int`.</span><span class="sxs-lookup"><span data-stu-id="e3861-104">The type of the second operand must be an [int](../keywords/int.md) or a type that has a predefined implicit numeric conversion to `int`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3861-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e3861-105">Remarks</span></span>

<span data-ttu-id="e3861-106">Si el primer operando es [int](../keywords/int.md) o [uint](../keywords/uint.md) (cantidad de 32 bits), el valor de desplazamiento viene dado por los cinco bits de orden inferior del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="e3861-106">If the first operand is an [int](../keywords/int.md) or [uint](../keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand.</span></span> <span data-ttu-id="e3861-107">Es decir, el recuento de desplazamiento real es de 0 a 31 bits.</span><span class="sxs-lookup"><span data-stu-id="e3861-107">That is, the actual shift count is 0 to 31 bits.</span></span>

<span data-ttu-id="e3861-108">Si el primer operando es [long](../keywords/long.md) o [ulong](../keywords/ulong.md) (cantidad de 64 bits), el valor de desplazamiento viene dado por los seis bits de orden inferior del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="e3861-108">If the first operand is a [long](../keywords/long.md) or [ulong](../keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand.</span></span> <span data-ttu-id="e3861-109">Es decir, el recuento de desplazamiento real es de 0 a 63 bits.</span><span class="sxs-lookup"><span data-stu-id="e3861-109">That is, the actual shift count is 0 to 63 bits.</span></span>

<span data-ttu-id="e3861-110">Se descartan los bits de orden superior que no están dentro del intervalo del tipo del primer operando después del desplazamiento y se rellenan con ceros los bits vacíos de orden inferior.</span><span class="sxs-lookup"><span data-stu-id="e3861-110">Any high-order bits that are not within the range of the type of the first operand after the shift are discarded, and the low-order empty bits are zero-filled.</span></span> <span data-ttu-id="e3861-111">Las operaciones de desplazamiento nunca producen desbordamientos.</span><span class="sxs-lookup"><span data-stu-id="e3861-111">Shift operations never cause overflows.</span></span>

<span data-ttu-id="e3861-112">Los tipos definidos por el usuario pueden sobrecargar el operador `<<` (vea [operator](../keywords/operator.md)); el tipo del primer operando debe ser el tipo definido por el usuario y el tipo del segundo operando debe ser `int`.</span><span class="sxs-lookup"><span data-stu-id="e3861-112">User-defined types can overload the `<<` operator (see [operator](../keywords/operator.md)); the type of the first operand must be the user-defined type, and the type of the second operand must be `int`.</span></span> <span data-ttu-id="e3861-113">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="e3861-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>

## <a name="example"></a><span data-ttu-id="e3861-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e3861-114">Example</span></span>

[!code-csharp[csRefOperators#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#14)]

## <a name="comments"></a><span data-ttu-id="e3861-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e3861-115">Comments</span></span>

<span data-ttu-id="e3861-116">Tenga en cuenta que `i<<1` y `i<<33` dan el mismo resultado, ya que 1 y 33 tienen los mismos cinco bits de orden inferior.</span><span class="sxs-lookup"><span data-stu-id="e3861-116">Note that `i<<1` and `i<<33` give the same result, because 1 and 33 have the same low-order five bits.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3861-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3861-117">See also</span></span>

- [<span data-ttu-id="e3861-118">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="e3861-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e3861-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e3861-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e3861-120">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="e3861-120">C# Operators</span></span>](index.md)
