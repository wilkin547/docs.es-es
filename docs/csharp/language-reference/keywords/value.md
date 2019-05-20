---
title: value (Palabra clave contextual, Referencia de C#)
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: cfd370df771998057fd421a0917b3e2fcd96d9f8
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633037"
---
# <a name="value-c-reference"></a><span data-ttu-id="5e856-102">value (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5e856-102">value (C# Reference)</span></span>

<span data-ttu-id="5e856-103">La palabra clave contextual `value` se usa en el descriptor de acceso set de las declaraciones de propiedad normales.</span><span class="sxs-lookup"><span data-stu-id="5e856-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="5e856-104">Es similar a un parámetro de entrada de un método.</span><span class="sxs-lookup"><span data-stu-id="5e856-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="5e856-105">El término `value` hace referencia al valor que el código de cliente intenta asignar a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="5e856-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="5e856-106">En el ejemplo siguiente, `MyDerivedClass` tiene una propiedad denominada `Name` que usa el parámetro `value` para asignar una nueva cadena al campo de respaldo `name`.</span><span class="sxs-lookup"><span data-stu-id="5e856-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="5e856-107">Desde el punto de vista del código de cliente, la operación se escribe como una simple asignación.</span><span class="sxs-lookup"><span data-stu-id="5e856-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="5e856-108">Para obtener más información sobre el uso de `value`, vea [Propiedades](../../programming-guide/classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="5e856-108">For more information about the use of `value`, see [Properties](../../programming-guide/classes-and-structs/properties.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5e856-109">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5e856-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5e856-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e856-110">See also</span></span>

- [<span data-ttu-id="5e856-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="5e856-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5e856-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5e856-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5e856-113">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="5e856-113">C# Keywords</span></span>](index.md)
