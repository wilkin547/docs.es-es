---
title: unchecked (palabra clave) - Referencia de C#
ms.date: 07/20/2015
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
ms.openlocfilehash: 6dad0dfd508fb390dd0a52d1b48d70b4c5725513
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713006"
---
# <a name="unchecked-c-reference"></a><span data-ttu-id="40141-102">unchecked (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="40141-102">unchecked (C# Reference)</span></span>

<span data-ttu-id="40141-103">La palabra clave `unchecked` se usa para suprimir la comprobación de desbordamiento en las operaciones y conversiones aritméticas de tipos enteros.</span><span class="sxs-lookup"><span data-stu-id="40141-103">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="40141-104">En un contexto unchecked, si una expresión genera un valor que está fuera del intervalo del tipo de destino, no se marca el desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="40141-104">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="40141-105">Por ejemplo, dado que el cálculo del siguiente ejemplo se realiza en un bloque o una expresión `unchecked`, el hecho de que el resultado sea demasiado grande para un entero se omite y se asigna a `int1` el valor -2 147 483 639.</span><span class="sxs-lookup"><span data-stu-id="40141-105">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>

[!code-csharp[csrefKeywordsChecked#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#5)]

<span data-ttu-id="40141-106">Si se quita el entorno `unchecked`, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="40141-106">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="40141-107">El desbordamiento se puede detectar en tiempo de compilación porque todos los términos de la expresión son constantes.</span><span class="sxs-lookup"><span data-stu-id="40141-107">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>

<span data-ttu-id="40141-108">Las expresiones que contienen términos no constantes son unchecked de forma predeterminada en tiempo de compilación y tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="40141-108">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="40141-109">Vea [checked](checked.md) para obtener información sobre cómo habilitar un entorno checked.</span><span class="sxs-lookup"><span data-stu-id="40141-109">See [checked](checked.md) for information about enabling a checked environment.</span></span>

<span data-ttu-id="40141-110">Puesto que la comprobación de desbordamiento lleva tiempo, el uso del código unchecked en situaciones donde no hay riesgo de desbordamiento puede mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="40141-110">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="40141-111">Pero si el desbordamiento es una posibilidad, se debe usar un entorno checked.</span><span class="sxs-lookup"><span data-stu-id="40141-111">However, if overflow is a possibility, a checked environment should be used.</span></span>

## <a name="example"></a><span data-ttu-id="40141-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="40141-112">Example</span></span>

<span data-ttu-id="40141-113">En este ejemplo se muestra cómo usar la palabra clave `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="40141-113">This sample shows how to use the `unchecked` keyword.</span></span>

[!code-csharp[csrefKeywordsChecked#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="40141-114">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="40141-114">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="40141-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="40141-115">See also</span></span>

- [<span data-ttu-id="40141-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="40141-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="40141-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="40141-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="40141-118">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="40141-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="40141-119">Checked y Unchecked</span><span class="sxs-lookup"><span data-stu-id="40141-119">Checked and Unchecked</span></span>](checked-and-unchecked.md)
- [<span data-ttu-id="40141-120">checked</span><span class="sxs-lookup"><span data-stu-id="40141-120">checked</span></span>](checked.md)
