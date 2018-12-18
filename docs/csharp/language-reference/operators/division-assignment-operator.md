---
title: 'Operador /=: Referencia de C#'
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: ed4dd6c0c944b77543aae4de8d51534b4df4f4ef
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286525"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="79221-102">/= (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="79221-102">/= Operator (C# Reference)</span></span>

<span data-ttu-id="79221-103">Operador de asignación y división.</span><span class="sxs-lookup"><span data-stu-id="79221-103">The division assignment operator.</span></span>

<span data-ttu-id="79221-104">Una expresión que usa el operador `/=`, como</span><span class="sxs-lookup"><span data-stu-id="79221-104">An expression using the `/=` operator, such as</span></span>

```csharp
x /= y
```

<span data-ttu-id="79221-105">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="79221-105">is equivalent to</span></span>

```csharp
x = x / y
```

<span data-ttu-id="79221-106">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="79221-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="79221-107">El [operador de división](division-operator.md) `/` divide su primer operando por su segundo operando.</span><span class="sxs-lookup"><span data-stu-id="79221-107">The [division operator](division-operator.md) `/` divides its first operand by its second operand.</span></span> <span data-ttu-id="79221-108">Es compatible con todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="79221-108">It's supported by all numeric types.</span></span>

<span data-ttu-id="79221-109">En el siguiente ejemplo se muestra el uso del operador `/=`:</span><span class="sxs-lookup"><span data-stu-id="79221-109">The following example demonstrates the usage of the `/=` operator:</span></span>

[!code-csharp-interactive[divide and assign](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#DivisionAssignment)]

## <a name="operator-overloadability"></a><span data-ttu-id="79221-110">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="79221-110">Operator overloadability</span></span>

<span data-ttu-id="79221-111">Si un tipo definido por el usuario [sobrecarga](../keywords/operator.md) el [operador de división](division-operator.md) `/`, el operador de asignación de división `/=` se sobrecarga implícitamente.</span><span class="sxs-lookup"><span data-stu-id="79221-111">If a user-defined type [overloads](../keywords/operator.md) the [division operator](division-operator.md) `/`, the division assignment operator `/=` is implicitly overloaded.</span></span> <span data-ttu-id="79221-112">Un tipo definido por el usuario no puede sobrecargar de forma explícita el operador de asignación de división.</span><span class="sxs-lookup"><span data-stu-id="79221-112">A user-defined type cannot explicitly overload the division assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="79221-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="79221-113">C# language specification</span></span>

<span data-ttu-id="79221-114">Para obtener más información, vea la sección [Asignación compuesta](~/_csharplang/spec/expressions.md#compound-assignment) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="79221-114">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="79221-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="79221-115">See also</span></span>

- [<span data-ttu-id="79221-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="79221-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="79221-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="79221-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="79221-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="79221-118">C# Operators</span></span>](index.md)
