---
title: "Interfaces genéricas (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2a9a994c339553b923b930660c0e129dd930de96
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="generic-interfaces-c-programming-guide"></a><span data-ttu-id="43b34-102">Interfaces genéricas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="43b34-102">Generic Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="43b34-103">A menudo es útil definir interfaces para las clases de colección genéricas o para las clases genéricas que representan los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="43b34-103">It is often useful to define interfaces either for generic collection classes, or for the generic classes that represent items in the collection.</span></span> <span data-ttu-id="43b34-104">Lo preferible para las clases genéricas es usar interfaces genéricas, como <xref:System.IComparable%601> en lugar de <xref:System.IComparable>, para evitar las operaciones de conversión boxing y unboxing en los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="43b34-104">The preference for generic classes is to use generic interfaces, such as <xref:System.IComparable%601> rather than <xref:System.IComparable>, in order to avoid boxing and unboxing operations on value types.</span></span> <span data-ttu-id="43b34-105">La biblioteca de clases .NET Framework define varias interfaces genéricas para usarlas con las clases de colección del espacio de nombres <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="43b34-105">The .NET Framework class library defines several generic interfaces for use with the collection classes in the <xref:System.Collections.Generic> namespace.</span></span>  
  
 <span data-ttu-id="43b34-106">Cuando una interfaz se especifica como restricción en un parámetro de tipo, solo se pueden usar los tipos que implementan la interfaz.</span><span class="sxs-lookup"><span data-stu-id="43b34-106">When an interface is specified as a constraint on a type parameter, only types that implement the interface can be used.</span></span> <span data-ttu-id="43b34-107">El ejemplo de código siguiente muestra una clase `SortedList<T>` derivada de la clase `GenericList<T>`.</span><span class="sxs-lookup"><span data-stu-id="43b34-107">The following code example shows a `SortedList<T>` class that derives from the `GenericList<T>` class.</span></span> <span data-ttu-id="43b34-108">Para obtener más información, vea [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md).</span><span class="sxs-lookup"><span data-stu-id="43b34-108">For more information, see [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md).</span></span> <span data-ttu-id="43b34-109">`SortedList<T>` agrega la restricción `where T : IComparable<T>`.</span><span class="sxs-lookup"><span data-stu-id="43b34-109">`SortedList<T>` adds the constraint `where T : IComparable<T>`.</span></span> <span data-ttu-id="43b34-110">Esto permite al método `BubbleSort` de `SortedList<T>` usar el método <xref:System.IComparable%601.CompareTo%2A> genérico con los elementos de lista.</span><span class="sxs-lookup"><span data-stu-id="43b34-110">This enables the `BubbleSort` method in `SortedList<T>` to use the generic <xref:System.IComparable%601.CompareTo%2A> method on list elements.</span></span> <span data-ttu-id="43b34-111">En este ejemplo, los elementos de lista son una clase simple, `Person`, que implementa `IComparable<Person>`.</span><span class="sxs-lookup"><span data-stu-id="43b34-111">In this example, list elements are a simple class, `Person`, that implements `IComparable<Person>`.</span></span>  
  
 <span data-ttu-id="43b34-112">[!code-cs[csProgGuideGenerics#29](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="43b34-112">[!code-cs[csProgGuideGenerics#29](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_1.cs)]</span></span>  
  
 <span data-ttu-id="43b34-113">Se pueden especificar varias interfaces como restricciones en un solo tipo, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="43b34-113">Multiple interfaces can be specified as constraints on a single type, as follows:</span></span>  
  
 <span data-ttu-id="43b34-114">[!code-cs[csProgGuideGenerics#30](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="43b34-114">[!code-cs[csProgGuideGenerics#30](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_2.cs)]</span></span>  
  
 <span data-ttu-id="43b34-115">Una interfaz puede definir más de un parámetro de tipo, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="43b34-115">An interface can define more than one type parameter, as follows:</span></span>  
  
 <span data-ttu-id="43b34-116">[!code-cs[csProgGuideGenerics#31](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="43b34-116">[!code-cs[csProgGuideGenerics#31](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_3.cs)]</span></span>  
  
 <span data-ttu-id="43b34-117">Las reglas de herencia que se aplican a las clases también se aplican a las interfaces:</span><span class="sxs-lookup"><span data-stu-id="43b34-117">The rules of inheritance that apply to classes also apply to interfaces:</span></span>  
  
 <span data-ttu-id="43b34-118">[!code-cs[csProgGuideGenerics#32](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="43b34-118">[!code-cs[csProgGuideGenerics#32](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_4.cs)]</span></span>  
  
 <span data-ttu-id="43b34-119">Las interfaces genéricas pueden heredar de interfaces no genéricas si son contra-variantes, lo que significa que solo usan su parámetro de tipo como valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="43b34-119">Generic interfaces can inherit from non-generic interfaces if the generic interface is contra-variant, which means it only uses its type parameter as a return value.</span></span> <span data-ttu-id="43b34-120">En la biblioteca de clases .NET Framework, <xref:System.Collections.Generic.IEnumerable%601> hereda de <xref:System.Collections.IEnumerable> porque <xref:System.Collections.Generic.IEnumerable%601> solo usa `T` en el valor devuelto de <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> y en el captador de propiedad <xref:System.Collections.Generic.IEnumerator%601.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="43b34-120">In the .NET Framework class library, <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable> because <xref:System.Collections.Generic.IEnumerable%601> only uses `T` in the return value of <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> and in the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property getter.</span></span>  
  
 <span data-ttu-id="43b34-121">Las clases concretas pueden implementar interfaces construidas cerradas, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="43b34-121">Concrete classes can implement closed constructed interfaces, as follows:</span></span>  
  
 <span data-ttu-id="43b34-122">[!code-cs[csProgGuideGenerics#33](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="43b34-122">[!code-cs[csProgGuideGenerics#33](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_5.cs)]</span></span>  
  
 <span data-ttu-id="43b34-123">Las clases genéricas pueden implementar interfaces genéricas o interfaces construidas cerradas siempre que la lista de parámetros de la clase suministre todos los argumentos que necesita la interfaz, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="43b34-123">Generic classes can implement generic interfaces or closed constructed interfaces as long as the class parameter list supplies all arguments required by the interface, as follows:</span></span>  
  
 <span data-ttu-id="43b34-124">[!code-cs[csProgGuideGenerics#34](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="43b34-124">[!code-cs[csProgGuideGenerics#34](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_6.cs)]</span></span>  
  
 <span data-ttu-id="43b34-125">Las reglas que controlan la sobrecarga de métodos son las mismas para los métodos incluidos en las clases genéricas, los structs genéricos o las interfaces genéricas.</span><span class="sxs-lookup"><span data-stu-id="43b34-125">The rules that control method overloading are the same for methods within generic classes, generic structs, or generic interfaces.</span></span> <span data-ttu-id="43b34-126">Para obtener más información, vea [Métodos genéricos](../../../csharp/programming-guide/generics/generic-methods.md).</span><span class="sxs-lookup"><span data-stu-id="43b34-126">For more information, see [Generic Methods](../../../csharp/programming-guide/generics/generic-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b34-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="43b34-127">See Also</span></span>  
 <span data-ttu-id="43b34-128">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="43b34-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="43b34-129">[Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="43b34-129">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 <span data-ttu-id="43b34-130">[interfaz](../../../csharp/language-reference/keywords/interface.md) </span><span class="sxs-lookup"><span data-stu-id="43b34-130">[interface](../../../csharp/language-reference/keywords/interface.md) </span></span>  
 [<span data-ttu-id="43b34-131">Genéricos</span><span class="sxs-lookup"><span data-stu-id="43b34-131">Generics</span></span>](~/docs/standard/generics/index.md)

