---
title: Realizar combinaciones agrupadas
description: "Cómo realizar combinaciones agrupadas."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 9667daf9-a5fd-4b43-a5c4-a9c2b744000e
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0410c5f673e61f91c00a69cb1659e0d72852f128
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="perform-grouped-joins"></a><span data-ttu-id="499ea-104">Realizar combinaciones agrupadas</span><span class="sxs-lookup"><span data-stu-id="499ea-104">Perform grouped joins</span></span>

<span data-ttu-id="499ea-105">La combinación agrupada resulta útil para generar estructuras de datos jerárquicas.</span><span class="sxs-lookup"><span data-stu-id="499ea-105">The group join is useful for producing hierarchical data structures.</span></span> <span data-ttu-id="499ea-106">Empareja cada elemento de la primera colección con un conjunto de elementos correlacionados de la segunda colección.</span><span class="sxs-lookup"><span data-stu-id="499ea-106">It pairs each element from the first collection with a set of correlated elements from the second collection.</span></span>  
  
 <span data-ttu-id="499ea-107">Por ejemplo, una clase o una tabla de base de datos relacional denominada `Student` podría contener dos campos: `Id` y `Name`.</span><span class="sxs-lookup"><span data-stu-id="499ea-107">For example, a class or a relational database table named `Student` might contain two fields: `Id` and `Name`.</span></span> <span data-ttu-id="499ea-108">Una segunda clase o tabla de base de datos relacional denominada `Course` podría contener dos campos: `StudentId` y `CourseTitle`.</span><span class="sxs-lookup"><span data-stu-id="499ea-108">A second class or relational database table named `Course` might contain two fields: `StudentId` and `CourseTitle`.</span></span> <span data-ttu-id="499ea-109">Una combinación agrupada de estos dos orígenes de datos, basada en la combinación de `Student.Id` y `Course.StudentId`, agruparía cada `Student` con una colección de objetos `Course` (que podrían estar vacíos).</span><span class="sxs-lookup"><span data-stu-id="499ea-109">A group join of these two data sources, based on matching `Student.Id` and `Course.StudentId`, would group each `Student` with a collection of `Course` objects (which might be empty).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="499ea-110">Cada elemento de la primera colección aparece en el conjunto de resultados de una combinación agrupada, independientemente de si se encuentran elementos correlacionados en la segunda colección.</span><span class="sxs-lookup"><span data-stu-id="499ea-110">Each element of the first collection appears in the result set of a group join regardless of whether correlated elements are found in the second collection.</span></span> <span data-ttu-id="499ea-111">En el caso de que no se encuentren elementos correlacionados, la secuencia de elementos correlacionados para ese elemento estaría vacía.</span><span class="sxs-lookup"><span data-stu-id="499ea-111">In the case where no correlated elements are found, the sequence of correlated elements for that element is empty.</span></span> <span data-ttu-id="499ea-112">Por consiguiente, el selector de resultados tiene acceso a cada uno de los elementos de la primera colección.</span><span class="sxs-lookup"><span data-stu-id="499ea-112">The result selector therefore has access to every element of the first collection.</span></span> <span data-ttu-id="499ea-113">Esto difiere del selector de resultados en una combinación no agrupada, que no puede acceder a los elementos de la primera colección que no tienen ninguna coincidencia en la segunda colección.</span><span class="sxs-lookup"><span data-stu-id="499ea-113">This differs from the result selector in a non-group join, which cannot access elements from the first collection that have no match in the second collection.</span></span>  
  
 <span data-ttu-id="499ea-114">En el primer ejemplo de este tema se muestra cómo realizar una combinación agrupada.</span><span class="sxs-lookup"><span data-stu-id="499ea-114">The first example in this topic shows you how to perform a group join.</span></span> <span data-ttu-id="499ea-115">En el segundo ejemplo se muestra cómo usar una combinación agrupada para crear elementos XML.</span><span class="sxs-lookup"><span data-stu-id="499ea-115">The second example shows you how to use a group join to create XML elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="499ea-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="499ea-116">Example</span></span>  
  
