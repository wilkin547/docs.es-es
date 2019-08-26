---
title: Operaciones set (C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: cea0c0ba4dd6c7f874f69e3ec4a179248397b67d
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69591117"
---
# <a name="set-operations-c"></a><span data-ttu-id="1d119-102">Operaciones set (C#)</span><span class="sxs-lookup"><span data-stu-id="1d119-102">Set Operations (C#)</span></span>
<span data-ttu-id="1d119-103">Las operaciones set de LINQ se refieren a operaciones de consulta que generan un conjunto de resultados en función de la presencia o ausencia de elementos equivalentes dentro de la misma colección o en distintas colecciones (o conjuntos).</span><span class="sxs-lookup"><span data-stu-id="1d119-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="1d119-104">Los métodos del operador de consulta estándar que realizan operaciones set se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="1d119-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1d119-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1d119-105">Methods</span></span>  
  
|<span data-ttu-id="1d119-106">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="1d119-106">Method Name</span></span>|<span data-ttu-id="1d119-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1d119-107">Description</span></span>|<span data-ttu-id="1d119-108">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="1d119-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="1d119-109">Más información</span><span class="sxs-lookup"><span data-stu-id="1d119-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="1d119-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="1d119-110">Distinct</span></span>|<span data-ttu-id="1d119-111">Quita valores duplicados de una colección.</span><span class="sxs-lookup"><span data-stu-id="1d119-111">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="1d119-112">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="1d119-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="1d119-113">Except</span><span class="sxs-lookup"><span data-stu-id="1d119-113">Except</span></span>|<span data-ttu-id="1d119-114">Devuelve la diferencia de conjuntos, es decir, los elementos de una colección que no aparecen en una segunda colección.</span><span class="sxs-lookup"><span data-stu-id="1d119-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="1d119-115">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="1d119-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="1d119-116">Formar intersección</span><span class="sxs-lookup"><span data-stu-id="1d119-116">Intersect</span></span>|<span data-ttu-id="1d119-117">Devuelve la intersección de conjuntos, es decir, los elementos que aparecen en las dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="1d119-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="1d119-118">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="1d119-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="1d119-119">Unión</span><span class="sxs-lookup"><span data-stu-id="1d119-119">Union</span></span>|<span data-ttu-id="1d119-120">Devuelve la unión de conjuntos, es decir, los elementos únicos que aparecen en una de las dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="1d119-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="1d119-121">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="1d119-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="1d119-122">Comparación de operaciones set</span><span class="sxs-lookup"><span data-stu-id="1d119-122">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="1d119-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="1d119-123">Distinct</span></span>  
 <span data-ttu-id="1d119-124">En la siguiente ilustración se muestra el comportamiento del método <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> en una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1d119-124">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="1d119-125">La secuencia devuelta contiene los elementos únicos de la secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="1d119-125">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![Gráfico en el que se muestra el comportamiento de Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)  
  
### <a name="except"></a><span data-ttu-id="1d119-127">Except</span><span class="sxs-lookup"><span data-stu-id="1d119-127">Except</span></span>  
 <span data-ttu-id="1d119-128">En la siguiente ilustración se muestra el comportamiento de <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1d119-128">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1d119-129">La secuencia devuelta solo contiene los elementos de la primera secuencia de entrada que no están en la segunda secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="1d119-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="1d119-130">![Gráfico que muestra la acción de Except&#40;&#41;. ](./media/set-operations/except-behavior-graphic.png "Muestra el comportamiento de Except.")</span><span class="sxs-lookup"><span data-stu-id="1d119-130">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="1d119-131">Formar intersección</span><span class="sxs-lookup"><span data-stu-id="1d119-131">Intersect</span></span>  
 <span data-ttu-id="1d119-132">En la siguiente ilustración se muestra el comportamiento de <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1d119-132">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1d119-133">La secuencia devuelta contiene los elementos que son comunes a las dos secuencias de entrada.</span><span class="sxs-lookup"><span data-stu-id="1d119-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![Gráfico en el que se muestra la intersección de dos secuencias.](./media/set-operations/intersection-two-sequences.png)  
 
### <a name="union"></a><span data-ttu-id="1d119-135">Unión</span><span class="sxs-lookup"><span data-stu-id="1d119-135">Union</span></span>  
 <span data-ttu-id="1d119-136">En la siguiente ilustración se muestra una operación de unión en dos secuencias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1d119-136">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="1d119-137">La secuencia devuelta contiene los elementos únicos de las dos secuencias de entrada.</span><span class="sxs-lookup"><span data-stu-id="1d119-137">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![Gráfico en el que se muestra la unión de dos secuencias.](./media/set-operations/union-operation-two-sequences.png)  
## <a name="see-also"></a><span data-ttu-id="1d119-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d119-139">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="1d119-140">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="1d119-140">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="1d119-141">Cómo: Combinar y comparar colecciones de cadenas (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="1d119-141">How to: Combine and Compare String Collections (LINQ) (C#)</span></span>](./how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="1d119-142">Cómo: Buscar la diferencia de conjuntos entre dos listas (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="1d119-142">How to: Find the Set Difference Between Two Lists (LINQ) (C#)</span></span>](./how-to-find-the-set-difference-between-two-lists-linq.md)
