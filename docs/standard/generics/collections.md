---
title: "Colecciones genéricas en .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET Framework], collections
- generic collections [.NET Framework]
ms.assetid: 5b646751-6ab7-465c-916c-b1a76aefa9f5
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d7e7d11446c14cffbef1e5cade5f082874187636
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="generic-collections-in-the-net-framework"></a><span data-ttu-id="ba1ff-102">Colecciones genéricas en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ba1ff-102">Generic Collections in the .NET Framework</span></span>
<span data-ttu-id="ba1ff-103">Este tema proporciona una introducción a las clases de colección genéricas y otros tipos genéricos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-103">This topic provides an overview of the generic collection classes and other generic types in the .NET Framework.</span></span>  
  
## <a name="generic-collections-in-the-net-framework"></a><span data-ttu-id="ba1ff-104">Colecciones genéricas en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ba1ff-104">Generic Collections in the .NET Framework</span></span>  
 <span data-ttu-id="ba1ff-105">La biblioteca de clases de .NET Framework proporciona varias clases de colección genéricas en los espacios de nombres <xref:System.Collections.Generic> y <xref:System.Collections.ObjectModel>.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-105">The .NET Framework class library provides a number of generic collection classes in the <xref:System.Collections.Generic> and <xref:System.Collections.ObjectModel> namespaces.</span></span> <span data-ttu-id="ba1ff-106">Para obtener más información sobre estas clases, consulte [Tipos de colección utilizados normalmente](../../../docs/standard/collections/commonly-used-collection-types.md).</span><span class="sxs-lookup"><span data-stu-id="ba1ff-106">For more information about these classes, see [Commonly Used Collection Types](../../../docs/standard/collections/commonly-used-collection-types.md).</span></span>  
  
### <a name="systemcollectionsgeneric"></a><span data-ttu-id="ba1ff-107">System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="ba1ff-107">System.Collections.Generic</span></span>  
 <span data-ttu-id="ba1ff-108">Muchos de los tipos de colección genéricos son análogos directos de tipos no genéricos.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-108">Many of the generic collection types are direct analogs of nongeneric types.</span></span> <span data-ttu-id="ba1ff-109"><xref:System.Collections.Generic.Dictionary%602> es una versión genérica de <xref:System.Collections.Hashtable>; usa la estructura genérica <xref:System.Collections.Generic.KeyValuePair%602> para la enumeración en lugar de <xref:System.Collections.DictionaryEntry>.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-109"><xref:System.Collections.Generic.Dictionary%602> is a generic version of <xref:System.Collections.Hashtable>; it uses the generic structure <xref:System.Collections.Generic.KeyValuePair%602> for enumeration instead of <xref:System.Collections.DictionaryEntry>.</span></span>  
  
 <span data-ttu-id="ba1ff-110"><xref:System.Collections.Generic.List%601> es una versión genérica de <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-110"><xref:System.Collections.Generic.List%601> is a generic version of <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="ba1ff-111">Hay clases <xref:System.Collections.Generic.Queue%601> y <xref:System.Collections.Generic.Stack%601> genéricas que se corresponden con las versiones no genéricas.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-111">There are generic <xref:System.Collections.Generic.Queue%601> and <xref:System.Collections.Generic.Stack%601> classes that correspond to the nongeneric versions.</span></span>  
  
 <span data-ttu-id="ba1ff-112">Hay versiones genéricas y no genéricas de <xref:System.Collections.Generic.SortedList%602>.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-112">There are generic and nongeneric versions of <xref:System.Collections.Generic.SortedList%602>.</span></span> <span data-ttu-id="ba1ff-113">Ambas versiones son híbridos de un diccionario y una lista.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-113">Both versions are hybrids of a dictionary and a list.</span></span> <span data-ttu-id="ba1ff-114">La clase genérica <xref:System.Collections.Generic.SortedDictionary%602> es un diccionario puro y no tiene ninguna homóloga no genérica.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-114">The <xref:System.Collections.Generic.SortedDictionary%602> generic class is a pure dictionary and has no nongeneric counterpart.</span></span>  
  
 <span data-ttu-id="ba1ff-115">La clase genérica <xref:System.Collections.Generic.LinkedList%601> es una lista vinculada genuina.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-115">The <xref:System.Collections.Generic.LinkedList%601> generic class is a true linked list.</span></span> <span data-ttu-id="ba1ff-116">No tiene ninguna homóloga no genérica.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-116">It has no nongeneric counterpart.</span></span>  
  
