---
title: Operaciones de agregación (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 5d8e5c589b19527062f7752b2f795c8396683bbd
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675645"
---
# <a name="aggregation-operations-visual-basic"></a><span data-ttu-id="0c34b-102">Operaciones de agregación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c34b-102">Aggregation Operations (Visual Basic)</span></span>
<span data-ttu-id="0c34b-103">Una operación de agregación calcula un valor único a partir de una colección de valores.</span><span class="sxs-lookup"><span data-stu-id="0c34b-103">An aggregation operation computes a single value from a collection of values.</span></span> <span data-ttu-id="0c34b-104">Un ejemplo de operación de agregación es calcular el promedio de temperatura diaria a partir de los valores de temperatura diaria durante un mes.</span><span class="sxs-lookup"><span data-stu-id="0c34b-104">An example of an aggregation operation is calculating the average daily temperature from a month's worth of daily temperature values.</span></span>  
  
 <span data-ttu-id="0c34b-105">En la siguiente ilustración se muestran los resultados de dos operaciones de agregación diferentes en una secuencia de números.</span><span class="sxs-lookup"><span data-stu-id="0c34b-105">The following illustration shows the results of two different aggregation operations on a sequence of numbers.</span></span> <span data-ttu-id="0c34b-106">La primera operación suma los números.</span><span class="sxs-lookup"><span data-stu-id="0c34b-106">The first operation sums the numbers.</span></span> <span data-ttu-id="0c34b-107">La segunda operación devuelve el valor máximo de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="0c34b-107">The second operation returns the maximum value in the sequence.</span></span>  
  
 ![Ilustración que muestra las operaciones de agregación en LINQ.](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 <span data-ttu-id="0c34b-109">Los métodos del operador de consulta estándar que realizan operaciones de agregación se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="0c34b-109">The standard query operator methods that perform aggregation operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c34b-110">Métodos</span><span class="sxs-lookup"><span data-stu-id="0c34b-110">Methods</span></span>  
  
|<span data-ttu-id="0c34b-111">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="0c34b-111">Method Name</span></span>|<span data-ttu-id="0c34b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c34b-112">Description</span></span>|<span data-ttu-id="0c34b-113">Sintaxis de expresión de consulta de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0c34b-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="0c34b-114">Más información</span><span class="sxs-lookup"><span data-stu-id="0c34b-114">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="0c34b-115">Agregar</span><span class="sxs-lookup"><span data-stu-id="0c34b-115">Aggregate</span></span>|<span data-ttu-id="0c34b-116">Realiza una operación de agregación personalizada en los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="0c34b-116">Performs a custom aggregation operation on the values of a collection.</span></span>|<span data-ttu-id="0c34b-117">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="0c34b-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0c34b-118">Average</span><span class="sxs-lookup"><span data-stu-id="0c34b-118">Average</span></span>|<span data-ttu-id="0c34b-119">Calcula el valor medio de una colección de valores.</span><span class="sxs-lookup"><span data-stu-id="0c34b-119">Calculates the average value of a collection of values.</span></span>|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0c34b-120">Recuento</span><span class="sxs-lookup"><span data-stu-id="0c34b-120">Count</span></span>|<span data-ttu-id="0c34b-121">Cuenta los elementos de una colección; opcionalmente, solo aquellos que satisfacen una función de predicado.</span><span class="sxs-lookup"><span data-stu-id="0c34b-121">Counts the elements in a collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0c34b-122">LongCount</span><span class="sxs-lookup"><span data-stu-id="0c34b-122">LongCount</span></span>|<span data-ttu-id="0c34b-123">Cuenta los elementos de una gran colección; opcionalmente, solo aquellos que satisfacen una función de predicado.</span><span class="sxs-lookup"><span data-stu-id="0c34b-123">Counts the elements in a large collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0c34b-124">Máx.</span><span class="sxs-lookup"><span data-stu-id="0c34b-124">Max</span></span>|<span data-ttu-id="0c34b-125">Determina el valor máximo de una colección.</span><span class="sxs-lookup"><span data-stu-id="0c34b-125">Determines the maximum value in a collection.</span></span>|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0c34b-126">Mín.</span><span class="sxs-lookup"><span data-stu-id="0c34b-126">Min</span></span>|<span data-ttu-id="0c34b-127">Determina el valor mínimo de una colección.</span><span class="sxs-lookup"><span data-stu-id="0c34b-127">Determines the minimum value in a collection.</span></span>|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0c34b-128">Sum</span><span class="sxs-lookup"><span data-stu-id="0c34b-128">Sum</span></span>|<span data-ttu-id="0c34b-129">Calcula la suma de los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="0c34b-129">Calculates the sum of the values in a collection.</span></span>|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="0c34b-130">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="0c34b-130">Query Expression Syntax Examples</span></span>  
  
### <a name="average"></a><span data-ttu-id="0c34b-131">Average</span><span class="sxs-lookup"><span data-stu-id="0c34b-131">Average</span></span>  
 <span data-ttu-id="0c34b-132">El siguiente ejemplo de código utiliza el `Aggregate Into Average` cláusula en Visual Basic para calcular el promedio de temperatura en una matriz de números que representan las temperaturas.</span><span class="sxs-lookup"><span data-stu-id="0c34b-132">The following code example uses the `Aggregate Into Average` clause in Visual Basic to calculate the average temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#1)]  
  
### <a name="count"></a><span data-ttu-id="0c34b-133">Recuento</span><span class="sxs-lookup"><span data-stu-id="0c34b-133">Count</span></span>  
 <span data-ttu-id="0c34b-134">El siguiente ejemplo de código utiliza el `Aggregate Into Count` cláusula en Visual Basic para contar el número de valores de una matriz que son mayores que o igual a 80.</span><span class="sxs-lookup"><span data-stu-id="0c34b-134">The following code example uses the `Aggregate Into Count` clause in Visual Basic to count the number of values in an array that are greater than or equal to 80.</span></span>  
  
 [!code-vb[CsLINQAggregating#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#2)]  
  
### <a name="longcount"></a><span data-ttu-id="0c34b-135">LongCount</span><span class="sxs-lookup"><span data-stu-id="0c34b-135">LongCount</span></span>  
 <span data-ttu-id="0c34b-136">El siguiente ejemplo de código utiliza el `Aggregate Into LongCount` cláusula para contar el número de valores en una matriz.</span><span class="sxs-lookup"><span data-stu-id="0c34b-136">The following code example uses the `Aggregate Into LongCount` clause to count the number of values in an array.</span></span>  
  
 [!code-vb[CsLINQAggregating#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#3)]  
  
### <a name="max"></a><span data-ttu-id="0c34b-137">Máx.</span><span class="sxs-lookup"><span data-stu-id="0c34b-137">Max</span></span>  
 <span data-ttu-id="0c34b-138">El siguiente ejemplo de código utiliza el `Aggregate Into Max` cláusula para calcular la temperatura máxima en una matriz de números que representan las temperaturas.</span><span class="sxs-lookup"><span data-stu-id="0c34b-138">The following code example uses the `Aggregate Into Max` clause  to calculate the maximum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#4)]  
  
### <a name="min"></a><span data-ttu-id="0c34b-139">Mín.</span><span class="sxs-lookup"><span data-stu-id="0c34b-139">Min</span></span>  
 <span data-ttu-id="0c34b-140">El siguiente ejemplo de código utiliza el `Aggregate Into Min` cláusula para calcular la temperatura mínima en una matriz de números que representan las temperaturas.</span><span class="sxs-lookup"><span data-stu-id="0c34b-140">The following code example uses the `Aggregate Into Min` clause  to calculate the minimum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#5)]  
  
### <a name="sum"></a><span data-ttu-id="0c34b-141">Sum</span><span class="sxs-lookup"><span data-stu-id="0c34b-141">Sum</span></span>  
 <span data-ttu-id="0c34b-142">El siguiente ejemplo de código utiliza el `Aggregate Into Sum` cláusula para calcular el importe del gasto total de una matriz de valores que representan los gastos.</span><span class="sxs-lookup"><span data-stu-id="0c34b-142">The following code example uses the `Aggregate Into Sum` clause  to calculate the total expense amount from an array of values that represent expenses.</span></span>  
  
 [!code-vb[CsLINQAggregating#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="0c34b-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c34b-143">See also</span></span>
- <xref:System.Linq>
- [<span data-ttu-id="0c34b-144">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c34b-144">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="0c34b-145">Aggregate (cláusula)</span><span class="sxs-lookup"><span data-stu-id="0c34b-145">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="0c34b-146">Cómo: Calcular valores de columna en un archivo de texto CSV (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c34b-146">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [<span data-ttu-id="0c34b-147">Cómo: Recuento, suma o promedio de datos</span><span class="sxs-lookup"><span data-stu-id="0c34b-147">How to: Count, Sum, or Average Data</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)
- [<span data-ttu-id="0c34b-148">Cómo: Buscar el valor mínimo o máximo en un resultado de consulta</span><span class="sxs-lookup"><span data-stu-id="0c34b-148">How to: Find the Minimum or Maximum Value in a Query Result</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)
- [<span data-ttu-id="0c34b-149">Cómo: Consulta para el archivo de mayor tamaño o archivos en un árbol de directorios (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c34b-149">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [<span data-ttu-id="0c34b-150">Cómo: Buscar el número Total de Bytes en un conjunto de carpetas (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c34b-150">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
