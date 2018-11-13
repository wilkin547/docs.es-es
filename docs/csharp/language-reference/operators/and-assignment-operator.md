---
title: Operador &amp;= (Referencia de C#)
ms.date: 10/29/2018
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: 8ce27c999cf21a9059ba23ee3c86b8fa024c7341
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "50980614"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="4e0df-102">Operador &amp;= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4e0df-102">&amp;= Operator (C# Reference)</span></span>

<span data-ttu-id="4e0df-103">El operador de asignación AND.</span><span class="sxs-lookup"><span data-stu-id="4e0df-103">The AND assignment operator.</span></span>

<span data-ttu-id="4e0df-104">Una expresión que usa el operador `&=`, como</span><span class="sxs-lookup"><span data-stu-id="4e0df-104">An expression using the `&=` operator, such as</span></span>

```csharp
x &= y
```

<span data-ttu-id="4e0df-105">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="4e0df-105">is equivalent to</span></span>

```csharp
x = x & y
```

<span data-ttu-id="4e0df-106">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="4e0df-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="4e0df-107">Para los operandos enteros, el [operador `&`](and-operator.md) calcula el AND lógico bit a bit de sus operandos; para los operandos [bool](../keywords/bool.md), calcula el AND lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="4e0df-107">For integer operands, the [`&` operator](and-operator.md) computes the bitwise logical AND of its operands; for [bool](../keywords/bool.md) operands, it computes the logical AND of its operands.</span></span>

<span data-ttu-id="4e0df-108">En el siguiente ejemplo se muestra el uso del operador `&=`:</span><span class="sxs-lookup"><span data-stu-id="4e0df-108">The following example demonstrates the usage of the `&=` operator:</span></span>

[!code-csharp-interactive[AND assignment example](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#AndAssignmentExample)]

## <a name="operator-overloadability"></a><span data-ttu-id="4e0df-109">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="4e0df-109">Operator overloadability</span></span>

<span data-ttu-id="4e0df-110">Si un tipo definido por el usuario [sobrecarga](../keywords/operator.md) el [operador `&`](and-operator.md), el operador de asignación AND `&=` se sobrecarga de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="4e0df-110">If a user-defined type [overloads](../keywords/operator.md) the [`&` operator](and-operator.md), the AND assignment operator `&=` is implicitly overloaded.</span></span> <span data-ttu-id="4e0df-111">Un tipo definido por el usuario no puede sobrecargar de forma implícita el operador de asignación AND.</span><span class="sxs-lookup"><span data-stu-id="4e0df-111">A user-defined type cannot explicitly overload the AND assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4e0df-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4e0df-112">C# language specification</span></span>

<span data-ttu-id="4e0df-113">Para obtener más información, vea la sección [Asignación compuesta](~/_csharplang/spec/expressions.md#compound-assignment) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="4e0df-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4e0df-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e0df-114">See also</span></span>

- [<span data-ttu-id="4e0df-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="4e0df-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4e0df-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4e0df-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4e0df-117">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="4e0df-117">C# Operators</span></span>](index.md)
