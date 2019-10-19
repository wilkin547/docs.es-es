---
title: Operaciones Set (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: fe8dbff00ecd6da9b3b0e9792e67422583a00180
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582922"
---
# <a name="set-operations-visual-basic"></a><span data-ttu-id="954c1-102">Operaciones Set (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="954c1-102">Set Operations (Visual Basic)</span></span>

<span data-ttu-id="954c1-103">Las operaciones set de LINQ se refieren a operaciones de consulta que generan un conjunto de resultados en función de la presencia o ausencia de elementos equivalentes dentro de la misma colección o en distintas colecciones (o conjuntos).</span><span class="sxs-lookup"><span data-stu-id="954c1-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>

<span data-ttu-id="954c1-104">Los métodos del operador de consulta estándar que realizan operaciones set se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="954c1-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="954c1-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="954c1-105">Methods</span></span>

|<span data-ttu-id="954c1-106">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="954c1-106">Method Name</span></span>|<span data-ttu-id="954c1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="954c1-107">Description</span></span>|<span data-ttu-id="954c1-108">Visual Basic sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="954c1-108">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="954c1-109">Más información</span><span class="sxs-lookup"><span data-stu-id="954c1-109">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="954c1-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="954c1-110">Distinct</span></span>|<span data-ttu-id="954c1-111">Quita valores duplicados de una colección.</span><span class="sxs-lookup"><span data-stu-id="954c1-111">Removes duplicate values from a collection.</span></span>|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|
|<span data-ttu-id="954c1-112">Except</span><span class="sxs-lookup"><span data-stu-id="954c1-112">Except</span></span>|<span data-ttu-id="954c1-113">Devuelve la diferencia de conjuntos, es decir, los elementos de una colección que no aparecen en una segunda colección.</span><span class="sxs-lookup"><span data-stu-id="954c1-113">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="954c1-114">No disponible.</span><span class="sxs-lookup"><span data-stu-id="954c1-114">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|
|<span data-ttu-id="954c1-115">Formar intersección</span><span class="sxs-lookup"><span data-stu-id="954c1-115">Intersect</span></span>|<span data-ttu-id="954c1-116">Devuelve la intersección de conjuntos, es decir, los elementos que aparecen en las dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="954c1-116">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="954c1-117">No disponible.</span><span class="sxs-lookup"><span data-stu-id="954c1-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|
|<span data-ttu-id="954c1-118">Unión</span><span class="sxs-lookup"><span data-stu-id="954c1-118">Union</span></span>|<span data-ttu-id="954c1-119">Devuelve la unión de conjuntos, es decir, los elementos únicos que aparecen en una de las dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="954c1-119">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="954c1-120">No disponible.</span><span class="sxs-lookup"><span data-stu-id="954c1-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|

## <a name="comparison-of-set-operations"></a><span data-ttu-id="954c1-121">Comparación de operaciones set</span><span class="sxs-lookup"><span data-stu-id="954c1-121">Comparison of Set Operations</span></span>

### <a name="distinct"></a><span data-ttu-id="954c1-122">Distinct</span><span class="sxs-lookup"><span data-stu-id="954c1-122">Distinct</span></span>

<span data-ttu-id="954c1-123">En la siguiente ilustración se muestra el comportamiento del método <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> en una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="954c1-123">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="954c1-124">La secuencia devuelta contiene los elementos únicos de la secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="954c1-124">The returned sequence contains the unique elements from the input sequence.</span></span>

![Gráfico en el que se muestra el comportamiento de Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)

### <a name="except"></a><span data-ttu-id="954c1-126">Except</span><span class="sxs-lookup"><span data-stu-id="954c1-126">Except</span></span>

<span data-ttu-id="954c1-127">En la siguiente ilustración se muestra el comportamiento de <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="954c1-127">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="954c1-128">La secuencia devuelta solo contiene los elementos de la primera secuencia de entrada que no están en la segunda secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="954c1-128">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>

<span data-ttu-id="954c1-129">![Gráfico que muestra la acción de&#40;&#41;excepto.](./media/set-operations/except-behavior-graphic.png "Muestra el comportamiento de excepto.")</span><span class="sxs-lookup"><span data-stu-id="954c1-129">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>

### <a name="intersect"></a><span data-ttu-id="954c1-130">Formar intersección</span><span class="sxs-lookup"><span data-stu-id="954c1-130">Intersect</span></span>

<span data-ttu-id="954c1-131">En la siguiente ilustración se muestra el comportamiento de <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="954c1-131">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="954c1-132">La secuencia devuelta contiene los elementos que son comunes a las dos secuencias de entrada.</span><span class="sxs-lookup"><span data-stu-id="954c1-132">The returned sequence contains the elements that are common to both of the input sequences.</span></span>

![Gráfico mostrando la intersección de dos secuencias.](./media/set-operations/intersection-two-sequences.png)

### <a name="union"></a><span data-ttu-id="954c1-134">Unión</span><span class="sxs-lookup"><span data-stu-id="954c1-134">Union</span></span>

<span data-ttu-id="954c1-135">En la siguiente ilustración se muestra una operación de unión en dos secuencias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="954c1-135">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="954c1-136">La secuencia devuelta contiene los elementos únicos de las dos secuencias de entrada.</span><span class="sxs-lookup"><span data-stu-id="954c1-136">The returned sequence contains the unique elements from both input sequences.</span></span>

![Gráfico mostrando la unión de dos secuencias.](./media/set-operations/union-operation-two-sequences.png)

## <a name="query-expression-syntax-example"></a><span data-ttu-id="954c1-138">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="954c1-138">Query Expression Syntax Example</span></span>

<span data-ttu-id="954c1-139">En el ejemplo siguiente se usa la cláusula `Distinct` en una consulta LINQ para devolver los números únicos de una lista de enteros.</span><span class="sxs-lookup"><span data-stu-id="954c1-139">The following example uses the `Distinct` clause in a LINQ query to return the unique numbers from a list of integers.</span></span>

[!code-vb[CsLINQSetOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQSetOps/VB/setops.vb#1)]

## <a name="see-also"></a><span data-ttu-id="954c1-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="954c1-140">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="954c1-141">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="954c1-141">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="954c1-142">Distinct (cláusula)</span><span class="sxs-lookup"><span data-stu-id="954c1-142">Distinct Clause</span></span>](../../../../visual-basic/language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="954c1-143">Cómo: combinar y comparar colecciones de cadenas (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="954c1-143">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="954c1-144">Cómo: buscar la diferencia de conjuntos entre dos listas (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="954c1-144">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
