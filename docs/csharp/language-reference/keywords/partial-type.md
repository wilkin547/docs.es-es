---
title: Tipo parcial (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 365d00d2c53d3efe1cd4330bdd3ec48740a49c53
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43422334"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="d7d4d-102">Tipo parcial (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d7d4d-102">partial type (C# Reference)</span></span>

<span data-ttu-id="d7d4d-103">Las definiciones de tipo parcial permiten dividir la definición de una clase, estructura o interfaz en varios archivos.</span><span class="sxs-lookup"><span data-stu-id="d7d4d-103">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>

<span data-ttu-id="d7d4d-104">En *File1.cs*:</span><span class="sxs-lookup"><span data-stu-id="d7d4d-104">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="d7d4d-105">La declaración en *File2.cs*:</span><span class="sxs-lookup"><span data-stu-id="d7d4d-105">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="d7d4d-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d7d4d-106">Remarks</span></span>

<span data-ttu-id="d7d4d-107">Dividir un tipo de clase, estructura o interfaz en varios archivos puede resultar útil cuando trabaja con proyectos de gran tamaño o con código generado automáticamente, como el proporcionado por el [Diseñador de Windows Forms](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="d7d4d-107">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span> <span data-ttu-id="d7d4d-108">Un tipo parcial puede contener un [método parcial](partial-method.md).</span><span class="sxs-lookup"><span data-stu-id="d7d4d-108">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="d7d4d-109">Para más información, vea [Clases y métodos parciales](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="d7d4d-109">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d7d4d-110">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d7d4d-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d7d4d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7d4d-111">See also</span></span>

- [<span data-ttu-id="d7d4d-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d7d4d-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d7d4d-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d7d4d-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d7d4d-114">Modificadores</span><span class="sxs-lookup"><span data-stu-id="d7d4d-114">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="d7d4d-115">Introducción a los genéricos</span><span class="sxs-lookup"><span data-stu-id="d7d4d-115">Introduction to Generics</span></span>](../../programming-guide/generics/introduction-to-generics.md)