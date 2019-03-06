---
title: '* operador: Referencia de C#'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: a5e120d26614f1e38cc2f2db02949552140b594e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977349"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c7ea3-102">Operador \* (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c7ea3-102">\* operator (C# Reference)</span></span>

<span data-ttu-id="c7ea3-103">El operador `*` se admite de dos formas: un operador de direccionamiento indirecto del puntero unario o un operador de multiplicación binario.</span><span class="sxs-lookup"><span data-stu-id="c7ea3-103">The `*` operator is supported in two forms: a unary pointer indirection operator or a binary multiplication operator.</span></span>

## <a name="pointer-indirection-operator"></a><span data-ttu-id="c7ea3-104">Operador de direccionamiento indirecto del puntero</span><span class="sxs-lookup"><span data-stu-id="c7ea3-104">Pointer indirection operator</span></span>

<span data-ttu-id="c7ea3-105">Use el operador unario `*` para obtener la variable a la que apunta un operando de un tipo de puntero.</span><span class="sxs-lookup"><span data-stu-id="c7ea3-105">Use the unary `*` operator to obtain the variable to which an operand of a pointer type points.</span></span> <span data-ttu-id="c7ea3-106">Para obtener más información, vea [Cómo: Obtener el valor de una variable de puntero](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md).</span><span class="sxs-lookup"><span data-stu-id="c7ea3-106">For more information, see [How to: obtain the value of a pointer variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md).</span></span>

<span data-ttu-id="c7ea3-107">El operador de direccionamiento indirecto del puntero `*` requiere el contexto [unsafe](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="c7ea3-107">The pointer indirection operator `*` requires [unsafe](../keywords/unsafe.md) context.</span></span>

## <a name="multiplication-operator"></a><span data-ttu-id="c7ea3-108">Operador de multiplicación</span><span class="sxs-lookup"><span data-stu-id="c7ea3-108">Multiplication operator</span></span>

<span data-ttu-id="c7ea3-109">En tipos numéricos, el operador `*` calcula la suma de sus operandos:</span><span class="sxs-lookup"><span data-stu-id="c7ea3-109">For numeric types, the `*` operator computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#Multiply)]

## <a name="operator-overloadability"></a><span data-ttu-id="c7ea3-110">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="c7ea3-110">Operator overloadability</span></span>

<span data-ttu-id="c7ea3-111">Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) un operador `*` binario.</span><span class="sxs-lookup"><span data-stu-id="c7ea3-111">User-defined types can [overload](../keywords/operator.md) a binary `*` operator.</span></span> <span data-ttu-id="c7ea3-112">Cuando se sobrecarga un operador `*` binario, el [operador de asignación de multiplicación](multiplication-assignment-operator.md) `*=` también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="c7ea3-112">When a binary `*` operator is overloaded, the [multiplication assignment operator](multiplication-assignment-operator.md) `*=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c7ea3-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c7ea3-113">C# language specification</span></span>

<span data-ttu-id="c7ea3-114">Para obtener más información, consulte las secciones de [direccionamiento indirecto del puntero](~/_csharplang/spec/unsafe-code.md#pointer-indirection) y del [operador de multiplicación](~/_csharplang/spec/expressions.md#multiplication-operator) de la [especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="c7ea3-114">For more information, see the [Pointer indirection](~/_csharplang/spec/unsafe-code.md#pointer-indirection) and [Multiplication operator](~/_csharplang/spec/expressions.md#multiplication-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c7ea3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7ea3-115">See also</span></span>

- [<span data-ttu-id="c7ea3-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c7ea3-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c7ea3-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c7ea3-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c7ea3-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="c7ea3-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="c7ea3-119">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="c7ea3-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)