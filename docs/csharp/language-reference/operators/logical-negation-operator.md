---
title: '! operador: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
ms.openlocfilehash: 6b6d1796032f536aac0be49d4f101c1380b4e98f
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333231"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="29499-103">!</span><span class="sxs-lookup"><span data-stu-id="29499-103">!</span></span> <span data-ttu-id="29499-104">operator (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="29499-104">operator (C# Reference)</span></span>

<span data-ttu-id="29499-105">El operador lógico de negación (`!`) es un operador unario que niega su operando.</span><span class="sxs-lookup"><span data-stu-id="29499-105">The logical negation operator (`!`) is a unary operator that negates its operand.</span></span> <span data-ttu-id="29499-106">Está definido para el tipo `bool` y devuelve `true` si, y solo si, su operando es `false`.</span><span class="sxs-lookup"><span data-stu-id="29499-106">It is defined for `bool` and returns `true` if and only if its operand is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="29499-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="29499-107">Remarks</span></span>

<span data-ttu-id="29499-108">Los tipos definidos por el usuario pueden sobrecargar el operador `!` (vea [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="29499-108">User-defined types can overload the `!` operator (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="29499-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="29499-109">Example</span></span>

[!code-csharp[csRefOperators#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#7)]

## <a name="see-also"></a><span data-ttu-id="29499-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="29499-110">See also</span></span>

- [<span data-ttu-id="29499-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="29499-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="29499-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="29499-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="29499-113">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="29499-113">C# Operators</span></span>](index.md)