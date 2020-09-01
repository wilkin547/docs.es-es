---
description: 'Palabra clave checked: Referencia de C#'
title: 'Palabra clave checked: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- checked_CSharpKeyword
- checked
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
ms.openlocfilehash: 4dd8bc02d3af89d6bab3aef55a88cb8b40704da6
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138285"
---
# <a name="checked-c-reference"></a><span data-ttu-id="a50f4-103">checked (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a50f4-103">checked (C# Reference)</span></span>

<span data-ttu-id="a50f4-104">La palabra clave `checked` se usa con el fin de habilitar explícitamente la comprobación de desbordamiento para operaciones aritméticas y conversiones de tipo integral.</span><span class="sxs-lookup"><span data-stu-id="a50f4-104">The `checked` keyword is used to explicitly enable overflow checking for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="a50f4-105">De manera predeterminada, una expresión que solo contiene valores constantes provoca un error del compilador si la expresión genera un valor fuera del intervalo del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="a50f4-105">By default, an expression that contains only constant values causes a compiler error if the expression produces a value that is outside the range of the destination type.</span></span> <span data-ttu-id="a50f4-106">Si la expresión contiene uno o varios valores no constantes, el compilador no detecta el desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="a50f4-106">If the expression contains one or more non-constant values, the compiler does not detect the overflow.</span></span> <span data-ttu-id="a50f4-107">En el siguiente ejemplo, la evaluación de la expresión asignada a `i2` no genera un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="a50f4-107">Evaluating the expression assigned to `i2` in the following example does not cause a compiler error.</span></span>

[!code-csharp[csrefKeywordsChecked#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#3)]

<span data-ttu-id="a50f4-108">De manera predeterminada, estas expresiones no constantes no se someten a la comprobación de desbordamiento en tiempo de ejecución y no generan excepciones de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="a50f4-108">By default, these non-constant expressions are not checked for overflow at run time either, and they do not raise overflow exceptions.</span></span> <span data-ttu-id="a50f4-109">En el ejemplo anterior, se muestra -2 147 483 639 como la suma de dos enteros positivos.</span><span class="sxs-lookup"><span data-stu-id="a50f4-109">The previous example displays -2,147,483,639 as the sum of two positive integers.</span></span>

<span data-ttu-id="a50f4-110">La comprobación de desbordamiento se puede habilitar mediante opciones del compilador, la configuración del entorno o la palabra clave `checked`.</span><span class="sxs-lookup"><span data-stu-id="a50f4-110">Overflow checking can be enabled by compiler options, environment configuration, or use of the `checked` keyword.</span></span> <span data-ttu-id="a50f4-111">En los ejemplos siguientes, se muestra cómo usar una expresión `checked` o un bloque `checked` para detectar el desbordamiento generado por la suma anterior en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a50f4-111">The following examples demonstrate how to use a `checked` expression or a `checked` block to detect the overflow that is produced by the previous sum at run time.</span></span> <span data-ttu-id="a50f4-112">En ambos ejemplos se genera una excepción de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="a50f4-112">Both examples raise an overflow exception.</span></span>

[!code-csharp[csrefKeywordsChecked#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#4)]

<span data-ttu-id="a50f4-113">Se puede usar la palabra clave [unchecked](./unchecked.md) para evitar la comprobación de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="a50f4-113">The [unchecked](./unchecked.md) keyword can be used to prevent overflow checking.</span></span>

## <a name="example"></a><span data-ttu-id="a50f4-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a50f4-114">Example</span></span>

<span data-ttu-id="a50f4-115">En este ejemplo, se muestra cómo usar `checked` para habilitar la comprobación de desbordamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a50f4-115">This sample shows how to use `checked` to enable overflow checking at run time.</span></span>

[!code-csharp[csrefKeywordsChecked#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#1)]

## <a name="c-language-specification"></a><span data-ttu-id="a50f4-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a50f4-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a50f4-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a50f4-117">See also</span></span>

- [<span data-ttu-id="a50f4-118">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a50f4-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a50f4-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a50f4-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a50f4-120">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="a50f4-120">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="a50f4-121">Checked y unchecked</span><span class="sxs-lookup"><span data-stu-id="a50f4-121">Checked and Unchecked</span></span>](./checked-and-unchecked.md)
- [<span data-ttu-id="a50f4-122">unchecked</span><span class="sxs-lookup"><span data-stu-id="a50f4-122">unchecked</span></span>](./unchecked.md)
