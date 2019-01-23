---
title: 'Operador |: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 185ea3aabff4794ec08cca541773dbec3574ab4b
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333517"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="cce25-102">Operador| (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="cce25-102">| operator (C# Reference)</span></span>

<span data-ttu-id="cce25-103">Los operadores binarios `|` están predefinidos para los tipos enteros y `bool`.</span><span class="sxs-lookup"><span data-stu-id="cce25-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="cce25-104">Para los tipos enteros, `|` calcula OR bit a bit de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="cce25-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="cce25-105">Para operandos `bool`, `|` calcula el OR lógico de sus operandos; es decir, el resultado es `false` si y solo si ambos operandos son `false`.</span><span class="sxs-lookup"><span data-stu-id="cce25-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cce25-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cce25-106">Remarks</span></span>

<span data-ttu-id="cce25-107">El operador `|` binario evalúa ambos operandos con independencia del valor del primero, a diferencia del [operador OR condicional](conditional-or-operator.md) `||`.</span><span class="sxs-lookup"><span data-stu-id="cce25-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator](conditional-or-operator.md) `||`.</span></span>

<span data-ttu-id="cce25-108">Los tipos definidos por el usuario pueden sobrecargar el operador `|` (vea [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="cce25-108">User-defined types can overload the `|` operator (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="cce25-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cce25-109">Example</span></span>

 [!code-csharp[csRefOperators#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#31)]

## <a name="see-also"></a><span data-ttu-id="cce25-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="cce25-110">See also</span></span>

- [<span data-ttu-id="cce25-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="cce25-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cce25-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cce25-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cce25-113">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="cce25-113">C# operators</span></span>](index.md)