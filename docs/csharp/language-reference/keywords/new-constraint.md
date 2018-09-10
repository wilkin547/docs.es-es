---
title: Restricción new (Referencia de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 9948fc65030a4636c5d23db4ef8c3a584018d2f5
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087016"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="f0af6-102">Restricción new (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f0af6-102">new constraint (C# Reference)</span></span>

<span data-ttu-id="f0af6-103">La restricción `new` especifica que cualquier tipo de argumento en una declaración de clase genérica debe tener un constructor sin parámetros público.</span><span class="sxs-lookup"><span data-stu-id="f0af6-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="f0af6-104">Para usar la restricción new, el tipo no puede ser abstracto.</span><span class="sxs-lookup"><span data-stu-id="f0af6-104">To use the new constraint, the type cannot be abstract.</span></span>

## <a name="example"></a><span data-ttu-id="f0af6-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f0af6-105">Example</span></span>

<span data-ttu-id="f0af6-106">Aplique la restricción `new` a un tipo de parámetro cuando la clase genérica cree otras instancias del tipo, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0af6-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

## <a name="example"></a><span data-ttu-id="f0af6-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f0af6-107">Example</span></span>

<span data-ttu-id="f0af6-108">Cuando use la restricción `new()` con otras restricciones, se debe especificar en último lugar:</span><span class="sxs-lookup"><span data-stu-id="f0af6-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="f0af6-109">Para obtener más información, vea [Restricciones de tipos de parámetros](../../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="f0af6-109">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f0af6-110">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f0af6-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f0af6-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0af6-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="f0af6-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f0af6-112">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="f0af6-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f0af6-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f0af6-114">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="f0af6-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f0af6-115">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="f0af6-115">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="f0af6-116">Genéricos</span><span class="sxs-lookup"><span data-stu-id="f0af6-116">Generics</span></span>](../../programming-guide/generics/index.md)