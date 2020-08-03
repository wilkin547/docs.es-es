---
title: 'Matrices con asignación implícita de tipos: Guía de programación de C#'
description: El tipo de una matriz con tipo implícito en C# se infiere de los elementos del inicializador de matriz. Use matrices con tipo implícito en las expresiones de consulta.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], implicitly-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
ms.openlocfilehash: 1f14f68207dfb79c92eaa01ac2a8ffaa08facc03
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474714"
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a><span data-ttu-id="e72ce-104">Matrices con asignación implícita de tipos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="e72ce-104">Implicitly Typed Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="e72ce-105">Puede crear una matriz con tipo implícito en la que se deduce el tipo de la instancia de matriz de los elementos especificados en el inicializador de matriz.</span><span class="sxs-lookup"><span data-stu-id="e72ce-105">You can create an implicitly-typed array in which the type of the array instance is inferred from the elements specified in the array initializer.</span></span> <span data-ttu-id="e72ce-106">Las reglas de cualquier variable con tipo implícito también se aplican a las matrices con tipo implícito.</span><span class="sxs-lookup"><span data-stu-id="e72ce-106">The rules for any implicitly-typed variable also apply to implicitly-typed arrays.</span></span> <span data-ttu-id="e72ce-107">Para más información, vea [Variables locales con asignación implícita de tipos](../classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="e72ce-107">For more information, see [Implicitly Typed Local Variables](../classes-and-structs/implicitly-typed-local-variables.md).</span></span>

<span data-ttu-id="e72ce-108">Normalmente, se usan matrices con tipo implícito en expresiones de consulta junto con tipos anónimos e inicializadores de objeto y colección.</span><span class="sxs-lookup"><span data-stu-id="e72ce-108">Implicitly-typed arrays are usually used in query expressions together with anonymous types and object and collection initializers.</span></span>

<span data-ttu-id="e72ce-109">En los ejemplos siguientes, se muestra cómo crear una matriz con tipo implícito:</span><span class="sxs-lookup"><span data-stu-id="e72ce-109">The following examples show how to create an implicitly-typed array:</span></span>

[!code-csharp[csProgGuideLINQ#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#37)]

<span data-ttu-id="e72ce-110">En el ejemplo anterior observe que, con las matrices con tipo implícito, no se usan corchetes en el lado izquierdo de la instrucción de inicialización.</span><span class="sxs-lookup"><span data-stu-id="e72ce-110">In the previous example, notice that with implicitly-typed arrays, no square brackets are used on the left side of the initialization statement.</span></span> <span data-ttu-id="e72ce-111">Tenga en cuenta también que las matrices escalonadas se inicializan mediante `new []` al igual que las matrices unidimensionales.</span><span class="sxs-lookup"><span data-stu-id="e72ce-111">Note also that jagged arrays are initialized by using `new []` just like single-dimension arrays.</span></span>

## <a name="implicitly-typed-arrays-in-object-initializers"></a><span data-ttu-id="e72ce-112">Matrices con tipo implícito en inicializadores de objeto</span><span class="sxs-lookup"><span data-stu-id="e72ce-112">Implicitly-typed Arrays in Object Initializers</span></span>

<span data-ttu-id="e72ce-113">Al crear un tipo anónimo que contiene una matriz, esta debe tener tipo implícito en el inicializador de objeto del tipo.</span><span class="sxs-lookup"><span data-stu-id="e72ce-113">When you create an anonymous type that contains an array, the array must be implicitly typed in the type's object initializer.</span></span> <span data-ttu-id="e72ce-114">En el ejemplo siguiente, `contacts` es una matriz con tipos implícitos anónimos, cada uno de los cuales contiene una matriz denominada `PhoneNumbers`.</span><span class="sxs-lookup"><span data-stu-id="e72ce-114">In the following example, `contacts` is an implicitly-typed array of anonymous types, each of which contains an array named `PhoneNumbers`.</span></span> <span data-ttu-id="e72ce-115">Tenga en cuenta que la palabra clave `var` no se usa dentro de los inicializadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="e72ce-115">Note that the `var` keyword is not used inside the object initializers.</span></span>

[!code-csharp[csProgGuideLINQ#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#38)]

## <a name="see-also"></a><span data-ttu-id="e72ce-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e72ce-116">See also</span></span>

- [<span data-ttu-id="e72ce-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e72ce-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e72ce-118">Variables locales con asignación implícita de tipos</span><span class="sxs-lookup"><span data-stu-id="e72ce-118">Implicitly Typed Local Variables</span></span>](../classes-and-structs/implicitly-typed-local-variables.md)
- [<span data-ttu-id="e72ce-119">Matrices</span><span class="sxs-lookup"><span data-stu-id="e72ce-119">Arrays</span></span>](./index.md)
- [<span data-ttu-id="e72ce-120">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="e72ce-120">Anonymous Types</span></span>](../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="e72ce-121">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="e72ce-121">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)
- [<span data-ttu-id="e72ce-122">var</span><span class="sxs-lookup"><span data-stu-id="e72ce-122">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="e72ce-123">LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="e72ce-123">LINQ in C#</span></span>](../../linq/index.md)
