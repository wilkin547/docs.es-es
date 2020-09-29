---
title: 'Interfaces genéricas: Guía de programación de C#'
description: Aprenda a usar interfaces genéricas en C#. Vea ejemplos de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
ms.openlocfilehash: ec86395a41baea75694572b59b2c76cbde24fedf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170394"
---
# <a name="generic-interfaces-c-programming-guide"></a><span data-ttu-id="901c5-104">Interfaces genéricas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="901c5-104">Generic Interfaces (C# Programming Guide)</span></span>

<span data-ttu-id="901c5-105">A menudo es útil definir interfaces para las clases de colección genéricas o para las clases genéricas que representan los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="901c5-105">It is often useful to define interfaces either for generic collection classes, or for the generic classes that represent items in the collection.</span></span> <span data-ttu-id="901c5-106">Lo preferible para las clases genéricas es usar interfaces genéricas, como <xref:System.IComparable%601> en lugar de <xref:System.IComparable>, para evitar las operaciones de conversión boxing y unboxing en los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="901c5-106">The preference for generic classes is to use generic interfaces, such as <xref:System.IComparable%601> rather than <xref:System.IComparable>, in order to avoid boxing and unboxing operations on value types.</span></span> <span data-ttu-id="901c5-107">En la biblioteca de clases de .NET se definen varias interfaces genéricas para usarlas con las clases de colección del espacio de nombres <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="901c5-107">The .NET class library defines several generic interfaces for use with the collection classes in the <xref:System.Collections.Generic> namespace.</span></span>  
  
 <span data-ttu-id="901c5-108">Cuando una interfaz se especifica como restricción en un parámetro de tipo, solo se pueden usar los tipos que implementan la interfaz.</span><span class="sxs-lookup"><span data-stu-id="901c5-108">When an interface is specified as a constraint on a type parameter, only types that implement the interface can be used.</span></span> <span data-ttu-id="901c5-109">El ejemplo de código siguiente muestra una clase `SortedList<T>` derivada de la clase `GenericList<T>`.</span><span class="sxs-lookup"><span data-stu-id="901c5-109">The following code example shows a `SortedList<T>` class that derives from the `GenericList<T>` class.</span></span> <span data-ttu-id="901c5-110">Para obtener más información, vea [Introducción a los genéricos](./index.md).</span><span class="sxs-lookup"><span data-stu-id="901c5-110">For more information, see [Introduction to Generics](./index.md).</span></span> <span data-ttu-id="901c5-111">`SortedList<T>` agrega la restricción `where T : IComparable<T>`.</span><span class="sxs-lookup"><span data-stu-id="901c5-111">`SortedList<T>` adds the constraint `where T : IComparable<T>`.</span></span> <span data-ttu-id="901c5-112">Esto permite al método `BubbleSort` de `SortedList<T>` usar el método <xref:System.IComparable%601.CompareTo%2A> genérico con los elementos de lista.</span><span class="sxs-lookup"><span data-stu-id="901c5-112">This enables the `BubbleSort` method in `SortedList<T>` to use the generic <xref:System.IComparable%601.CompareTo%2A> method on list elements.</span></span> <span data-ttu-id="901c5-113">En este ejemplo, los elementos de lista son una clase simple, `Person`, que implementa `IComparable<Person>`.</span><span class="sxs-lookup"><span data-stu-id="901c5-113">In this example, list elements are a simple class, `Person`, that implements `IComparable<Person>`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics2.cs#29)]  
  
 <span data-ttu-id="901c5-114">Se pueden especificar varias interfaces como restricciones en un solo tipo, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="901c5-114">Multiple interfaces can be specified as constraints on a single type, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#30)]  
  
 <span data-ttu-id="901c5-115">Una interfaz puede definir más de un parámetro de tipo, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="901c5-115">An interface can define more than one type parameter, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#31)]  
  
 <span data-ttu-id="901c5-116">Las reglas de herencia que se aplican a las clases también se aplican a las interfaces:</span><span class="sxs-lookup"><span data-stu-id="901c5-116">The rules of inheritance that apply to classes also apply to interfaces:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#32)]  
  
 <span data-ttu-id="901c5-117">Las interfaces genéricas pueden heredar de interfaces no genéricas si son contravariantes, lo que significa que solo usan su parámetro de tipo como valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="901c5-117">Generic interfaces can inherit from non-generic interfaces if the generic interface is contravariant, which means it only uses its type parameter as a return value.</span></span> <span data-ttu-id="901c5-118">En la biblioteca de clases de .NET, <xref:System.Collections.Generic.IEnumerable%601> hereda de <xref:System.Collections.IEnumerable> porque <xref:System.Collections.Generic.IEnumerable%601> solo usa `T` en el valor devuelto de <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> y en el captador de propiedad <xref:System.Collections.Generic.IEnumerator%601.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="901c5-118">In the .NET class library, <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable> because <xref:System.Collections.Generic.IEnumerable%601> only uses `T` in the return value of <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> and in the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property getter.</span></span>  
  
 <span data-ttu-id="901c5-119">Las clases concretas pueden implementar interfaces construidas cerradas, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="901c5-119">Concrete classes can implement closed constructed interfaces, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#33)]  
  
 <span data-ttu-id="901c5-120">Las clases genéricas pueden implementar interfaces genéricas o interfaces construidas cerradas siempre que la lista de parámetros de la clase suministre todos los argumentos que necesita la interfaz, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="901c5-120">Generic classes can implement generic interfaces or closed constructed interfaces as long as the class parameter list supplies all arguments required by the interface, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#34)]  
  
 <span data-ttu-id="901c5-121">Las reglas que controlan la sobrecarga de métodos son las mismas para los métodos incluidos en las clases genéricas, los structs genéricos o las interfaces genéricas.</span><span class="sxs-lookup"><span data-stu-id="901c5-121">The rules that control method overloading are the same for methods within generic classes, generic structs, or generic interfaces.</span></span> <span data-ttu-id="901c5-122">Para obtener más información, vea [Métodos genéricos](./generic-methods.md).</span><span class="sxs-lookup"><span data-stu-id="901c5-122">For more information, see [Generic Methods](./generic-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="901c5-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="901c5-123">See also</span></span>

- [<span data-ttu-id="901c5-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="901c5-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="901c5-125">Introducción a los genéricos</span><span class="sxs-lookup"><span data-stu-id="901c5-125">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="901c5-126">interface</span><span class="sxs-lookup"><span data-stu-id="901c5-126">interface</span></span>](../../language-reference/keywords/interface.md)
- [<span data-ttu-id="901c5-127">Genéricos</span><span class="sxs-lookup"><span data-stu-id="901c5-127">Generics</span></span>](../../../standard/generics/index.md)
