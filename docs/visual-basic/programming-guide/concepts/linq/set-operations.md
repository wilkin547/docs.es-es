---
description: 'Más información acerca de: operaciones Set (Visual Basic)'
title: Operaciones Set
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: 9c75c9e029ba260917f59c7d2ea0341c157bf406
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471674"
---
# <a name="set-operations-visual-basic"></a><span data-ttu-id="1b808-103">Operaciones Set (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b808-103">Set Operations (Visual Basic)</span></span>

<span data-ttu-id="1b808-104">Las operaciones set de LINQ se refieren a operaciones de consulta que generan un conjunto de resultados en función de la presencia o ausencia de elementos equivalentes dentro de la misma colección o en distintas colecciones (o conjuntos).</span><span class="sxs-lookup"><span data-stu-id="1b808-104">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>

<span data-ttu-id="1b808-105">Los métodos del operador de consulta estándar que realizan operaciones set se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="1b808-105">The standard query operator methods that perform set operations are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="1b808-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="1b808-106">Methods</span></span>

|<span data-ttu-id="1b808-107">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="1b808-107">Method Name</span></span>|<span data-ttu-id="1b808-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b808-108">Description</span></span>|<span data-ttu-id="1b808-109">Visual Basic sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="1b808-109">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="1b808-110">Más información</span><span class="sxs-lookup"><span data-stu-id="1b808-110">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="1b808-111">Distinct</span><span class="sxs-lookup"><span data-stu-id="1b808-111">Distinct</span></span>|<span data-ttu-id="1b808-112">Quita valores duplicados de una colección.</span><span class="sxs-lookup"><span data-stu-id="1b808-112">Removes duplicate values from a collection.</span></span>|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|
|<span data-ttu-id="1b808-113">Except</span><span class="sxs-lookup"><span data-stu-id="1b808-113">Except</span></span>|<span data-ttu-id="1b808-114">Devuelve la diferencia de conjuntos, es decir, los elementos de una colección que no aparecen en una segunda colección.</span><span class="sxs-lookup"><span data-stu-id="1b808-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="1b808-115">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="1b808-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|
|<span data-ttu-id="1b808-116">Formar intersección</span><span class="sxs-lookup"><span data-stu-id="1b808-116">Intersect</span></span>|<span data-ttu-id="1b808-117">Devuelve la intersección de conjuntos, es decir, los elementos que aparecen en las dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="1b808-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="1b808-118">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="1b808-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|
|<span data-ttu-id="1b808-119">Unión</span><span class="sxs-lookup"><span data-stu-id="1b808-119">Union</span></span>|<span data-ttu-id="1b808-120">Devuelve la unión de conjuntos, es decir, los elementos únicos que aparecen en una de las dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="1b808-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="1b808-121">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="1b808-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|

## <a name="comparison-of-set-operations"></a><span data-ttu-id="1b808-122">Comparación de operaciones set</span><span class="sxs-lookup"><span data-stu-id="1b808-122">Comparison of Set Operations</span></span>

### <a name="distinct"></a><span data-ttu-id="1b808-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="1b808-123">Distinct</span></span>

<span data-ttu-id="1b808-124">En la siguiente ilustración se muestra el comportamiento del método <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> en una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1b808-124">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="1b808-125">La secuencia devuelta contiene los elementos únicos de la secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="1b808-125">The returned sequence contains the unique elements from the input sequence.</span></span>

![Gráfico en el que se muestra el comportamiento de Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)

### <a name="except"></a><span data-ttu-id="1b808-127">Except</span><span class="sxs-lookup"><span data-stu-id="1b808-127">Except</span></span>

<span data-ttu-id="1b808-128">En la siguiente ilustración se muestra el comportamiento de <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1b808-128">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1b808-129">La secuencia devuelta solo contiene los elementos de la primera secuencia de entrada que no están en la segunda secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="1b808-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>

<span data-ttu-id="1b808-130">![Gráfico que muestra la acción de Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Muestra el comportamiento de Except.")</span><span class="sxs-lookup"><span data-stu-id="1b808-130">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>

### <a name="intersect"></a><span data-ttu-id="1b808-131">Formar intersección</span><span class="sxs-lookup"><span data-stu-id="1b808-131">Intersect</span></span>

<span data-ttu-id="1b808-132">En la siguiente ilustración se muestra el comportamiento de <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1b808-132">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1b808-133">La secuencia devuelta contiene los elementos que son comunes a las dos secuencias de entrada.</span><span class="sxs-lookup"><span data-stu-id="1b808-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>

![Gráfico en el que se muestra la intersección de dos secuencias.](./media/set-operations/intersection-two-sequences.png)

### <a name="union"></a><span data-ttu-id="1b808-135">Unión</span><span class="sxs-lookup"><span data-stu-id="1b808-135">Union</span></span>

<span data-ttu-id="1b808-136">En la siguiente ilustración se muestra una operación de unión en dos secuencias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1b808-136">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="1b808-137">La secuencia devuelta contiene los elementos únicos de las dos secuencias de entrada.</span><span class="sxs-lookup"><span data-stu-id="1b808-137">The returned sequence contains the unique elements from both input sequences.</span></span>

![Gráfico en el que se muestra la unión de dos secuencias.](./media/set-operations/union-operation-two-sequences.png)

## <a name="query-expression-syntax-example"></a><span data-ttu-id="1b808-139">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="1b808-139">Query Expression Syntax Example</span></span>

<span data-ttu-id="1b808-140">En el ejemplo siguiente se usa la `Distinct` cláusula en una consulta LINQ para devolver los números únicos de una lista de enteros.</span><span class="sxs-lookup"><span data-stu-id="1b808-140">The following example uses the `Distinct` clause in a LINQ query to return the unique numbers from a list of integers.</span></span>

[!code-vb[CsLINQSetOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQSetOps/VB/setops.vb#1)]

## <a name="see-also"></a><span data-ttu-id="1b808-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1b808-141">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="1b808-142">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b808-142">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="1b808-143">Cláusula Distinct</span><span class="sxs-lookup"><span data-stu-id="1b808-143">Distinct Clause</span></span>](../../../language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="1b808-144">Cómo: combinar y comparar colecciones de cadenas (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b808-144">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="1b808-145">Cómo: buscar la diferencia de conjuntos entre dos listas (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b808-145">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)
