---
title: '- operador: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 8cf6e8871a88e2b37b9531ecbd616289523473c7
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333764"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="ba401-102">Operador - (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ba401-102">- operator (C# Reference)</span></span>

<span data-ttu-id="ba401-103">El operador `-` puede funcionar como un operador unario o binario.</span><span class="sxs-lookup"><span data-stu-id="ba401-103">The `-` operator can function as either a unary or a binary operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba401-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ba401-104">Remarks</span></span>

<span data-ttu-id="ba401-105">Los operadores unarios `-` están predefinidos para todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="ba401-105">Unary `-` operators are predefined for all numeric types.</span></span> <span data-ttu-id="ba401-106">El resultado de una operación unaria `-` aplicada a un tipo numérico es la negación numérica del operando.</span><span class="sxs-lookup"><span data-stu-id="ba401-106">The result of a unary `-` operation on a numeric type is the numeric negation of the operand.</span></span>

<span data-ttu-id="ba401-107">Los operadores binarios `-` están predefinidos para todos los tipos numéricos y de enumeración de modo que restan el segundo operando del primero.</span><span class="sxs-lookup"><span data-stu-id="ba401-107">Binary `-` operators are predefined for all numeric and enumeration types to subtract the second operand from the first.</span></span>

<span data-ttu-id="ba401-108">Los tipos de delegado también proporcionan un operador `-` binario, que realiza la eliminación de delegados.</span><span class="sxs-lookup"><span data-stu-id="ba401-108">Delegate types also provide a binary `-` operator, which performs delegate removal.</span></span>

<span data-ttu-id="ba401-109">Los tipos definidos por el usuario pueden sobrecargar los operadores `-` unarios y `-` binarios.</span><span class="sxs-lookup"><span data-stu-id="ba401-109">User-defined types can overload the unary `-` and binary `-` operators.</span></span> <span data-ttu-id="ba401-110">Para más información, consulte [operator keyword](../keywords/operator.md) (Palabra clave operator).</span><span class="sxs-lookup"><span data-stu-id="ba401-110">For more information, see [operator keyword](../keywords/operator.md).</span></span>

## <a name="example"></a><span data-ttu-id="ba401-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba401-111">Example</span></span>

[!code-csharp[csRefOperators#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#40)]

## <a name="see-also"></a><span data-ttu-id="ba401-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba401-112">See also</span></span>

- [<span data-ttu-id="ba401-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="ba401-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ba401-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ba401-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ba401-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="ba401-115">C# operators</span></span>](index.md)