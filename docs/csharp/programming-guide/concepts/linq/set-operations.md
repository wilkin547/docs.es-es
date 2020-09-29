---
title: Operaciones set (C#)
description: Aprenda sobre las operaciones Set y los métodos de operador de consulta estándar que realizan operaciones Set en LINQ en C#.
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 8679f804adaaeada390206e3e1dd2a0711a2cbf6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195615"
---
# <a name="set-operations-c"></a><span data-ttu-id="33182-103">Operaciones set (C#)</span><span class="sxs-lookup"><span data-stu-id="33182-103">Set Operations (C#)</span></span>

<span data-ttu-id="33182-104">Las operaciones set de LINQ se refieren a operaciones de consulta que generan un conjunto de resultados en función de la presencia o ausencia de elementos equivalentes dentro de la misma colección o en distintas colecciones (o conjuntos).</span><span class="sxs-lookup"><span data-stu-id="33182-104">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="33182-105">Los métodos del operador de consulta estándar que realizan operaciones set se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="33182-105">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33182-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="33182-106">Methods</span></span>  
  
|<span data-ttu-id="33182-107">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="33182-107">Method Name</span></span>|<span data-ttu-id="33182-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="33182-108">Description</span></span>|<span data-ttu-id="33182-109">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="33182-109">C# Query Expression Syntax</span></span>|<span data-ttu-id="33182-110">Más información</span><span class="sxs-lookup"><span data-stu-id="33182-110">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="33182-111">Distinct</span><span class="sxs-lookup"><span data-stu-id="33182-111">Distinct</span></span>|<span data-ttu-id="33182-112">Quita valores duplicados de una colección.</span><span class="sxs-lookup"><span data-stu-id="33182-112">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="33182-113">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="33182-113">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="33182-114">Except</span><span class="sxs-lookup"><span data-stu-id="33182-114">Except</span></span>|<span data-ttu-id="33182-115">Devuelve la diferencia de conjuntos, es decir, los elementos de una colección que no aparecen en una segunda colección.</span><span class="sxs-lookup"><span data-stu-id="33182-115">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="33182-116">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="33182-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="33182-117">Formar intersección</span><span class="sxs-lookup"><span data-stu-id="33182-117">Intersect</span></span>|<span data-ttu-id="33182-118">Devuelve la intersección de conjuntos, es decir, los elementos que aparecen en las dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="33182-118">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="33182-119">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="33182-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="33182-120">Unión</span><span class="sxs-lookup"><span data-stu-id="33182-120">Union</span></span>|<span data-ttu-id="33182-121">Devuelve la unión de conjuntos, es decir, los elementos únicos que aparecen en una de las dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="33182-121">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="33182-122">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="33182-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="33182-123">Comparación de operaciones set</span><span class="sxs-lookup"><span data-stu-id="33182-123">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="33182-124">Distinct</span><span class="sxs-lookup"><span data-stu-id="33182-124">Distinct</span></span>  

 <span data-ttu-id="33182-125">En la siguiente ilustración se muestra el comportamiento del método <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> en una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="33182-125">The following example depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="33182-126">La secuencia devuelta contiene los elementos únicos de la secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="33182-126">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![Gráfico en el que se muestra el comportamiento de Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)  

 [!code-csharp-interactive[Distinct](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#1)]
  
### <a name="except"></a><span data-ttu-id="33182-128">Except</span><span class="sxs-lookup"><span data-stu-id="33182-128">Except</span></span>  

 <span data-ttu-id="33182-129">En el ejemplo siguiente se muestra el comportamiento de <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="33182-129">The following example depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="33182-130">La secuencia devuelta solo contiene los elementos de la primera secuencia de entrada que no están en la segunda secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="33182-130">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="33182-131">![Gráfico que muestra la acción de Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Muestra el comportamiento de Except.")</span><span class="sxs-lookup"><span data-stu-id="33182-131">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
[!code-csharp-interactive[Except](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#2)]

### <a name="intersect"></a><span data-ttu-id="33182-132">Formar intersección</span><span class="sxs-lookup"><span data-stu-id="33182-132">Intersect</span></span>  

 <span data-ttu-id="33182-133">En el ejemplo siguiente se muestra el comportamiento de <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="33182-133">The following example depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="33182-134">La secuencia devuelta contiene los elementos que son comunes a las dos secuencias de entrada.</span><span class="sxs-lookup"><span data-stu-id="33182-134">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![Gráfico en el que se muestra la intersección de dos secuencias.](./media/set-operations/intersection-two-sequences.png)  

[!code-csharp-interactive[Intersect](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#3)]

### <a name="union"></a><span data-ttu-id="33182-136">Unión</span><span class="sxs-lookup"><span data-stu-id="33182-136">Union</span></span>  

 <span data-ttu-id="33182-137">En el siguiente ejemplo se muestra una operación de unión en dos secuencias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="33182-137">The following example depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="33182-138">La secuencia devuelta contiene los elementos únicos de las dos secuencias de entrada.</span><span class="sxs-lookup"><span data-stu-id="33182-138">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![Gráfico en el que se muestra la unión de dos secuencias.](./media/set-operations/union-operation-two-sequences.png)  

[!code-csharp-interactive[Union](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#4)]

## <a name="see-also"></a><span data-ttu-id="33182-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33182-140">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="33182-141">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="33182-141">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="33182-142">Procedimiento para combinar y comparar colecciones de cadenas (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="33182-142">How to combine and compare string collections (LINQ) (C#)</span></span>](./how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="33182-143">Procedimiento para buscar la diferencia de conjuntos entre dos listas (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="33182-143">How to find the set difference between two lists (LINQ) (C#)</span></span>](./how-to-find-the-set-difference-between-two-lists-linq.md)
