---
title: 'Matrices con asignación implícita de tipos: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], implicitly-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
ms.openlocfilehash: 943760af30422cd333fdff65cdf678108c9d9564
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705722"
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a><span data-ttu-id="2700c-102">Matrices con asignación implícita de tipos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="2700c-102">Implicitly Typed Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="2700c-103">Puede crear una matriz con tipo implícito en la que se deduce el tipo de la instancia de matriz de los elementos especificados en el inicializador de matriz.</span><span class="sxs-lookup"><span data-stu-id="2700c-103">You can create an implicitly-typed array in which the type of the array instance is inferred from the elements specified in the array initializer.</span></span> <span data-ttu-id="2700c-104">Las reglas de cualquier variable con tipo implícito también se aplican a las matrices con tipo implícito.</span><span class="sxs-lookup"><span data-stu-id="2700c-104">The rules for any implicitly-typed variable also apply to implicitly-typed arrays.</span></span> <span data-ttu-id="2700c-105">Para más información, vea [Variables locales con asignación implícita de tipos](../classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="2700c-105">For more information, see [Implicitly Typed Local Variables](../classes-and-structs/implicitly-typed-local-variables.md).</span></span>

<span data-ttu-id="2700c-106">Normalmente, se usan matrices con tipo implícito en expresiones de consulta junto con tipos anónimos e inicializadores de objeto y colección.</span><span class="sxs-lookup"><span data-stu-id="2700c-106">Implicitly-typed arrays are usually used in query expressions together with anonymous types and object and collection initializers.</span></span>

<span data-ttu-id="2700c-107">En los ejemplos siguientes, se muestra cómo crear una matriz con tipo implícito:</span><span class="sxs-lookup"><span data-stu-id="2700c-107">The following examples show how to create an implicitly-typed array:</span></span>

[!code-csharp[csProgGuideLINQ#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#37)]

<span data-ttu-id="2700c-108">En el ejemplo anterior observe que, con las matrices con tipo implícito, no se usan corchetes en el lado izquierdo de la instrucción de inicialización.</span><span class="sxs-lookup"><span data-stu-id="2700c-108">In the previous example, notice that with implicitly-typed arrays, no square brackets are used on the left side of the initialization statement.</span></span> <span data-ttu-id="2700c-109">Tenga en cuenta también que las matrices escalonadas se inicializan mediante `new []` al igual que las matrices unidimensionales.</span><span class="sxs-lookup"><span data-stu-id="2700c-109">Note also that jagged arrays are initialized by using `new []` just like single-dimension arrays.</span></span>

## <a name="implicitly-typed-arrays-in-object-initializers"></a><span data-ttu-id="2700c-110">Matrices con tipo implícito en inicializadores de objeto</span><span class="sxs-lookup"><span data-stu-id="2700c-110">Implicitly-typed Arrays in Object Initializers</span></span>

<span data-ttu-id="2700c-111">Al crear un tipo anónimo que contiene una matriz, esta debe tener tipo implícito en el inicializador de objeto del tipo.</span><span class="sxs-lookup"><span data-stu-id="2700c-111">When you create an anonymous type that contains an array, the array must be implicitly typed in the type's object initializer.</span></span> <span data-ttu-id="2700c-112">En el ejemplo siguiente, `contacts` es una matriz con tipos implícitos anónimos, cada uno de los cuales contiene una matriz denominada `PhoneNumbers`.</span><span class="sxs-lookup"><span data-stu-id="2700c-112">In the following example, `contacts` is an implicitly-typed array of anonymous types, each of which contains an array named `PhoneNumbers`.</span></span> <span data-ttu-id="2700c-113">Tenga en cuenta que la palabra clave `var` no se usa dentro de los inicializadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="2700c-113">Note that the `var` keyword is not used inside the object initializers.</span></span>

[!code-csharp[csProgGuideLINQ#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#38)]

## <a name="see-also"></a><span data-ttu-id="2700c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2700c-114">See also</span></span>

- [<span data-ttu-id="2700c-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2700c-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2700c-116">Variables locales con asignación implícita de tipos</span><span class="sxs-lookup"><span data-stu-id="2700c-116">Implicitly Typed Local Variables</span></span>](../classes-and-structs/implicitly-typed-local-variables.md)
- [<span data-ttu-id="2700c-117">Matrices</span><span class="sxs-lookup"><span data-stu-id="2700c-117">Arrays</span></span>](./index.md)
- [<span data-ttu-id="2700c-118">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="2700c-118">Anonymous Types</span></span>](../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="2700c-119">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="2700c-119">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)
- [<span data-ttu-id="2700c-120">var</span><span class="sxs-lookup"><span data-stu-id="2700c-120">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="2700c-121">LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="2700c-121">LINQ in C#</span></span>](../../linq/index.md)
