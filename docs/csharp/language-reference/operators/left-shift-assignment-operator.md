---
title: 'Operador <<=: Referencia de C#'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: d2105fbee4ddfe1b2cb3325d82b0f2f8c5559297
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219456"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1bf18-102">Operador \<\<= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="1bf18-102">\<\<= operator (C# Reference)</span></span>

<span data-ttu-id="1bf18-103">Operador de asignación de desplazamiento a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="1bf18-103">The left-shift assignment operator.</span></span>

<span data-ttu-id="1bf18-104">Una expresión que usa el operador `<<=`, como</span><span class="sxs-lookup"><span data-stu-id="1bf18-104">An expression using the `<<=` operator, such as</span></span>

```csharp
x <<= y
```

<span data-ttu-id="1bf18-105">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="1bf18-105">is equivalent to</span></span>

```csharp
x = x << y
```

<span data-ttu-id="1bf18-106">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="1bf18-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="1bf18-107">El [operador `<<`](left-shift-operator.md) desplaza su primer operando a la izquierda el número de bits definido por su segundo operando.</span><span class="sxs-lookup"><span data-stu-id="1bf18-107">The [`<<` operator](left-shift-operator.md) shifts its first operand left by the number of bits defined by its second operand.</span></span>

<span data-ttu-id="1bf18-108">En el siguiente ejemplo se muestra el uso del operador `<<=`:</span><span class="sxs-lookup"><span data-stu-id="1bf18-108">The following example demonstrates the usage of the `<<=` operator:</span></span>

[!code-csharp-interactive[left shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShiftAssignment)]

## <a name="operator-overloadability"></a><span data-ttu-id="1bf18-109">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="1bf18-109">Operator overloadability</span></span>

<span data-ttu-id="1bf18-110">Si un tipo definido por el usuario [sobrecarga](../keywords/operator.md) el [operador `<<`](left-shift-operator.md), el operador de asignación de desplazamiento a la izquierda `<<=` se sobrecarga de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="1bf18-110">If a user-defined type [overloads](../keywords/operator.md) the [`<<` operator](left-shift-operator.md), the left-shift assignment operator `<<=` is implicitly overloaded.</span></span> <span data-ttu-id="1bf18-111">Un tipo definido por el usuario no puede sobrecargar de forma explícita el operador de asignación de desplazamiento a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="1bf18-111">A user-defined type cannot explicitly overload the left-shift assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1bf18-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="1bf18-112">C# language specification</span></span>

<span data-ttu-id="1bf18-113">Para obtener más información, vea la sección [Asignación compuesta](~/_csharplang/spec/expressions.md#compound-assignment) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="1bf18-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1bf18-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bf18-114">See also</span></span>

- [<span data-ttu-id="1bf18-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="1bf18-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1bf18-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1bf18-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1bf18-117">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="1bf18-117">C# Operators</span></span>](index.md)
