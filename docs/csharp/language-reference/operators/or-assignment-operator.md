---
title: 'Operador |=: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: f4f7806c8679af400a371decd0c367929b3fb81d
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333270"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="33731-102">Operador |= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="33731-102">|= operator (C# Reference)</span></span>

<span data-ttu-id="33731-103">El operador de asignación OR.</span><span class="sxs-lookup"><span data-stu-id="33731-103">The OR assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="33731-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33731-104">Remarks</span></span>

<span data-ttu-id="33731-105">Una expresión que use el operador de asignación `|=`, como</span><span class="sxs-lookup"><span data-stu-id="33731-105">An expression using the `|=` assignment operator, such as</span></span>

```csharp
x |= y
```

<span data-ttu-id="33731-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="33731-106">is equivalent to</span></span>

```csharp
x = x | y
```

<span data-ttu-id="33731-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="33731-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="33731-108">El [operador &#124;](or-operator.md) realiza una operación lógica OR bit a bit sobre operandos integrales y una operación lógica OR sobre operandos de tipo bool.</span><span class="sxs-lookup"><span data-stu-id="33731-108">The [&#124; operator](or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>

<span data-ttu-id="33731-109">El operador `|=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador &#124;](or-operator.md) (vea [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="33731-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](or-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="33731-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33731-110">Example</span></span>

[!code-csharp[csRefOperators#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#10)]

## <a name="see-also"></a><span data-ttu-id="33731-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="33731-111">See also</span></span>

- [<span data-ttu-id="33731-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="33731-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="33731-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="33731-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="33731-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="33731-114">C# operators</span></span>](index.md)