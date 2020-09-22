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
ms.openlocfilehash: 0445ac33473c7e2d1916705893b22ba21bb981ff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536851"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="f45cd-103">Tipo parcial (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f45cd-103">partial type (C# Reference)</span></span>

<span data-ttu-id="f45cd-104">Las definiciones de tipo parcial permiten dividir la definición de una clase, estructura o interfaz en varios archivos.</span><span class="sxs-lookup"><span data-stu-id="f45cd-104">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>

<span data-ttu-id="f45cd-105">En *File1.cs*:</span><span class="sxs-lookup"><span data-stu-id="f45cd-105">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="f45cd-106">La declaración en *File2.cs*:</span><span class="sxs-lookup"><span data-stu-id="f45cd-106">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="f45cd-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f45cd-107">Remarks</span></span>

<span data-ttu-id="f45cd-108">Dividir un tipo de clase, estructura o interfaz en varios archivos puede resultar útil cuando trabaja con proyectos de gran tamaño o con código generado automáticamente, como el proporcionado por el [Diseñador de Windows Forms](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time).</span><span class="sxs-lookup"><span data-stu-id="f45cd-108">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time).</span></span> <span data-ttu-id="f45cd-109">Un tipo parcial puede contener un [método parcial](partial-method.md).</span><span class="sxs-lookup"><span data-stu-id="f45cd-109">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="f45cd-110">Para más información, vea [Clases y métodos parciales](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="f45cd-110">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f45cd-111">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f45cd-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f45cd-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f45cd-112">See also</span></span>

- [<span data-ttu-id="f45cd-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f45cd-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f45cd-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f45cd-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f45cd-115">Modificadores</span><span class="sxs-lookup"><span data-stu-id="f45cd-115">Modifiers</span></span>](index.md)
- [<span data-ttu-id="f45cd-116">Introducción a los genéricos</span><span class="sxs-lookup"><span data-stu-id="f45cd-116">Introduction to Generics</span></span>](../../programming-guide/generics/index.md)