### <a name="systemcollectionsobjectmodel"></a><span data-ttu-id="ba1ff-117">System.Collections.ObjectModel</span><span class="sxs-lookup"><span data-stu-id="ba1ff-117">System.Collections.ObjectModel</span></span>  
 <span data-ttu-id="ba1ff-118">La clase genérica <xref:System.Collections.ObjectModel.Collection%601> proporciona una clase base para derivar sus propios tipos de colección genéricos.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-118">The <xref:System.Collections.ObjectModel.Collection%601> generic class provides a base class for deriving your own generic collection types.</span></span> <span data-ttu-id="ba1ff-119">La clase <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> proporciona una manera sencilla de generar una colección de solo lectura de cualquier tipo que implementa la interfaz genérica <xref:System.Collections.Generic.IList%601>.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-119">The <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class provides an easy way to produce a read-only collection from any type that implements the <xref:System.Collections.Generic.IList%601> generic interface.</span></span> <span data-ttu-id="ba1ff-120">La clase genérica <xref:System.Collections.ObjectModel.KeyedCollection%602> proporciona una manera de almacenar objetos que contienen sus propias claves.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-120">The <xref:System.Collections.ObjectModel.KeyedCollection%602> generic class provides a way to store objects that contain their own keys.</span></span>  
  
## <a name="other-generic-types"></a><span data-ttu-id="ba1ff-121">Otros tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="ba1ff-121">Other Generic Types</span></span>  
 <span data-ttu-id="ba1ff-122">La estructura genérica <xref:System.Nullable%601> permite usar tipos de valor como si se les pudiera asignar el valor `null`.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-122">The <xref:System.Nullable%601> generic structure allows you to use value types as if they could be assigned `null`.</span></span> <span data-ttu-id="ba1ff-123">Esto puede ser útil para trabajar con consultas de base de datos en las que pueden faltar campos que contienen tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-123">This can be useful when working with database queries, where fields that contain value types can be missing.</span></span> <span data-ttu-id="ba1ff-124">El parámetro de tipo genérico puede ser cualquier tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-124">The generic type parameter can be any value type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba1ff-125">En C# no es necesario usar <xref:System.Nullable%601> explícitamente porque el lenguaje tiene sintaxis para tipos que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-125">In C# it is not necessary to use <xref:System.Nullable%601> explicitly because the language has syntax for nullable types.</span></span>  
  
 <span data-ttu-id="ba1ff-126">La estructura genérica <xref:System.ArraySegment%601> proporciona una manera de delimitar un intervalo de elementos en una matriz unidimensional basada en cero de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-126">The <xref:System.ArraySegment%601> generic structure provides a way to delimit a range of elements within a one-dimensional, zero-based array of any type.</span></span> <span data-ttu-id="ba1ff-127">El parámetro de tipo genérico es el tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-127">The generic type parameter is the type of the array's elements.</span></span>  
  
 <span data-ttu-id="ba1ff-128">El delegado genérico <xref:System.EventHandler%601> elimina la necesidad de declarar un tipo de delegado para controlar los eventos, si su evento sigue el patrón de control de eventos que usa [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba1ff-128">The <xref:System.EventHandler%601> generic delegate eliminates the need to declare a delegate type to handle events, if your event follows the event-handling pattern used by the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="ba1ff-129">Por ejemplo, supongamos que ha creado una clase `MyEventArgs`, derivada de <xref:System.EventArgs>, para contener los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="ba1ff-129">For example, suppose you have created a `MyEventArgs` class, derived from <xref:System.EventArgs>, to hold the data for your event.</span></span> <span data-ttu-id="ba1ff-130">Puede declarar el evento de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ba1ff-130">You can then declare the event as follows:</span></span>  
  
 [!code-cpp[Conceptual.Generics.Overview#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Generics.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source2.cs#7)]
 [!code-vb[Conceptual.Generics.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="ba1ff-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba1ff-131">See Also</span></span>  
 <xref:System.Collections.Generic?displayProperty=nameWithType>  
 <xref:System.Collections.ObjectModel?displayProperty=nameWithType>  
 [<span data-ttu-id="ba1ff-132">Genéricos</span><span class="sxs-lookup"><span data-stu-id="ba1ff-132">Generics</span></span>](../../../docs/standard/generics/index.md)  
 [<span data-ttu-id="ba1ff-133">Delegados genéricos para manipular matrices y listas</span><span class="sxs-lookup"><span data-stu-id="ba1ff-133">Generic Delegates for Manipulating Arrays and Lists</span></span>](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)  
 [<span data-ttu-id="ba1ff-134">Interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="ba1ff-134">Generic Interfaces</span></span>](../../../docs/standard/generics/interfaces.md)
