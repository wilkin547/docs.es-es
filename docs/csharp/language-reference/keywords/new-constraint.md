---
title: 'Restricción new: Referencia de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 6f6d1b663d03dc9b3adf0e7055dcffacc79d83dc
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795344"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="67234-102">Restricción new (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="67234-102">new constraint (C# Reference)</span></span>

<span data-ttu-id="67234-103">La restricción `new` especifica que un tipo de argumento en una declaración de clase genérica debe tener un constructor sin parámetros público.</span><span class="sxs-lookup"><span data-stu-id="67234-103">The `new` constraint specifies that a type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="67234-104">Para usar la restricción `new`, el tipo no puede ser abstracto.</span><span class="sxs-lookup"><span data-stu-id="67234-104">To use the `new` constraint, the type cannot be abstract.</span></span>

<span data-ttu-id="67234-105">Aplique la restricción `new` a un tipo de parámetro cuando una clase genérica cree otras instancias del tipo, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="67234-105">Apply the `new` constraint to a type parameter when a generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

<span data-ttu-id="67234-106">Cuando use la restricción `new()` con otras restricciones, se debe especificar en último lugar:</span><span class="sxs-lookup"><span data-stu-id="67234-106">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="67234-107">Para obtener más información, vea [Restricciones de tipos de parámetros](../../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="67234-107">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="67234-108">También puede usar la palabra clave `new` para [crear una instancia de un tipo](../operators/new-operator.md) o como un [modificador de declaración de miembro](new-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="67234-108">You can also use the `new` keyword to [create an instance of a type](../operators/new-operator.md) or as a [member declaration modifier](new-modifier.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="67234-109">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="67234-109">C# language specification</span></span>

<span data-ttu-id="67234-110">Para más información, vea la sección [Restricciones de parámetros de tipo](~/_csharplang/spec/classes.md#type-parameter-constraints) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="67234-110">For more information, see the [Type parameter constraints](~/_csharplang/spec/classes.md#type-parameter-constraints) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="67234-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="67234-111">See also</span></span>

- [<span data-ttu-id="67234-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="67234-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="67234-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="67234-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="67234-114">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="67234-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="67234-115">Genéricos</span><span class="sxs-lookup"><span data-stu-id="67234-115">Generics</span></span>](../../programming-guide/generics/index.md)
