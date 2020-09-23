---
title: Operaciones de agregación
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 1cf82d8acfdb1f8b0fc33c324064574b0dd01f4a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078403"
---
# <a name="aggregation-operations-visual-basic"></a><span data-ttu-id="be3aa-102">Operaciones de agregación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be3aa-102">Aggregation Operations (Visual Basic)</span></span>

<span data-ttu-id="be3aa-103">Una operación de agregación calcula un valor único a partir de una colección de valores.</span><span class="sxs-lookup"><span data-stu-id="be3aa-103">An aggregation operation computes a single value from a collection of values.</span></span> <span data-ttu-id="be3aa-104">Un ejemplo de operación de agregación es calcular el promedio de temperatura diaria a partir de los valores de temperatura diaria durante un mes.</span><span class="sxs-lookup"><span data-stu-id="be3aa-104">An example of an aggregation operation is calculating the average daily temperature from a month's worth of daily temperature values.</span></span>  
  
 <span data-ttu-id="be3aa-105">En la siguiente ilustración se muestran los resultados de dos operaciones de agregación diferentes en una secuencia de números.</span><span class="sxs-lookup"><span data-stu-id="be3aa-105">The following illustration shows the results of two different aggregation operations on a sequence of numbers.</span></span> <span data-ttu-id="be3aa-106">La primera operación suma los números.</span><span class="sxs-lookup"><span data-stu-id="be3aa-106">The first operation sums the numbers.</span></span> <span data-ttu-id="be3aa-107">La segunda operación devuelve el valor máximo de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="be3aa-107">The second operation returns the maximum value in the sequence.</span></span>  
  
 ![Ilustración en la que se muestran operaciones de agregación en LINQ.](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 <span data-ttu-id="be3aa-109">Los métodos del operador de consulta estándar que realizan operaciones de agregación se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="be3aa-109">The standard query operator methods that perform aggregation operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be3aa-110">Métodos</span><span class="sxs-lookup"><span data-stu-id="be3aa-110">Methods</span></span>  
  
|<span data-ttu-id="be3aa-111">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="be3aa-111">Method Name</span></span>|<span data-ttu-id="be3aa-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="be3aa-112">Description</span></span>|<span data-ttu-id="be3aa-113">Visual Basic sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="be3aa-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="be3aa-114">Más información</span><span class="sxs-lookup"><span data-stu-id="be3aa-114">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="be3aa-115">Agregar</span><span class="sxs-lookup"><span data-stu-id="be3aa-115">Aggregate</span></span>|<span data-ttu-id="be3aa-116">Realiza una operación de agregación personalizada en los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="be3aa-116">Performs a custom aggregation operation on the values of a collection.</span></span>|<span data-ttu-id="be3aa-117">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="be3aa-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="be3aa-118">Average</span><span class="sxs-lookup"><span data-stu-id="be3aa-118">Average</span></span>|<span data-ttu-id="be3aa-119">Calcula el valor medio de una colección de valores.</span><span class="sxs-lookup"><span data-stu-id="be3aa-119">Calculates the average value of a collection of values.</span></span>|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="be3aa-120">Recuento</span><span class="sxs-lookup"><span data-stu-id="be3aa-120">Count</span></span>|<span data-ttu-id="be3aa-121">Cuenta los elementos de una colección; opcionalmente, solo aquellos que satisfacen una función de predicado.</span><span class="sxs-lookup"><span data-stu-id="be3aa-121">Counts the elements in a collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="be3aa-122">LongCount</span><span class="sxs-lookup"><span data-stu-id="be3aa-122">LongCount</span></span>|<span data-ttu-id="be3aa-123">Cuenta los elementos de una gran colección; opcionalmente, solo aquellos que satisfacen una función de predicado.</span><span class="sxs-lookup"><span data-stu-id="be3aa-123">Counts the elements in a large collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="be3aa-124">Máx.</span><span class="sxs-lookup"><span data-stu-id="be3aa-124">Max</span></span>|<span data-ttu-id="be3aa-125">Determina el valor máximo de una colección.</span><span class="sxs-lookup"><span data-stu-id="be3aa-125">Determines the maximum value in a collection.</span></span>|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="be3aa-126">Mín.</span><span class="sxs-lookup"><span data-stu-id="be3aa-126">Min</span></span>|<span data-ttu-id="be3aa-127">Determina el valor mínimo de una colección.</span><span class="sxs-lookup"><span data-stu-id="be3aa-127">Determines the minimum value in a collection.</span></span>|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="be3aa-128">Sum</span><span class="sxs-lookup"><span data-stu-id="be3aa-128">Sum</span></span>|<span data-ttu-id="be3aa-129">Calcula la suma de los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="be3aa-129">Calculates the sum of the values in a collection.</span></span>|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="be3aa-130">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="be3aa-130">Query Expression Syntax Examples</span></span>  
  
### <a name="average"></a><span data-ttu-id="be3aa-131">Average</span><span class="sxs-lookup"><span data-stu-id="be3aa-131">Average</span></span>  

 <span data-ttu-id="be3aa-132">En el ejemplo de código siguiente `Aggregate Into Average` se usa la cláusula en Visual Basic para calcular la temperatura media de una matriz de números que representan temperaturas.</span><span class="sxs-lookup"><span data-stu-id="be3aa-132">The following code example uses the `Aggregate Into Average` clause in Visual Basic to calculate the average temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#1)]  
  
### <a name="count"></a><span data-ttu-id="be3aa-133">Count</span><span class="sxs-lookup"><span data-stu-id="be3aa-133">Count</span></span>  

 <span data-ttu-id="be3aa-134">En el ejemplo de código siguiente `Aggregate Into Count` se usa la cláusula en Visual Basic para contar el número de valores de una matriz que son mayores o iguales que 80.</span><span class="sxs-lookup"><span data-stu-id="be3aa-134">The following code example uses the `Aggregate Into Count` clause in Visual Basic to count the number of values in an array that are greater than or equal to 80.</span></span>  
  
 [!code-vb[CsLINQAggregating#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#2)]  
  
### <a name="longcount"></a><span data-ttu-id="be3aa-135">LongCount</span><span class="sxs-lookup"><span data-stu-id="be3aa-135">LongCount</span></span>  

 <span data-ttu-id="be3aa-136">En el ejemplo de código siguiente `Aggregate Into LongCount` se usa la cláusula para contar el número de valores de una matriz.</span><span class="sxs-lookup"><span data-stu-id="be3aa-136">The following code example uses the `Aggregate Into LongCount` clause to count the number of values in an array.</span></span>  
  
 [!code-vb[CsLINQAggregating#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#3)]  
  
### <a name="max"></a><span data-ttu-id="be3aa-137">Max</span><span class="sxs-lookup"><span data-stu-id="be3aa-137">Max</span></span>  

 <span data-ttu-id="be3aa-138">En el ejemplo de código siguiente `Aggregate Into Max` se usa la cláusula para calcular la temperatura máxima de una matriz de números que representan temperaturas.</span><span class="sxs-lookup"><span data-stu-id="be3aa-138">The following code example uses the `Aggregate Into Max` clause  to calculate the maximum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#4)]  
  
### <a name="min"></a><span data-ttu-id="be3aa-139">Min</span><span class="sxs-lookup"><span data-stu-id="be3aa-139">Min</span></span>  

 <span data-ttu-id="be3aa-140">En el ejemplo de código siguiente `Aggregate Into Min` se usa la cláusula para calcular la temperatura mínima de una matriz de números que representan temperaturas.</span><span class="sxs-lookup"><span data-stu-id="be3aa-140">The following code example uses the `Aggregate Into Min` clause  to calculate the minimum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#5)]  
  
### <a name="sum"></a><span data-ttu-id="be3aa-141">Sum</span><span class="sxs-lookup"><span data-stu-id="be3aa-141">Sum</span></span>  

 <span data-ttu-id="be3aa-142">En el ejemplo de código siguiente `Aggregate Into Sum` se usa la cláusula para calcular el importe total de los gastos de una matriz de valores que representan gastos.</span><span class="sxs-lookup"><span data-stu-id="be3aa-142">The following code example uses the `Aggregate Into Sum` clause  to calculate the total expense amount from an array of values that represent expenses.</span></span>  
  
 [!code-vb[CsLINQAggregating#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="be3aa-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="be3aa-143">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="be3aa-144">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be3aa-144">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="be3aa-145">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="be3aa-145">Aggregate Clause</span></span>](../../../language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="be3aa-146">Cómo: calcular valores de columna en un archivo de texto CSV (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be3aa-146">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [<span data-ttu-id="be3aa-147">Cómo: Hacer el recuento, la suma o el promedio de datos</span><span class="sxs-lookup"><span data-stu-id="be3aa-147">How to: Count, Sum, or Average Data</span></span>](../../language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)
- [<span data-ttu-id="be3aa-148">Cómo: Buscar los valores máximo y mínimo en el resultado de una consulta</span><span class="sxs-lookup"><span data-stu-id="be3aa-148">How to: Find the Minimum or Maximum Value in a Query Result</span></span>](../../language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)
- [<span data-ttu-id="be3aa-149">Cómo buscar el archivo o archivos de mayor tamaño en un árbol de directorios (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be3aa-149">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [<span data-ttu-id="be3aa-150">Cómo: buscar el número total de bytes en un conjunto de carpetas (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be3aa-150">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
