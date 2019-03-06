---
title: 'Operador *=: Referencia de C#'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 70461f79e714e44354fe4137e5360769fa048d3e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967391"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="89f0d-102">Operador \*= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="89f0d-102">\*= Operator (C# Reference)</span></span>

<span data-ttu-id="89f0d-103">Operador de asignación de multiplicación.</span><span class="sxs-lookup"><span data-stu-id="89f0d-103">The multiplication assignment operator.</span></span>

<span data-ttu-id="89f0d-104">Una expresión que usa el operador `*=`, como</span><span class="sxs-lookup"><span data-stu-id="89f0d-104">An expression using the `*=` operator, such as</span></span>

```csharp
x *= y
```

<span data-ttu-id="89f0d-105">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="89f0d-105">is equivalent to</span></span>

```csharp
x = x * y
```

<span data-ttu-id="89f0d-106">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="89f0d-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="89f0d-107">Para tipos numéricos, el [operador \*](multiplication-operator.md) calcula la suma de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="89f0d-107">For numeric types, the [\* operator](multiplication-operator.md) computes the product of its operands.</span></span>

<span data-ttu-id="89f0d-108">En el siguiente ejemplo se muestra el uso del operador `*=`:</span><span class="sxs-lookup"><span data-stu-id="89f0d-108">The following example demonstrates the usage of the `*=` operator:</span></span>

[!code-csharp-interactive[multiply and assign](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#MultiplyAndAssign)]

## <a name="operator-overloadability"></a><span data-ttu-id="89f0d-109">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="89f0d-109">Operator overloadability</span></span>

<span data-ttu-id="89f0d-110">Si un tipo definido por el usuario [sobrecarga](../keywords/operator.md) el [operador de multiplicación](multiplication-operator.md) `*`, el operador de asignación de multiplicación `*=` se sobrecarga implícitamente.</span><span class="sxs-lookup"><span data-stu-id="89f0d-110">If a user-defined type [overloads](../keywords/operator.md) the [multiplication operator](multiplication-operator.md) `*`, the multiplication assignment operator `*=` is implicitly overloaded.</span></span> <span data-ttu-id="89f0d-111">Un tipo definido por el usuario no puede sobrecargar de forma implícita el operador de asignación de multiplicación.</span><span class="sxs-lookup"><span data-stu-id="89f0d-111">A user-defined type cannot explicitly overload the multiplication assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="89f0d-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="89f0d-112">C# language specification</span></span>

<span data-ttu-id="89f0d-113">Para obtener más información, vea la sección [Asignación compuesta](~/_csharplang/spec/expressions.md#compound-assignment) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="89f0d-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="89f0d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="89f0d-114">See also</span></span>

- [<span data-ttu-id="89f0d-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="89f0d-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="89f0d-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="89f0d-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="89f0d-117">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="89f0d-117">C# Operators</span></span>](index.md)
