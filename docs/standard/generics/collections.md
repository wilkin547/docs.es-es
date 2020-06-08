---
title: Colecciones genéricas en .NET
ms.date: 02/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET], collections
- generic collections [.NET]
- generic types [.NET]
ms.assetid: 5b646751-6ab7-465c-916c-b1a76aefa9f5
ms.openlocfilehash: 5767bac0bb1e3ae9e586e9a10d8452d421519447
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287576"
---
# <a name="generic-collections-in-net"></a><span data-ttu-id="63e70-102">Colecciones genéricas en .NET</span><span class="sxs-lookup"><span data-stu-id="63e70-102">Generic collections in .NET</span></span>

 <span data-ttu-id="63e70-103">La biblioteca de clases de .NET ofrece varias clases de colección genéricas en los espacios de nombres <xref:System.Collections.Generic> y <xref:System.Collections.ObjectModel>.</span><span class="sxs-lookup"><span data-stu-id="63e70-103">The .NET class library provides a number of generic collection classes in the <xref:System.Collections.Generic> and <xref:System.Collections.ObjectModel> namespaces.</span></span> <span data-ttu-id="63e70-104">Para obtener información más detallada sobre estas clases, vea [Tipos de colección utilizados normalmente](../collections/commonly-used-collection-types.md).</span><span class="sxs-lookup"><span data-stu-id="63e70-104">For more detailed information about these classes, see [Commonly Used Collection Types](../collections/commonly-used-collection-types.md).</span></span>  
  
## <a name="systemcollectionsgeneric"></a><span data-ttu-id="63e70-105">System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="63e70-105">System.Collections.Generic</span></span>

 <span data-ttu-id="63e70-106">Muchos de los tipos de colección genéricos son análogos directos de tipos no genéricos.</span><span class="sxs-lookup"><span data-stu-id="63e70-106">Many of the generic collection types are direct analogs of nongeneric types.</span></span> <span data-ttu-id="63e70-107"><xref:System.Collections.Generic.Dictionary%602> es una versión genérica de <xref:System.Collections.Hashtable>; usa la estructura genérica <xref:System.Collections.Generic.KeyValuePair%602> para la enumeración en lugar de <xref:System.Collections.DictionaryEntry>.</span><span class="sxs-lookup"><span data-stu-id="63e70-107"><xref:System.Collections.Generic.Dictionary%602> is a generic version of <xref:System.Collections.Hashtable>; it uses the generic structure <xref:System.Collections.Generic.KeyValuePair%602> for enumeration instead of <xref:System.Collections.DictionaryEntry>.</span></span>  
  
 <span data-ttu-id="63e70-108"><xref:System.Collections.Generic.List%601> es una versión genérica de <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="63e70-108"><xref:System.Collections.Generic.List%601> is a generic version of <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="63e70-109">Hay clases <xref:System.Collections.Generic.Queue%601> y <xref:System.Collections.Generic.Stack%601> genéricas que se corresponden con las versiones no genéricas.</span><span class="sxs-lookup"><span data-stu-id="63e70-109">There are generic <xref:System.Collections.Generic.Queue%601> and <xref:System.Collections.Generic.Stack%601> classes that correspond to the nongeneric versions.</span></span>  
  
 <span data-ttu-id="63e70-110">Hay versiones genéricas y no genéricas de <xref:System.Collections.Generic.SortedList%602>.</span><span class="sxs-lookup"><span data-stu-id="63e70-110">There are generic and nongeneric versions of <xref:System.Collections.Generic.SortedList%602>.</span></span> <span data-ttu-id="63e70-111">Ambas versiones son híbridos de un diccionario y una lista.</span><span class="sxs-lookup"><span data-stu-id="63e70-111">Both versions are hybrids of a dictionary and a list.</span></span> <span data-ttu-id="63e70-112">La clase genérica <xref:System.Collections.Generic.SortedDictionary%602> es un diccionario puro y no tiene ninguna homóloga no genérica.</span><span class="sxs-lookup"><span data-stu-id="63e70-112">The <xref:System.Collections.Generic.SortedDictionary%602> generic class is a pure dictionary and has no nongeneric counterpart.</span></span>  
  
 <span data-ttu-id="63e70-113">La clase genérica <xref:System.Collections.Generic.LinkedList%601> es una lista vinculada genuina.</span><span class="sxs-lookup"><span data-stu-id="63e70-113">The <xref:System.Collections.Generic.LinkedList%601> generic class is a true linked list.</span></span> <span data-ttu-id="63e70-114">No tiene ninguna homóloga no genérica.</span><span class="sxs-lookup"><span data-stu-id="63e70-114">It has no nongeneric counterpart.</span></span>  
  
