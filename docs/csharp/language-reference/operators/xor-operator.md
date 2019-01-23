---
title: 'Operador ^: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
ms.openlocfilehash: 152be2d81d1bf340b839d74f169d63d7260f7ca5
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333712"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="019d4-102">Operador ^ (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="019d4-102">^ operator (C# Reference)</span></span>

<span data-ttu-id="019d4-103">Los operadores binarios `^` están predefinidos para los tipos enteros y `bool`.</span><span class="sxs-lookup"><span data-stu-id="019d4-103">Binary `^` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="019d4-104">Para los tipos enteros, `^` calcula OR exclusiva bit a bit de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="019d4-104">For integral types, `^` computes the bitwise exclusive-OR of its operands.</span></span> <span data-ttu-id="019d4-105">Para operandos `bool`, `^` calcula OR exclusiva lógica de sus operandos; es decir, el resultado es `true` si y solo si exactamente uno de sus operandos es `true`.</span><span class="sxs-lookup"><span data-stu-id="019d4-105">For `bool` operands, `^` computes the logical exclusive-or of its operands; that is, the result is `true` if and only if exactly one of its operands is `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="019d4-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="019d4-106">Remarks</span></span>

<span data-ttu-id="019d4-107">Los tipos definidos por el usuario pueden sobrecargar el operador `^` (vea [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="019d4-107">User-defined types can overload the `^` operator (see [operator](../keywords/operator.md)).</span></span> <span data-ttu-id="019d4-108">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="019d4-108">Operations on integral types are generally allowed on enumeration.</span></span>

## <a name="example"></a><span data-ttu-id="019d4-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="019d4-109">Example</span></span>

[!code-csharp[csRefOperators#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#30)]

<span data-ttu-id="019d4-110">El cálculo de `0xf8 ^ 0x3f` en el ejemplo anterior realiza una operación OR exclusiva bit a bit de los siguientes dos valores binarios, que corresponden a los valores hexadecimales F8 y 3F:</span><span class="sxs-lookup"><span data-stu-id="019d4-110">The computation of `0xf8 ^ 0x3f` in the previous example performs a bitwise exclusive-OR of the following two binary values, which correspond to the hexadecimal values F8 and 3F:</span></span>

`1111 1000`

`0011 1111`

<span data-ttu-id="019d4-111">El resultado de la OR exclusiva es `1100 0111`, que es C7 en hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="019d4-111">The result of the exclusive-OR is `1100 0111`, which is C7 in hexadecimal.</span></span>

## <a name="see-also"></a><span data-ttu-id="019d4-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="019d4-112">See Also</span></span>

- [<span data-ttu-id="019d4-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="019d4-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="019d4-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="019d4-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="019d4-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="019d4-115">C# operators</span></span>](index.md)
