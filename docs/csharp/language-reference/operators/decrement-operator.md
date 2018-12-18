---
title: -- Operador - Referencia de C#
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 4fba014e8dabc13cd874e17f23515dc29d93f24b
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236933"
---
# <a name="---operator-c-reference"></a><span data-ttu-id="d3a14-102">Operador -- (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d3a14-102">-- Operator (C# Reference)</span></span>

<span data-ttu-id="d3a14-103">El operador de decremento unario `--` disminuye su operando en 1.</span><span class="sxs-lookup"><span data-stu-id="d3a14-103">The unary decrement operator `--` decrements its operand by 1.</span></span> <span data-ttu-id="d3a14-104">Se admite en dos formas: el operador de decremento de postfijo ( `x--`) y el operador de decremento de prefijo (`--x`).</span><span class="sxs-lookup"><span data-stu-id="d3a14-104">It's supported in two forms: the postfix decrement operator, `x--`, and the prefix decrement operator, `--x`.</span></span>

## <a name="postfix-decrement-operator"></a><span data-ttu-id="d3a14-105">Operador de decremento de postfijo</span><span class="sxs-lookup"><span data-stu-id="d3a14-105">Postfix decrement operator</span></span>

<span data-ttu-id="d3a14-106">El resultado de `x--` es el valor de `x` *antes* de la operación, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3a14-106">The result of `x--` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix decrement](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PostfixDecrement)]

## <a name="prefix-decrement-operator"></a><span data-ttu-id="d3a14-107">Operador de decremento de prefijo</span><span class="sxs-lookup"><span data-stu-id="d3a14-107">Prefix decrement operator</span></span>

<span data-ttu-id="d3a14-108">El resultado de `--x` es el valor de `x` *después* de la operación, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3a14-108">The result of `--x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix decrement](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PrefixDecrement)]

## <a name="remarks"></a><span data-ttu-id="d3a14-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3a14-109">Remarks</span></span>

<span data-ttu-id="d3a14-110">El operador de decremento está predefinido para todos los [tipos enteros](../keywords/integral-types-table.md) (incluido el tipo [char](../keywords/char.md)), los [tipos de punto flotante](../keywords/floating-point-types-table.md) y cualquier tipo [enum](../keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="d3a14-110">The decrement operator is predefined for all [integral types](../keywords/integral-types-table.md) (including the [char](../keywords/char.md) type), [floating-point types](../keywords/floating-point-types-table.md), and any [enum](../keywords/enum.md) type.</span></span>

<span data-ttu-id="d3a14-111">Un operando del operador de decremento debe ser una variable, un acceso de [propiedad](../../programming-guide/classes-and-structs/properties.md) o un de [indizador](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="d3a14-111">An operand of the decrement operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../../csharp/programming-guide/indexers/index.md) access.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="d3a14-112">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="d3a14-112">Operator overloadability</span></span>

<span data-ttu-id="d3a14-113">Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `--`.</span><span class="sxs-lookup"><span data-stu-id="d3a14-113">User-defined types can [overload](../keywords/operator.md) the `--` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d3a14-114">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d3a14-114">C# language specification</span></span>

<span data-ttu-id="d3a14-115">Para más información, vea las secciones [Operadores postfijos de incremento y decremento](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) y [Prefijo de incremento y decremento de operadores](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) de la [Especificación del lenguaje C# ](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d3a14-115">For more information, see the [Postfix increment and decrement operators](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) and [Prefix increment and decrement operators](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d3a14-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3a14-116">See also</span></span>

- [<span data-ttu-id="d3a14-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d3a14-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d3a14-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d3a14-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d3a14-119">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="d3a14-119">C# Operators</span></span>](index.md)
- [<span data-ttu-id="d3a14-120">Operador ++</span><span class="sxs-lookup"><span data-stu-id="d3a14-120">++ Operator</span></span>](increment-operator.md)
- [<span data-ttu-id="d3a14-121">Aumento y disminución de punteros</span><span class="sxs-lookup"><span data-stu-id="d3a14-121">How to: increment and decrement pointers</span></span>](../../programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