## <a name="systemcollectionsobjectmodel"></a><span data-ttu-id="63e70-115">System.Collections.ObjectModel</span><span class="sxs-lookup"><span data-stu-id="63e70-115">System.Collections.ObjectModel</span></span>

 <span data-ttu-id="63e70-116">La clase genérica <xref:System.Collections.ObjectModel.Collection%601> proporciona una clase base para derivar sus propios tipos de colección genéricos.</span><span class="sxs-lookup"><span data-stu-id="63e70-116">The <xref:System.Collections.ObjectModel.Collection%601> generic class provides a base class for deriving your own generic collection types.</span></span> <span data-ttu-id="63e70-117">La clase <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> proporciona una manera sencilla de generar una colección de solo lectura de cualquier tipo que implementa la interfaz genérica <xref:System.Collections.Generic.IList%601>.</span><span class="sxs-lookup"><span data-stu-id="63e70-117">The <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class provides an easy way to produce a read-only collection from any type that implements the <xref:System.Collections.Generic.IList%601> generic interface.</span></span> <span data-ttu-id="63e70-118">La clase genérica <xref:System.Collections.ObjectModel.KeyedCollection%602> proporciona una manera de almacenar objetos que contienen sus propias claves.</span><span class="sxs-lookup"><span data-stu-id="63e70-118">The <xref:System.Collections.ObjectModel.KeyedCollection%602> generic class provides a way to store objects that contain their own keys.</span></span>  
  
## <a name="other-generic-types"></a><span data-ttu-id="63e70-119">Otros tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="63e70-119">Other generic types</span></span>

 <span data-ttu-id="63e70-120">La estructura genérica <xref:System.Nullable%601> permite usar tipos de valor como si se les pudiera asignar el valor `null`.</span><span class="sxs-lookup"><span data-stu-id="63e70-120">The <xref:System.Nullable%601> generic structure allows you to use value types as if they could be assigned `null`.</span></span> <span data-ttu-id="63e70-121">Esto puede ser útil para trabajar con consultas de base de datos en las que pueden faltar campos que contienen tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="63e70-121">This can be useful when working with database queries, where fields that contain value types can be missing.</span></span> <span data-ttu-id="63e70-122">El parámetro de tipo genérico puede ser cualquier tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="63e70-122">The generic type parameter can be any value type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="63e70-123">En C# y Visual Basic no hay que usar <xref:System.Nullable%601> explícitamente porque el lenguaje tiene sintaxis para tipos que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="63e70-123">In C# and Visual Basic, it is not necessary to use <xref:System.Nullable%601> explicitly because the language has syntax for nullable types.</span></span> <span data-ttu-id="63e70-124">Consulte [Tipos de valor que admiten un valor NULL (referencia de C#)](../../csharp/language-reference/builtin-types/nullable-value-types.md) y [Tipos de valor que admiten un valor NULL (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="63e70-124">See [Nullable value types (C# reference)](../../csharp/language-reference/builtin-types/nullable-value-types.md) and [Nullable value types (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span></span>
  
 <span data-ttu-id="63e70-125">La estructura genérica <xref:System.ArraySegment%601> proporciona una manera de delimitar un intervalo de elementos en una matriz unidimensional basada en cero de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="63e70-125">The <xref:System.ArraySegment%601> generic structure provides a way to delimit a range of elements within a one-dimensional, zero-based array of any type.</span></span> <span data-ttu-id="63e70-126">El parámetro de tipo genérico es el tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="63e70-126">The generic type parameter is the type of the array's elements.</span></span>  
  
 <span data-ttu-id="63e70-127">El delegado genérico <xref:System.EventHandler%601> elimina la necesidad de declarar un tipo de delegado para controlar los eventos, siempre que el evento siga el patrón de control de eventos que usa .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="63e70-127">The <xref:System.EventHandler%601> generic delegate eliminates the need to declare a delegate type to handle events, if your event follows the event-handling pattern used by the .NET Framework.</span></span> <span data-ttu-id="63e70-128">Por ejemplo, supongamos que ha creado una clase `MyEventArgs`, derivada de <xref:System.EventArgs>, para contener los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="63e70-128">For example, suppose you have created a `MyEventArgs` class, derived from <xref:System.EventArgs>, to hold the data for your event.</span></span> <span data-ttu-id="63e70-129">Puede declarar el evento de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="63e70-129">You can then declare the event as follows:</span></span>  
  
 [!code-cpp[Conceptual.Generics.Overview#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Generics.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source2.cs#7)]
 [!code-vb[Conceptual.Generics.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="63e70-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="63e70-130">See also</span></span>

- <xref:System.Collections.Generic?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel?displayProperty=nameWithType>
- [<span data-ttu-id="63e70-131">Genéricos</span><span class="sxs-lookup"><span data-stu-id="63e70-131">Generics</span></span>](index.md)
- [<span data-ttu-id="63e70-132">Delegados genéricos para manipular matrices y listas</span><span class="sxs-lookup"><span data-stu-id="63e70-132">Generic Delegates for Manipulating Arrays and Lists</span></span>](delegates-for-manipulating-arrays-and-lists.md)
- [<span data-ttu-id="63e70-133">Interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="63e70-133">Generic Interfaces</span></span>](interfaces.md)
