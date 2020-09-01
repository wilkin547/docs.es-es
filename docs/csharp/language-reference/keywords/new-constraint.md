---
description: 'Restricción new: Referencia de C#'
title: 'Restricción new: Referencia de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: f7b097729fe973aba7b85c48e1b1033aade83080
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139455"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="fe19b-103">Restricción new (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="fe19b-103">new constraint (C# Reference)</span></span>

<span data-ttu-id="fe19b-104">La restricción `new` especifica que un tipo de argumento en una declaración de clase genérica debe tener un constructor sin parámetros público.</span><span class="sxs-lookup"><span data-stu-id="fe19b-104">The `new` constraint specifies that a type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="fe19b-105">Para usar la restricción `new`, el tipo no puede ser abstracto.</span><span class="sxs-lookup"><span data-stu-id="fe19b-105">To use the `new` constraint, the type cannot be abstract.</span></span>

<span data-ttu-id="fe19b-106">Aplique la restricción `new` a un tipo de parámetro cuando una clase genérica cree otras instancias del tipo, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fe19b-106">Apply the `new` constraint to a type parameter when a generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

<span data-ttu-id="fe19b-107">Cuando use la restricción `new()` con otras restricciones, se debe especificar en último lugar:</span><span class="sxs-lookup"><span data-stu-id="fe19b-107">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="fe19b-108">Para obtener más información, vea [Restricciones de tipos de parámetros](../../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="fe19b-108">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="fe19b-109">También puede usar la palabra clave `new` para [crear una instancia de un tipo](../operators/new-operator.md) o como un [modificador de declaración de miembro](new-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="fe19b-109">You can also use the `new` keyword to [create an instance of a type](../operators/new-operator.md) or as a [member declaration modifier](new-modifier.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fe19b-110">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="fe19b-110">C# language specification</span></span>

<span data-ttu-id="fe19b-111">Para más información, vea la sección [Restricciones de parámetros de tipo](~/_csharplang/spec/classes.md#type-parameter-constraints) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="fe19b-111">For more information, see the [Type parameter constraints](~/_csharplang/spec/classes.md#type-parameter-constraints) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fe19b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe19b-112">See also</span></span>

- [<span data-ttu-id="fe19b-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="fe19b-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fe19b-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fe19b-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fe19b-115">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="fe19b-115">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="fe19b-116">Genéricos</span><span class="sxs-lookup"><span data-stu-id="fe19b-116">Generics</span></span>](../../programming-guide/generics/index.md)
