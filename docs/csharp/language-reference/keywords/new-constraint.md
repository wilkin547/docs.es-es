---
title: 'Restricción new: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 32fcb13e1f217707d53300c532169b1a1759fa7e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633408"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="bdab2-102">Restricción new (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="bdab2-102">new constraint (C# Reference)</span></span>

<span data-ttu-id="bdab2-103">La restricción `new` especifica que cualquier tipo de argumento en una declaración de clase genérica debe tener un constructor sin parámetros público.</span><span class="sxs-lookup"><span data-stu-id="bdab2-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="bdab2-104">Para usar la restricción new, el tipo no puede ser abstracto.</span><span class="sxs-lookup"><span data-stu-id="bdab2-104">To use the new constraint, the type cannot be abstract.</span></span>

## <a name="example"></a><span data-ttu-id="bdab2-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bdab2-105">Example</span></span>

<span data-ttu-id="bdab2-106">Aplique la restricción `new` a un tipo de parámetro cuando la clase genérica cree otras instancias del tipo, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bdab2-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

## <a name="example"></a><span data-ttu-id="bdab2-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bdab2-107">Example</span></span>

<span data-ttu-id="bdab2-108">Cuando use la restricción `new()` con otras restricciones, se debe especificar en último lugar:</span><span class="sxs-lookup"><span data-stu-id="bdab2-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="bdab2-109">Para obtener más información, vea [Restricciones de tipos de parámetros](../../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="bdab2-109">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bdab2-110">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="bdab2-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="bdab2-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdab2-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="bdab2-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="bdab2-112">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="bdab2-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="bdab2-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bdab2-114">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="bdab2-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="bdab2-115">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="bdab2-115">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="bdab2-116">Genéricos</span><span class="sxs-lookup"><span data-stu-id="bdab2-116">Generics</span></span>](../../programming-guide/generics/index.md)
