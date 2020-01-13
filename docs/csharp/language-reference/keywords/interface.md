---
title: 'interface: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 19ca4b8a490dc85de0d0e2be6d3ca8fa7982fc14
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713449"
---
# <a name="interface-c-reference"></a><span data-ttu-id="4046f-102">interface (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4046f-102">interface (C# Reference)</span></span>

<span data-ttu-id="4046f-103">Una interfaz contiene solo las firmas de [métodos](../../programming-guide/classes-and-structs/methods.md), [propiedades](../../programming-guide/classes-and-structs/properties.md), [eventos](../../programming-guide/events/index.md) o [indizadores](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="4046f-103">An interface contains only the signatures of [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [events](../../programming-guide/events/index.md) or [indexers](../../programming-guide/indexers/index.md).</span></span> <span data-ttu-id="4046f-104">Una clase o struct que implemente la interfaz debe implementar los miembros de la interfaz que se especifican en la definición de interfaz.</span><span class="sxs-lookup"><span data-stu-id="4046f-104">A class or struct that implements the interface must implement the members of the interface that are specified in the interface definition.</span></span> <span data-ttu-id="4046f-105">En el ejemplo siguiente, la clase `ImplementationClass` debe implementar un método denominado `SampleMethod` que no tiene ningún parámetro y devuelve `void`.</span><span class="sxs-lookup"><span data-stu-id="4046f-105">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>

<span data-ttu-id="4046f-106">Para obtener más información y ejemplos, vea [Interfaces](../../programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="4046f-106">For more information and examples, see [Interfaces](../../programming-guide/interfaces/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="4046f-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4046f-107">Example</span></span>

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

<span data-ttu-id="4046f-108">Una interfaz puede ser miembro de un espacio de nombres o de una clase, y puede contener signaturas de los siguientes miembros:</span><span class="sxs-lookup"><span data-stu-id="4046f-108">An interface can be a member of a namespace or a class and can contain signatures of the following members:</span></span>

- [<span data-ttu-id="4046f-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="4046f-109">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="4046f-110">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4046f-110">Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)

- [<span data-ttu-id="4046f-111">Indizadores</span><span class="sxs-lookup"><span data-stu-id="4046f-111">Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)

- [<span data-ttu-id="4046f-112">Eventos</span><span class="sxs-lookup"><span data-stu-id="4046f-112">Events</span></span>](event.md)

<span data-ttu-id="4046f-113">Una interfaz puede heredar de una o varias interfaces base.</span><span class="sxs-lookup"><span data-stu-id="4046f-113">An interface can inherit from one or more base interfaces.</span></span>

<span data-ttu-id="4046f-114">Cuando una lista de tipos base contiene una clase e interfaces base, la clase base debe aparecer primero en la lista.</span><span class="sxs-lookup"><span data-stu-id="4046f-114">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>

<span data-ttu-id="4046f-115">Una clase que implementa una interfaz puede implementar explícitamente miembros de esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="4046f-115">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="4046f-116">A un miembro implementado explícitamente solo se puede tener acceso mediante una instancia de la interfaz, y no mediante una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="4046f-116">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span>

<span data-ttu-id="4046f-117">Para obtener más información detallada y ejemplos de código de la implementación de interfaces explícita, vea [Implementación de interfaz explícita](../../programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="4046f-117">For more details and code examples on explicit interface implementation, see [Explicit Interface Implementation](../../programming-guide/interfaces/explicit-interface-implementation.md).</span></span>

## <a name="example"></a><span data-ttu-id="4046f-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4046f-118">Example</span></span>

<span data-ttu-id="4046f-119">En el ejemplo siguiente se muestra la implementación de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="4046f-119">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="4046f-120">En este ejemplo, la interfaz contiene la declaración de propiedad y la clase contiene la implementación.</span><span class="sxs-lookup"><span data-stu-id="4046f-120">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="4046f-121">Cualquier instancia de una clase que implemente `IPoint` tiene las propiedades de entero `x` e `y`.</span><span class="sxs-lookup"><span data-stu-id="4046f-121">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a><span data-ttu-id="4046f-122">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4046f-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="4046f-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="4046f-123">See also</span></span>

- [<span data-ttu-id="4046f-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="4046f-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4046f-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4046f-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4046f-126">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="4046f-126">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="4046f-127">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="4046f-127">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="4046f-128">Interfaces</span><span class="sxs-lookup"><span data-stu-id="4046f-128">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
- [<span data-ttu-id="4046f-129">Utilizar propiedades</span><span class="sxs-lookup"><span data-stu-id="4046f-129">Using Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="4046f-130">Utilizar indizadores</span><span class="sxs-lookup"><span data-stu-id="4046f-130">Using Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
- [<span data-ttu-id="4046f-131">class</span><span class="sxs-lookup"><span data-stu-id="4046f-131">class</span></span>](class.md)
- [<span data-ttu-id="4046f-132">struct</span><span class="sxs-lookup"><span data-stu-id="4046f-132">struct</span></span>](struct.md)
- [<span data-ttu-id="4046f-133">Interfaces</span><span class="sxs-lookup"><span data-stu-id="4046f-133">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
