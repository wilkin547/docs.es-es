---
title: value (Palabra clave contextual, Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: 84d0c51ddafb59144f4ba8c6e73412642fa8fa28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712902"
---
# <a name="value-c-reference"></a><span data-ttu-id="992a4-102">value (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="992a4-102">value (C# Reference)</span></span>

<span data-ttu-id="992a4-103">La palabra clave contextual `value` se usa en el descriptor de acceso `set` de las declaraciones [propiedad](../../programming-guide/classes-and-structs/properties.md) y [indizador](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="992a4-103">The contextual keyword `value` is used in the `set` accessor in [property](../../programming-guide/classes-and-structs/properties.md) and [indexer](../../programming-guide/indexers/index.md) declarations.</span></span> <span data-ttu-id="992a4-104">Es parecido a un parámetro de entrada de un método.</span><span class="sxs-lookup"><span data-stu-id="992a4-104">It is similar to an input parameter of a method.</span></span> <span data-ttu-id="992a4-105">El término `value` hace referencia al valor que el código de cliente intenta asignar a la propiedad o indizador.</span><span class="sxs-lookup"><span data-stu-id="992a4-105">The word `value` references the value that client code is attempting to assign to the property or indexer.</span></span> <span data-ttu-id="992a4-106">En el ejemplo siguiente, `MyDerivedClass` tiene una propiedad denominada `Name` que usa el parámetro `value` para asignar una nueva cadena al campo de respaldo `name`.</span><span class="sxs-lookup"><span data-stu-id="992a4-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="992a4-107">Desde el punto de vista del código de cliente, la operación se escribe como una simple asignación.</span><span class="sxs-lookup"><span data-stu-id="992a4-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="992a4-108">Para obtener más información, consulte los artículos [Propiedades](../../programming-guide/classes-and-structs/properties.md) e [Indizadores](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="992a4-108">For more information, see the [Properties](../../programming-guide/classes-and-structs/properties.md) and [Indexeres](../../programming-guide/indexers/index.md) articles.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="992a4-109">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="992a4-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="992a4-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="992a4-110">See also</span></span>

- [<span data-ttu-id="992a4-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="992a4-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="992a4-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="992a4-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="992a4-113">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="992a4-113">C# Keywords</span></span>](index.md)
