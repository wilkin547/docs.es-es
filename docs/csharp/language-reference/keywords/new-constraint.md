---
title: 'Restricción new: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 2aa68bec13322e332bfe3841bc99403f72301183
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421803"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="bcfc7-102">Restricción new (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="bcfc7-102">new constraint (C# Reference)</span></span>

<span data-ttu-id="bcfc7-103">La restricción `new` especifica que cualquier tipo de argumento en una declaración de clase genérica debe tener un constructor sin parámetros público.</span><span class="sxs-lookup"><span data-stu-id="bcfc7-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="bcfc7-104">Para usar la restricción new, el tipo no puede ser abstracto.</span><span class="sxs-lookup"><span data-stu-id="bcfc7-104">To use the new constraint, the type cannot be abstract.</span></span>

## <a name="example"></a><span data-ttu-id="bcfc7-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bcfc7-105">Example</span></span>

<span data-ttu-id="bcfc7-106">Aplique la restricción `new` a un tipo de parámetro cuando la clase genérica cree otras instancias del tipo, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bcfc7-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

## <a name="example"></a><span data-ttu-id="bcfc7-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bcfc7-107">Example</span></span>

<span data-ttu-id="bcfc7-108">Cuando use la restricción `new()` con otras restricciones, se debe especificar en último lugar:</span><span class="sxs-lookup"><span data-stu-id="bcfc7-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="bcfc7-109">Para obtener más información, vea [Restricciones de tipos de parámetros](../../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="bcfc7-109">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bcfc7-110">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="bcfc7-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="bcfc7-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcfc7-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="bcfc7-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="bcfc7-112">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="bcfc7-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="bcfc7-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bcfc7-114">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="bcfc7-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="bcfc7-115">Genéricos</span><span class="sxs-lookup"><span data-stu-id="bcfc7-115">Generics</span></span>](../../programming-guide/generics/index.md)
