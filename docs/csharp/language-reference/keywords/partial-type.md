---
description: 'Tipo parcial: Referencia de C#'
title: 'Tipo parcial: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 4e73b34390143a2ac9b839e1da79b7894232c4b4
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2020
ms.locfileid: "91437886"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="8c027-103">Tipo parcial (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8c027-103">partial type (C# Reference)</span></span>

<span data-ttu-id="8c027-104">Las definiciones de tipo parcial permiten dividir la definición de una clase, estructura, interfaz o registro en varios archivos.</span><span class="sxs-lookup"><span data-stu-id="8c027-104">Partial type definitions allow for the definition of a class, struct, interface, or record to be split into multiple files.</span></span>

<span data-ttu-id="8c027-105">En *File1.cs*:</span><span class="sxs-lookup"><span data-stu-id="8c027-105">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="8c027-106">La declaración en *File2.cs*:</span><span class="sxs-lookup"><span data-stu-id="8c027-106">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="8c027-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8c027-107">Remarks</span></span>

<span data-ttu-id="8c027-108">Dividir un tipo de clase, estructura o interfaz en varios archivos puede resultar útil cuando trabaja con proyectos de gran tamaño o con código generado automáticamente, como el proporcionado por el [Diseñador de Windows Forms](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time).</span><span class="sxs-lookup"><span data-stu-id="8c027-108">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time).</span></span> <span data-ttu-id="8c027-109">Un tipo parcial puede contener un [método parcial](partial-method.md).</span><span class="sxs-lookup"><span data-stu-id="8c027-109">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="8c027-110">Para más información, vea [Clases y métodos parciales](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="8c027-110">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8c027-111">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="8c027-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="8c027-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c027-112">See also</span></span>

- [<span data-ttu-id="8c027-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="8c027-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8c027-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8c027-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8c027-115">Modificadores</span><span class="sxs-lookup"><span data-stu-id="8c027-115">Modifiers</span></span>](index.md)
- [<span data-ttu-id="8c027-116">Introducción a los genéricos</span><span class="sxs-lookup"><span data-stu-id="8c027-116">Introduction to Generics</span></span>](../../programming-guide/generics/index.md)
