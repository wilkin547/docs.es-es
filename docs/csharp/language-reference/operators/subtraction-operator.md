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
ms.openlocfilehash: 920981addd5c779c9ad1c666ef45e1de5cd23408
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633002"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="06dea-102">Operador - (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="06dea-102">- operator (C# Reference)</span></span>

<span data-ttu-id="06dea-103">El operador `-` puede funcionar como un operador unario o binario.</span><span class="sxs-lookup"><span data-stu-id="06dea-103">The `-` operator can function as either a unary or a binary operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="06dea-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06dea-104">Remarks</span></span>

<span data-ttu-id="06dea-105">Los operadores unarios `-` están predefinidos para todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="06dea-105">Unary `-` operators are predefined for all numeric types.</span></span> <span data-ttu-id="06dea-106">El resultado de una operación unaria `-` aplicada a un tipo numérico es la negación numérica del operando.</span><span class="sxs-lookup"><span data-stu-id="06dea-106">The result of a unary `-` operation on a numeric type is the numeric negation of the operand.</span></span>

<span data-ttu-id="06dea-107">Los operadores binarios `-` están predefinidos para todos los tipos numéricos y de enumeración de modo que restan el segundo operando del primero.</span><span class="sxs-lookup"><span data-stu-id="06dea-107">Binary `-` operators are predefined for all numeric and enumeration types to subtract the second operand from the first.</span></span>

<span data-ttu-id="06dea-108">Los tipos de delegado también proporcionan un operador `-` binario, que realiza la eliminación de delegados.</span><span class="sxs-lookup"><span data-stu-id="06dea-108">Delegate types also provide a binary `-` operator, which performs delegate removal.</span></span>

<span data-ttu-id="06dea-109">Los tipos definidos por el usuario pueden sobrecargar los operadores `-` unarios y `-` binarios.</span><span class="sxs-lookup"><span data-stu-id="06dea-109">User-defined types can overload the unary `-` and binary `-` operators.</span></span> <span data-ttu-id="06dea-110">Para más información, consulte [operator keyword](../keywords/operator.md) (Palabra clave operator).</span><span class="sxs-lookup"><span data-stu-id="06dea-110">For more information, see [operator keyword](../keywords/operator.md).</span></span>

## <a name="example"></a><span data-ttu-id="06dea-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06dea-111">Example</span></span>

[!code-csharp[csRefOperators#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#40)]

## <a name="see-also"></a><span data-ttu-id="06dea-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="06dea-112">See also</span></span>

- [<span data-ttu-id="06dea-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="06dea-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="06dea-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="06dea-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="06dea-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="06dea-115">C# operators</span></span>](index.md)
