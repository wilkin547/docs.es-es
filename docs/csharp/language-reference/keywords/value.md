---
description: value (Palabra clave contextual, Referencia de C#)
title: value (Palabra clave contextual, Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: ad2eb6f12d8c295dc5203994d6c570cd2377e3ee
ms.sourcegitcommit: 43ed174f085840ca18a791dc89fe833174da766d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90828921"
---
# <a name="value-c-reference"></a><span data-ttu-id="7e368-103">value (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="7e368-103">value (C# Reference)</span></span>

<span data-ttu-id="7e368-104">La palabra clave contextual `value` se usa en el descriptor de acceso `set` de las declaraciones [propiedad](../../programming-guide/classes-and-structs/properties.md) y [indizador](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="7e368-104">The contextual keyword `value` is used in the `set` accessor in [property](../../programming-guide/classes-and-structs/properties.md) and [indexer](../../programming-guide/indexers/index.md) declarations.</span></span> <span data-ttu-id="7e368-105">Es parecido a un parámetro de entrada de un método.</span><span class="sxs-lookup"><span data-stu-id="7e368-105">It is similar to an input parameter of a method.</span></span> <span data-ttu-id="7e368-106">El término `value` hace referencia al valor que el código de cliente intenta asignar a la propiedad o indizador.</span><span class="sxs-lookup"><span data-stu-id="7e368-106">The word `value` references the value that client code is attempting to assign to the property or indexer.</span></span> <span data-ttu-id="7e368-107">En el ejemplo siguiente, `MyDerivedClass` tiene una propiedad denominada `Name` que usa el parámetro `value` para asignar una nueva cadena al campo de respaldo `name`.</span><span class="sxs-lookup"><span data-stu-id="7e368-107">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="7e368-108">Desde el punto de vista del código de cliente, la operación se escribe como una simple asignación.</span><span class="sxs-lookup"><span data-stu-id="7e368-108">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="7e368-109">Para obtener más información, vea los artículos [Propiedades](../../programming-guide/classes-and-structs/properties.md) e [Indizadores](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="7e368-109">For more information, see the [Properties](../../programming-guide/classes-and-structs/properties.md) and [Indexers](../../programming-guide/indexers/index.md) articles.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7e368-110">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="7e368-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7e368-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e368-111">See also</span></span>

- [<span data-ttu-id="7e368-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="7e368-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7e368-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7e368-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7e368-114">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="7e368-114">C# Keywords</span></span>](index.md)
