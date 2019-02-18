---
title: '>>Operador =:Referencia de C#'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 51914bb5e9ebffd5d868528b5a8d3072a956cea6
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220918"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="281be-102">Operador >>= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="281be-102">>>= operator (C# Reference)</span></span>

<span data-ttu-id="281be-103">Operador de asignación de desplazamiento a la derecha.</span><span class="sxs-lookup"><span data-stu-id="281be-103">The right-shift assignment operator.</span></span>

<span data-ttu-id="281be-104">Una expresión que usa el operador `>>=`, como</span><span class="sxs-lookup"><span data-stu-id="281be-104">An expression using the `>>=` operator, such as</span></span>

```csharp
x >>= y
```

<span data-ttu-id="281be-105">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="281be-105">is equivalent to</span></span>

```csharp
x = x >> y
```

<span data-ttu-id="281be-106">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="281be-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="281be-107">El [operador `>>`](right-shift-operator.md) desplaza su primer operando a la derecha el número de bits definido por su segundo operando.</span><span class="sxs-lookup"><span data-stu-id="281be-107">The [`>>` operator](right-shift-operator.md) shifts its first operand right by the number of bits defined by its second operand.</span></span>

<span data-ttu-id="281be-108">En el siguiente ejemplo se muestra el uso del operador `>>=`:</span><span class="sxs-lookup"><span data-stu-id="281be-108">The following example demonstrates the usage of the `>>=` operator:</span></span>

[!code-csharp-interactive[right shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShiftAssignment)]

## <a name="operator-overloadability"></a><span data-ttu-id="281be-109">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="281be-109">Operator overloadability</span></span>

<span data-ttu-id="281be-110">Si un tipo definido por el usuario [sobrecarga](../keywords/operator.md) el [operador `>>`](right-shift-operator.md), el operador de asignación de desplazamiento a la derecha `>>=` se sobrecarga de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="281be-110">If a user-defined type [overloads](../keywords/operator.md) the [`>>` operator](right-shift-operator.md), the right-shift assignment operator `>>=` is implicitly overloaded.</span></span> <span data-ttu-id="281be-111">Un tipo definido por el usuario no puede sobrecargar de forma explícita el operador de asignación de desplazamiento a la derecha.</span><span class="sxs-lookup"><span data-stu-id="281be-111">A user-defined type cannot explicitly overload the right-shift assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="281be-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="281be-112">C# language specification</span></span>

<span data-ttu-id="281be-113">Para obtener más información, vea la sección [Asignación compuesta](~/_csharplang/spec/expressions.md#compound-assignment) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="281be-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="281be-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="281be-114">See also</span></span>

- [<span data-ttu-id="281be-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="281be-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="281be-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="281be-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="281be-117">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="281be-117">C# operators</span></span>](index.md)