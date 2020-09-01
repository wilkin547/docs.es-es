---
description: value (Palabra clave contextual, Referencia de C#)
title: value (Palabra clave contextual, Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: f72e9f097880d9de725a85a0973001baaefd9a9c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141743"
---
# <a name="value-c-reference"></a><span data-ttu-id="78133-103">value (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="78133-103">value (C# Reference)</span></span>

<span data-ttu-id="78133-104">La palabra clave contextual `value` se usa en el descriptor de acceso `set` de las declaraciones [propiedad](../../programming-guide/classes-and-structs/properties.md) y [indizador](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="78133-104">The contextual keyword `value` is used in the `set` accessor in [property](../../programming-guide/classes-and-structs/properties.md) and [indexer](../../programming-guide/indexers/index.md) declarations.</span></span> <span data-ttu-id="78133-105">Es parecido a un parámetro de entrada de un método.</span><span class="sxs-lookup"><span data-stu-id="78133-105">It is similar to an input parameter of a method.</span></span> <span data-ttu-id="78133-106">El término `value` hace referencia al valor que el código de cliente intenta asignar a la propiedad o indizador.</span><span class="sxs-lookup"><span data-stu-id="78133-106">The word `value` references the value that client code is attempting to assign to the property or indexer.</span></span> <span data-ttu-id="78133-107">En el ejemplo siguiente, `MyDerivedClass` tiene una propiedad denominada `Name` que usa el parámetro `value` para asignar una nueva cadena al campo de respaldo `name`.</span><span class="sxs-lookup"><span data-stu-id="78133-107">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="78133-108">Desde el punto de vista del código de cliente, la operación se escribe como una simple asignación.</span><span class="sxs-lookup"><span data-stu-id="78133-108">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="78133-109">Para obtener más información, consulte los artículos [Propiedades](../../programming-guide/classes-and-structs/properties.md) e [Indizadores](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="78133-109">For more information, see the [Properties](../../programming-guide/classes-and-structs/properties.md) and [Indexeres](../../programming-guide/indexers/index.md) articles.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="78133-110">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="78133-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="78133-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="78133-111">See also</span></span>

- [<span data-ttu-id="78133-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="78133-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="78133-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="78133-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="78133-114">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="78133-114">C# Keywords</span></span>](index.md)
