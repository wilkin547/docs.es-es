---
title: 'Interfaces genéricas: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
ms.openlocfilehash: 7fc79874c8e1ff24c38d288d3f6708e2851419e3
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423473"
---
# <a name="generic-interfaces-c-programming-guide"></a><span data-ttu-id="39ca6-102">Interfaces genéricas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="39ca6-102">Generic Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="39ca6-103">A menudo es útil definir interfaces para las clases de colección genéricas o para las clases genéricas que representan los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="39ca6-103">It is often useful to define interfaces either for generic collection classes, or for the generic classes that represent items in the collection.</span></span> <span data-ttu-id="39ca6-104">Lo preferible para las clases genéricas es usar interfaces genéricas, como <xref:System.IComparable%601> en lugar de <xref:System.IComparable>, para evitar las operaciones de conversión boxing y unboxing en los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="39ca6-104">The preference for generic classes is to use generic interfaces, such as <xref:System.IComparable%601> rather than <xref:System.IComparable>, in order to avoid boxing and unboxing operations on value types.</span></span> <span data-ttu-id="39ca6-105">La biblioteca de clases .NET Framework define varias interfaces genéricas para usarlas con las clases de colección del espacio de nombres <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="39ca6-105">The .NET Framework class library defines several generic interfaces for use with the collection classes in the <xref:System.Collections.Generic> namespace.</span></span>  
  
 <span data-ttu-id="39ca6-106">Cuando una interfaz se especifica como restricción en un parámetro de tipo, solo se pueden usar los tipos que implementan la interfaz.</span><span class="sxs-lookup"><span data-stu-id="39ca6-106">When an interface is specified as a constraint on a type parameter, only types that implement the interface can be used.</span></span> <span data-ttu-id="39ca6-107">El ejemplo de código siguiente muestra una clase `SortedList<T>` derivada de la clase `GenericList<T>`.</span><span class="sxs-lookup"><span data-stu-id="39ca6-107">The following code example shows a `SortedList<T>` class that derives from the `GenericList<T>` class.</span></span> <span data-ttu-id="39ca6-108">Para obtener más información, vea [Introducción a los genéricos](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="39ca6-108">For more information, see [Introduction to Generics](../../../csharp/programming-guide/generics/index.md).</span></span> <span data-ttu-id="39ca6-109">`SortedList<T>` agrega la restricción `where T : IComparable<T>`.</span><span class="sxs-lookup"><span data-stu-id="39ca6-109">`SortedList<T>` adds the constraint `where T : IComparable<T>`.</span></span> <span data-ttu-id="39ca6-110">Esto permite al método `BubbleSort` de `SortedList<T>` usar el método <xref:System.IComparable%601.CompareTo%2A> genérico con los elementos de lista.</span><span class="sxs-lookup"><span data-stu-id="39ca6-110">This enables the `BubbleSort` method in `SortedList<T>` to use the generic <xref:System.IComparable%601.CompareTo%2A> method on list elements.</span></span> <span data-ttu-id="39ca6-111">En este ejemplo, los elementos de lista son una clase simple, `Person`, que implementa `IComparable<Person>`.</span><span class="sxs-lookup"><span data-stu-id="39ca6-111">In this example, list elements are a simple class, `Person`, that implements `IComparable<Person>`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics2.cs#29)]  
  
 <span data-ttu-id="39ca6-112">Se pueden especificar varias interfaces como restricciones en un solo tipo, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="39ca6-112">Multiple interfaces can be specified as constraints on a single type, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#30)]  
  
 <span data-ttu-id="39ca6-113">Una interfaz puede definir más de un parámetro de tipo, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="39ca6-113">An interface can define more than one type parameter, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#31)]  
  
 <span data-ttu-id="39ca6-114">Las reglas de herencia que se aplican a las clases también se aplican a las interfaces:</span><span class="sxs-lookup"><span data-stu-id="39ca6-114">The rules of inheritance that apply to classes also apply to interfaces:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#32)]  
  
 <span data-ttu-id="39ca6-115">Las interfaces genéricas pueden heredar de interfaces no genéricas si son contravariantes, lo que significa que solo usan su parámetro de tipo como valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="39ca6-115">Generic interfaces can inherit from non-generic interfaces if the generic interface is contravariant, which means it only uses its type parameter as a return value.</span></span> <span data-ttu-id="39ca6-116">En la biblioteca de clases .NET Framework, <xref:System.Collections.Generic.IEnumerable%601> hereda de <xref:System.Collections.IEnumerable> porque <xref:System.Collections.Generic.IEnumerable%601> solo usa `T` en el valor devuelto de <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> y en el captador de propiedad <xref:System.Collections.Generic.IEnumerator%601.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="39ca6-116">In the .NET Framework class library, <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable> because <xref:System.Collections.Generic.IEnumerable%601> only uses `T` in the return value of <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> and in the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property getter.</span></span>  
  
 <span data-ttu-id="39ca6-117">Las clases concretas pueden implementar interfaces construidas cerradas, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="39ca6-117">Concrete classes can implement closed constructed interfaces, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#33)]  
  
 <span data-ttu-id="39ca6-118">Las clases genéricas pueden implementar interfaces genéricas o interfaces construidas cerradas siempre que la lista de parámetros de la clase suministre todos los argumentos que necesita la interfaz, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="39ca6-118">Generic classes can implement generic interfaces or closed constructed interfaces as long as the class parameter list supplies all arguments required by the interface, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#34)]  
  
 <span data-ttu-id="39ca6-119">Las reglas que controlan la sobrecarga de métodos son las mismas para los métodos incluidos en las clases genéricas, los structs genéricos o las interfaces genéricas.</span><span class="sxs-lookup"><span data-stu-id="39ca6-119">The rules that control method overloading are the same for methods within generic classes, generic structs, or generic interfaces.</span></span> <span data-ttu-id="39ca6-120">Para obtener más información, vea [Métodos genéricos](../../../csharp/programming-guide/generics/generic-methods.md).</span><span class="sxs-lookup"><span data-stu-id="39ca6-120">For more information, see [Generic Methods](../../../csharp/programming-guide/generics/generic-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39ca6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="39ca6-121">See also</span></span>

- [<span data-ttu-id="39ca6-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="39ca6-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="39ca6-123">Introducción a los genéricos</span><span class="sxs-lookup"><span data-stu-id="39ca6-123">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
- [<span data-ttu-id="39ca6-124">interface</span><span class="sxs-lookup"><span data-stu-id="39ca6-124">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)
- [<span data-ttu-id="39ca6-125">Genéricos</span><span class="sxs-lookup"><span data-stu-id="39ca6-125">Generics</span></span>](~/docs/standard/generics/index.md)
