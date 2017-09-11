---
title: Operaciones set (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 121dcd4d41dcfea332c45031a5fbed594e2f1e3e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="set-operations-c"></a><span data-ttu-id="10153-102">Operaciones set (C#)</span><span class="sxs-lookup"><span data-stu-id="10153-102">Set Operations (C#)</span></span>
<span data-ttu-id="10153-103">Las operaciones set de LINQ se refieren a operaciones de consulta que generan un conjunto de resultados en función de la presencia o ausencia de elementos equivalentes dentro de la misma colección o en distintas colecciones (o conjuntos).</span><span class="sxs-lookup"><span data-stu-id="10153-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="10153-104">Los métodos del operador de consulta estándar que realizan operaciones set se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="10153-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10153-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="10153-105">Methods</span></span>  
  
|<span data-ttu-id="10153-106">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="10153-106">Method Name</span></span>|<span data-ttu-id="10153-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="10153-107">Description</span></span>|<span data-ttu-id="10153-108">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="10153-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="10153-109">Más información</span><span class="sxs-lookup"><span data-stu-id="10153-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="10153-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="10153-110">Distinct</span></span>|<span data-ttu-id="10153-111">Quita valores duplicados de una colección.</span><span class="sxs-lookup"><span data-stu-id="10153-111">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="10153-112">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="10153-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName>|  
|<span data-ttu-id="10153-113">Except</span><span class="sxs-lookup"><span data-stu-id="10153-113">Except</span></span>|<span data-ttu-id="10153-114">Devuelve la diferencia de conjuntos, es decir, los elementos de una colección que no aparecen en una segunda colección.</span><span class="sxs-lookup"><span data-stu-id="10153-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="10153-115">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="10153-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=fullName>|  
|<span data-ttu-id="10153-116">Formar intersección</span><span class="sxs-lookup"><span data-stu-id="10153-116">Intersect</span></span>|<span data-ttu-id="10153-117">Devuelve la intersección de conjuntos, es decir, los elementos que aparecen en las dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="10153-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="10153-118">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="10153-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName>|  
|<span data-ttu-id="10153-119">Unión</span><span class="sxs-lookup"><span data-stu-id="10153-119">Union</span></span>|<span data-ttu-id="10153-120">Devuelve la unión de conjuntos, es decir, los elementos únicos que aparecen en una de las dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="10153-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="10153-121">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="10153-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=fullName>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="10153-122">Comparación de operaciones set</span><span class="sxs-lookup"><span data-stu-id="10153-122">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="10153-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="10153-123">Distinct</span></span>  
 <span data-ttu-id="10153-124">En la siguiente ilustración se muestra el comportamiento del método <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName> en una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="10153-124">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName> method on a sequence of characters.</span></span> <span data-ttu-id="10153-125">La secuencia devuelta contiene los elementos únicos de la secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="10153-125">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 <span data-ttu-id="10153-126">![Gráfico que muestra el comportamiento de Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span><span class="sxs-lookup"><span data-stu-id="10153-126">![Graphic showing the behavior of Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span></span>  
  
### <a name="except"></a><span data-ttu-id="10153-127">Except</span><span class="sxs-lookup"><span data-stu-id="10153-127">Except</span></span>  
 <span data-ttu-id="10153-128">En la siguiente ilustración se muestra el comportamiento de <xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="10153-128">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="10153-129">La secuencia devuelta solo contiene los elementos de la primera secuencia de entrada que no están en la segunda secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="10153-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="10153-130">![Gráfico que muestra la acción de Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span><span class="sxs-lookup"><span data-stu-id="10153-130">![Graphic showing the action of Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="10153-131">Formar intersección</span><span class="sxs-lookup"><span data-stu-id="10153-131">Intersect</span></span>  
 <span data-ttu-id="10153-132">En la siguiente ilustración se muestra el comportamiento de <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="10153-132">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="10153-133">La secuencia devuelta contiene los elementos que son comunes a las dos secuencias de entrada.</span><span class="sxs-lookup"><span data-stu-id="10153-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 <span data-ttu-id="10153-134">![Gráfico que muestra la intersección de dos secuencias.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span><span class="sxs-lookup"><span data-stu-id="10153-134">![Graphic showing the intersection of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span></span>  
  
### <a name="union"></a><span data-ttu-id="10153-135">Unión</span><span class="sxs-lookup"><span data-stu-id="10153-135">Union</span></span>  
 <span data-ttu-id="10153-136">En la siguiente ilustración se muestra una operación de unión en dos secuencias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="10153-136">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="10153-137">La secuencia devuelta contiene los elementos únicos de las dos secuencias de entrada.</span><span class="sxs-lookup"><span data-stu-id="10153-137">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 <span data-ttu-id="10153-138">![Gráfico que muestra la unión de dos secuencias.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span><span class="sxs-lookup"><span data-stu-id="10153-138">![Graphic showing the union of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10153-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="10153-139">See Also</span></span>  
 <span data-ttu-id="10153-140"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="10153-140"><xref:System.Linq></span></span>   
 <span data-ttu-id="10153-141">[Información general sobre operadores de consulta estándar (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="10153-141">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="10153-142">[How to: Combine and Compare String Collections (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)  (Cómo: Combinar y comparar colecciones de cadenas (LINQ) [C#])</span><span class="sxs-lookup"><span data-stu-id="10153-142">[How to: Combine and Compare String Collections (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md) </span></span>  
 <span data-ttu-id="10153-143">[How to: Find the Set Difference Between Two Lists (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md) (Cómo: Buscar la diferencia de conjuntos entre dos listas (LINQ) [C#])</span><span class="sxs-lookup"><span data-stu-id="10153-143">[How to: Find the Set Difference Between Two Lists (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)</span></span>