### <a name="group-join-example"></a><span data-ttu-id="499ea-117">Ejemplo de combinación agrupada</span><span class="sxs-lookup"><span data-stu-id="499ea-117">Group join example</span></span>  
 <span data-ttu-id="499ea-118">En el ejemplo siguiente se realiza una combinación agrupada de objetos de tipo `Person` y `Pet` basada en la coincidencia de `Person` con la propiedad `Pet.Owner`.</span><span class="sxs-lookup"><span data-stu-id="499ea-118">The following example performs a group join of objects of type `Person` and `Pet` based on the `Person` matching the `Pet.Owner` property.</span></span> <span data-ttu-id="499ea-119">A diferencia de una combinación no agrupada, que generaría un par de elementos para cada coincidencia, la combinación agrupada produce un único objeto resultante para cada elemento de la primera colección, que en este ejemplo es un objeto `Person`.</span><span class="sxs-lookup"><span data-stu-id="499ea-119">Unlike a non-group join, which would produce a pair of elements for each match, the group join produces only one resulting object for each element of the first collection, which in this example is a `Person` object.</span></span> <span data-ttu-id="499ea-120">Los elementos correspondientes de la segunda colección, que en este ejemplo son objetos `Pet`, se agrupan en una colección.</span><span class="sxs-lookup"><span data-stu-id="499ea-120">The corresponding elements from the second collection, which in this example are `Pet` objects, are grouped into a collection.</span></span> <span data-ttu-id="499ea-121">Por último, la función de selector de resultados crea un tipo anónimo para cada coincidencia formada por `Person.FirstName` y una colección de objetos `Pet`.</span><span class="sxs-lookup"><span data-stu-id="499ea-121">Finally, the result selector function creates an anonymous type for each match that consists of `Person.FirstName` and a collection of `Pet` objects.</span></span>  
  
 <span data-ttu-id="499ea-122">[!code-cs[CsLINQProgJoining#5](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="499ea-122">[!code-cs[CsLINQProgJoining#5](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="499ea-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="499ea-123">Example</span></span>  
  
### <a name="group-join-to-create-xml-example"></a><span data-ttu-id="499ea-124">Ejemplo de combinación agrupada para crear XML</span><span class="sxs-lookup"><span data-stu-id="499ea-124">Group join to create XML example</span></span>  
 <span data-ttu-id="499ea-125">Las combinaciones agrupadas resultan ideales para crear XML con LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="499ea-125">Group joins are ideal for creating XML by using LINQ to XML.</span></span> <span data-ttu-id="499ea-126">El siguiente ejemplo es similar al anterior, pero en lugar de crear tipos anónimos, la función de selector de resultados crea elementos XML que representan los objetos combinados.</span><span class="sxs-lookup"><span data-stu-id="499ea-126">The following example is similar to the previous example except that instead of creating anonymous types, the result selector function creates XML elements that represent the joined objects.</span></span>  
  
 <span data-ttu-id="499ea-127">[!code-cs[CsLINQProgJoining#6](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="499ea-127">[!code-cs[CsLINQProgJoining#6](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="499ea-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="499ea-128">See also</span></span>  
 <span data-ttu-id="499ea-129"><xref:System.Linq.Enumerable.Join%2A></span><span class="sxs-lookup"><span data-stu-id="499ea-129"><xref:System.Linq.Enumerable.Join%2A></span></span>   
 <span data-ttu-id="499ea-130"><xref:System.Linq.Enumerable.GroupJoin%2A></span><span class="sxs-lookup"><span data-stu-id="499ea-130"><xref:System.Linq.Enumerable.GroupJoin%2A></span></span>   
 <span data-ttu-id="499ea-131">[Realizar combinaciones internas](perform-inner-joins.md) </span><span class="sxs-lookup"><span data-stu-id="499ea-131">[Perform inner joins](perform-inner-joins.md) </span></span>  
 <span data-ttu-id="499ea-132">[Perform left outer joins](perform-left-outer-joins.md)  (Realizar operaciones de combinación externa izquierda)</span><span class="sxs-lookup"><span data-stu-id="499ea-132">[Perform left outer joins](perform-left-outer-joins.md) </span></span>  
 <span data-ttu-id="499ea-133">[Anonymous Types](../programming-guide/classes-and-structs/anonymous-types.md) (Tipos anónimos [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="499ea-133">[Anonymous types](../programming-guide/classes-and-structs/anonymous-types.md)</span></span>   
 

