---
title: 'object: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- object_CSharpKeyword
- object
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
ms.openlocfilehash: a1917a7925d4ed90ede40248fa394f9c45d09b4e
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238985"
---
# <a name="object-c-reference"></a><span data-ttu-id="9174c-102">object (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9174c-102">object (C# Reference)</span></span>

<span data-ttu-id="9174c-103">El tipo `object` es un alias de <xref:System.Object> en .NET.</span><span class="sxs-lookup"><span data-stu-id="9174c-103">The `object` type is an alias for <xref:System.Object> in .NET.</span></span> <span data-ttu-id="9174c-104">En el sistema de tipos unificado de C#, todos los tipos, los predefinidos y los definidos por el usuario, los tipos de referencia y los tipos de valores, heredan directa o indirectamente de <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="9174c-104">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span> <span data-ttu-id="9174c-105">Puede asignar valores de cualquier tipo a las variables de tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="9174c-105">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="9174c-106">Cuando una variable de un tipo de valor se convierte en objeto, se dice que se aplica la *conversión boxing*.</span><span class="sxs-lookup"><span data-stu-id="9174c-106">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="9174c-107">Cuando una variable de tipo de objeto se convierte en un tipo de valor, se dice que se aplica la *conversión unboxing*.</span><span class="sxs-lookup"><span data-stu-id="9174c-107">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="9174c-108">Para obtener más información, vea [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md) (Conversión boxing y conversión unboxing [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="9174c-108">For more information, see [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>

## <a name="example"></a><span data-ttu-id="9174c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9174c-109">Example</span></span>

<span data-ttu-id="9174c-110">El siguiente ejemplo muestra cómo las variables de tipo `object` pueden aceptar valores de cualquier tipo de datos y cómo las variables de tipo `object` pueden usar métodos en <xref:System.Object> desde .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9174c-110">The following sample shows how variables of type `object` can accept values of any data type and how variables of type `object` can use methods on <xref:System.Object> from the .NET Framework.</span></span>

[!code-csharp[csrefKeywordsTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#16)]

## <a name="c-language-specification"></a><span data-ttu-id="9174c-111">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="9174c-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="9174c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9174c-112">See also</span></span>

- [<span data-ttu-id="9174c-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9174c-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9174c-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9174c-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9174c-115">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="9174c-115">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="9174c-116">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="9174c-116">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="9174c-117">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="9174c-117">Value Types</span></span>](value-types.md)