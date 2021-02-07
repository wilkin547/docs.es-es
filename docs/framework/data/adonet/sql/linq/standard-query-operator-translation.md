---
description: 'Más información acerca de: traducción de operadores de consulta estándar'
title: Traslación del operador de consulta estándar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a60c30fa-1e68-45fe-b984-f6abb9ede40e
ms.openlocfilehash: e7e45e8f27f1e7d3c572f00ea014b4edb288b2b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681531"
---
# <a name="standard-query-operator-translation"></a><span data-ttu-id="31718-103">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="31718-103">Standard Query Operator Translation</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="31718-104">convierte los operadores de consulta estándar en comandos SQL.</span><span class="sxs-lookup"><span data-stu-id="31718-104">translates Standard Query Operators to SQL commands.</span></span> <span data-ttu-id="31718-105">El procesador de consultas de la base de datos determina la semántica de ejecución de la conversión a SQL.</span><span class="sxs-lookup"><span data-stu-id="31718-105">The query processor of the database determines the execution semantics of SQL translation.</span></span>

<span data-ttu-id="31718-106">Los operadores de consulta estándar se definen en *secuencias*.</span><span class="sxs-lookup"><span data-stu-id="31718-106">Standard Query Operators are defined against *sequences*.</span></span> <span data-ttu-id="31718-107">Una secuencia se *ordena* y se basa en la identidad de referencia para cada elemento de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="31718-107">A sequence is *ordered* and relies on reference identity for each element of the sequence.</span></span> <span data-ttu-id="31718-108">Para obtener más información, vea información general sobre [operadores de consulta estándar (C#)](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) o [información general sobre operadores de consulta estándar (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="31718-108">For more information, see [Standard Query Operators Overview (C#)](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>

<span data-ttu-id="31718-109">SQL trata principalmente con *conjuntos de valores desordenados*.</span><span class="sxs-lookup"><span data-stu-id="31718-109">SQL deals primarily with *unordered sets of values*.</span></span> <span data-ttu-id="31718-110">La ordenación es normalmente una operación de procesamiento posterior declarada de forma explícita que se aplica al resultado final de una consulta en lugar de a los resultados intermedios.</span><span class="sxs-lookup"><span data-stu-id="31718-110">Ordering is typically an explicitly stated, post-processing operation that is applied to the final result of a query rather than to intermediate results.</span></span> <span data-ttu-id="31718-111">La identidad se define con valores.</span><span class="sxs-lookup"><span data-stu-id="31718-111">Identity is defined by values.</span></span> <span data-ttu-id="31718-112">Por esta razón, las consultas SQL se entienden para tratar con conjuntos (*bolsas*) en lugar de *conjuntos*.</span><span class="sxs-lookup"><span data-stu-id="31718-112">For this reason, SQL queries are understood to deal with multisets (*bags*) instead of *sets*.</span></span>

<span data-ttu-id="31718-113">En los párrafos siguientes se describen las diferencias entre los operadores de consulta estándar y su conversión a SQL para el proveedor de SQL Server de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31718-113">The following paragraphs describe the differences between the Standard Query Operators and their SQL translation for the SQL Server provider for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>

## <a name="operator-support"></a><span data-ttu-id="31718-114">Compatibilidad de los operadores</span><span class="sxs-lookup"><span data-stu-id="31718-114">Operator Support</span></span>

### <a name="concat"></a><span data-ttu-id="31718-115">Concat</span><span class="sxs-lookup"><span data-stu-id="31718-115">Concat</span></span>

<span data-ttu-id="31718-116">El método <xref:System.Linq.Enumerable.Concat%2A> se define para los conjuntos múltiples ordenados cuando el orden del receptor y el orden del argumento son iguales.</span><span class="sxs-lookup"><span data-stu-id="31718-116">The <xref:System.Linq.Enumerable.Concat%2A> method is defined for ordered multisets where the order of the receiver and the order of the argument are the same.</span></span> <span data-ttu-id="31718-117"><xref:System.Linq.Enumerable.Concat%2A> funciona como `UNION ALL` sobre los conjuntos múltiples después del orden común.</span><span class="sxs-lookup"><span data-stu-id="31718-117"><xref:System.Linq.Enumerable.Concat%2A> works as `UNION ALL` over the multisets followed by the common order.</span></span>

<span data-ttu-id="31718-118">El último paso es ordenar en SQL antes de que se generen los resultados.</span><span class="sxs-lookup"><span data-stu-id="31718-118">The final step is ordering in SQL before results are produced.</span></span> <span data-ttu-id="31718-119"><xref:System.Linq.Enumerable.Concat%2A> no conserva el orden de sus argumentos.</span><span class="sxs-lookup"><span data-stu-id="31718-119"><xref:System.Linq.Enumerable.Concat%2A> does not preserve the order of its arguments.</span></span> <span data-ttu-id="31718-120">Para garantizar una ordenación correcta, debe ordenar explícitamente los resultados de <xref:System.Linq.Enumerable.Concat%2A>.</span><span class="sxs-lookup"><span data-stu-id="31718-120">To ensure appropriate ordering, you must explicitly order the results of <xref:System.Linq.Enumerable.Concat%2A>.</span></span>

### <a name="intersect-except-union"></a><span data-ttu-id="31718-121">Intersect, Except, Union</span><span class="sxs-lookup"><span data-stu-id="31718-121">Intersect, Except, Union</span></span>

<span data-ttu-id="31718-122">Los métodos <xref:System.Linq.Enumerable.Intersect%2A> y <xref:System.Linq.Enumerable.Except%2A> se definen bien solo en los conjuntos.</span><span class="sxs-lookup"><span data-stu-id="31718-122">The <xref:System.Linq.Enumerable.Intersect%2A> and <xref:System.Linq.Enumerable.Except%2A> methods are well defined only on sets.</span></span> <span data-ttu-id="31718-123">La semántica de conjuntos múltiples no está definida.</span><span class="sxs-lookup"><span data-stu-id="31718-123">The semantics for multisets is undefined.</span></span>

<span data-ttu-id="31718-124">El método <xref:System.Linq.Enumerable.Union%2A> se define para los conjuntos múltiples como la concatenación no ordenada de los conjuntos múltiples (de hecho, el resultado de la cláusula UNION ALL en SQL).</span><span class="sxs-lookup"><span data-stu-id="31718-124">The <xref:System.Linq.Enumerable.Union%2A> method is defined for multisets as the unordered concatenation of the multisets (effectively the result of the UNION ALL clause in SQL).</span></span>

### <a name="take-skip"></a><span data-ttu-id="31718-125">Take, Skip</span><span class="sxs-lookup"><span data-stu-id="31718-125">Take, Skip</span></span>

<span data-ttu-id="31718-126"><xref:System.Linq.Enumerable.Take%2A><xref:System.Linq.Enumerable.Skip%2A>los métodos y están bien definidos solo en *conjuntos ordenados*.</span><span class="sxs-lookup"><span data-stu-id="31718-126"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> methods are well defined only against *ordered sets*.</span></span> <span data-ttu-id="31718-127">La semántica para los conjuntos no ordenados o conjuntos múltiples no está definida.</span><span class="sxs-lookup"><span data-stu-id="31718-127">The semantics for unordered sets or multisets are undefined.</span></span>

> [!NOTE]
> <span data-ttu-id="31718-128"><xref:System.Linq.Enumerable.Take%2A> y <xref:System.Linq.Enumerable.Skip%2A> tienen ciertas limitaciones cuando se utilizan en consultas en SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="31718-128"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="31718-129">Para obtener más información, vea la entrada sobre cómo omitir y tomar excepciones en SQL Server 2000 "en [solución de problemas](troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="31718-129">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](troubleshooting.md).</span></span>

<span data-ttu-id="31718-130">Debido a las limitaciones de la ordenación en SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] intenta trasladar la ordenación del argumento de estos métodos al resultado del método.</span><span class="sxs-lookup"><span data-stu-id="31718-130">Because of limitations on ordering in SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tries to move the ordering of the argument of these methods to the result of the method.</span></span> <span data-ttu-id="31718-131">Por ejemplo, considere la siguiente consulta [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="31718-131">For example, consider the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query:</span></span>

[!code-csharp[DLinqSQOTranslation#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#1)]
[!code-vb[DLinqSQOTranslation#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#1)]

<span data-ttu-id="31718-132">El SQL generado para este código traslada la ordenación al final, como se observa a continuación:</span><span class="sxs-lookup"><span data-stu-id="31718-132">The generated SQL for this code moves the ordering to the end, as follows:</span></span>

```sql
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],
FROM [Customers] AS [t0]
WHERE (NOT (EXISTS(
    SELECT NULL AS [EMPTY]
    FROM (
        SELECT TOP 1 [t1].[CustomerID]
        FROM [Customers] AS [t1]
        WHERE [t1].[City] = @p0
        ORDER BY [t1].[CustomerID]
        ) AS [t2]
    WHERE [t0].[CustomerID] = [t2].[CustomerID]
    ))) AND ([t0].[City] = @p1)
ORDER BY [t0].[CustomerID]
```

<span data-ttu-id="31718-133">Parece obvio que toda la ordenación especificada debe ser coherente cuando se encadenan <xref:System.Linq.Enumerable.Take%2A> y <xref:System.Linq.Enumerable.Skip%2A>.</span><span class="sxs-lookup"><span data-stu-id="31718-133">It becomes obvious that all the specified ordering must be consistent when <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> are chained together.</span></span> <span data-ttu-id="31718-134">De lo contrario, los resultados no están definidos.</span><span class="sxs-lookup"><span data-stu-id="31718-134">Otherwise, the results are undefined.</span></span>

<span data-ttu-id="31718-135">Tanto <xref:System.Linq.Enumerable.Take%2A> como <xref:System.Linq.Enumerable.Skip%2A> están bien definidos para los argumentos integrales de constante no negativos basados en la especificación de operadores de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="31718-135">Both <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> are well-defined for non-negative, constant integral arguments based on the Standard Query Operator specification.</span></span>

### <a name="operators-with-no-translation"></a><span data-ttu-id="31718-136">Operadores sin conversión</span><span class="sxs-lookup"><span data-stu-id="31718-136">Operators with No Translation</span></span>

<span data-ttu-id="31718-137">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no convierte los métodos siguientes.</span><span class="sxs-lookup"><span data-stu-id="31718-137">The following methods are not translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="31718-138">La razón más común es la diferencia entre los conjuntos múltiples no ordenados y las secuencias.</span><span class="sxs-lookup"><span data-stu-id="31718-138">The most common reason is the difference between unordered multisets and sequences.</span></span>

|<span data-ttu-id="31718-139">Operadores</span><span class="sxs-lookup"><span data-stu-id="31718-139">Operators</span></span>|<span data-ttu-id="31718-140">Análisis razonado</span><span class="sxs-lookup"><span data-stu-id="31718-140">Rationale</span></span>|
|---------------|---------------|
|<span data-ttu-id="31718-141"><xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A></span><span class="sxs-lookup"><span data-stu-id="31718-141"><xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A></span></span>|<span data-ttu-id="31718-142">Las consultas SQL funcionan con conjuntos múltiples, no con secuencias.</span><span class="sxs-lookup"><span data-stu-id="31718-142">SQL queries operate on multisets, not on sequences.</span></span> <span data-ttu-id="31718-143">`ORDER BY` debe ser la última cláusula aplicada a los resultados.</span><span class="sxs-lookup"><span data-stu-id="31718-143">`ORDER BY` must be the last clause applied to the results.</span></span> <span data-ttu-id="31718-144">Por esta razón, no hay ninguna conversión general para estos dos métodos.</span><span class="sxs-lookup"><span data-stu-id="31718-144">For this reason, there is no general-purpose translation for these two methods.</span></span>|
|<xref:System.Linq.Enumerable.Reverse%2A>|<span data-ttu-id="31718-145">La conversión de este método es posible para un conjunto ordenado pero [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no la realiza actualmente.</span><span class="sxs-lookup"><span data-stu-id="31718-145">Translation of this method is possible for an ordered set but is not currently translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|
|<span data-ttu-id="31718-146"><xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="31718-146"><xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A></span></span>|<span data-ttu-id="31718-147">La conversión de estos métodos es posible para un conjunto ordenado pero [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no la realiza actualmente.</span><span class="sxs-lookup"><span data-stu-id="31718-147">Translation of these methods is possible for an ordered set but is not currently translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|
|<span data-ttu-id="31718-148"><xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="31718-148"><xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A></span></span>|<span data-ttu-id="31718-149">Las consultas SQL funcionan en conjuntos múltiples, no en secuencias indizables.</span><span class="sxs-lookup"><span data-stu-id="31718-149">SQL queries operate on multisets, not on indexable sequences.</span></span>|
|<span data-ttu-id="31718-150"><xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (sobrecarga con argumento predeterminado)</span><span class="sxs-lookup"><span data-stu-id="31718-150"><xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (overload with default arg)</span></span>|<span data-ttu-id="31718-151">En general, no se puede especificar un valor predeterminado para una tupla arbitraria.</span><span class="sxs-lookup"><span data-stu-id="31718-151">In general, a default value cannot be specified for an arbitrary tuple.</span></span> <span data-ttu-id="31718-152">Los valores nulos para las tuplas son posibles en algunos casos a través de combinaciones externas.</span><span class="sxs-lookup"><span data-stu-id="31718-152">Null values for tuples are possible in some cases through outer joins.</span></span>|

## <a name="expression-translation"></a><span data-ttu-id="31718-153">Conversión de expresiones</span><span class="sxs-lookup"><span data-stu-id="31718-153">Expression Translation</span></span>

### <a name="null-semantics"></a><span data-ttu-id="31718-154">Semántica de valores null</span><span class="sxs-lookup"><span data-stu-id="31718-154">Null semantics</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="31718-155">no impone las semántica de comparación de valores null en SQL.</span><span class="sxs-lookup"><span data-stu-id="31718-155">does not impose null comparison semantics on SQL.</span></span> <span data-ttu-id="31718-156">Los operadores de comparación se convierten sintácticamente en sus equivalentes SQL.</span><span class="sxs-lookup"><span data-stu-id="31718-156">Comparison operators are syntactically translated to their SQL equivalents.</span></span> <span data-ttu-id="31718-157">Por esta razón, la semántica refleja la semántica de SQL definida según la configuración del servidor o la conexión.</span><span class="sxs-lookup"><span data-stu-id="31718-157">For this reason, the semantics reflect SQL semantics that are defined by server or connection settings.</span></span> <span data-ttu-id="31718-158">Dos valores nulos se consideran distintos según la configuración predeterminada de SQL Server (aunque se puede cambiar la configuración para cambiar la semántica).</span><span class="sxs-lookup"><span data-stu-id="31718-158">For example, two null values are considered unequal under default SQL Server settings, but you can change the settings to change the semantics.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="31718-159">no tiene en cuenta la configuración del servidor cuando convierte las consultas.</span><span class="sxs-lookup"><span data-stu-id="31718-159">does not consider server settings when it translates queries.</span></span>

<span data-ttu-id="31718-160">Una comparación con el literal null se convierte a la versión de SQL correcta (`is null` o `is not null`).</span><span class="sxs-lookup"><span data-stu-id="31718-160">A comparison with the literal null is translated to the appropriate SQL version (`is null` or `is not null`).</span></span>

<span data-ttu-id="31718-161">SQL Server define el valor `null` en la intercalación.</span><span class="sxs-lookup"><span data-stu-id="31718-161">The value of `null` in collation is defined by SQL Server.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="31718-162">no cambia la intercalación.</span><span class="sxs-lookup"><span data-stu-id="31718-162">does not change the collation.</span></span>

### <a name="aggregates"></a><span data-ttu-id="31718-163">Agregados</span><span class="sxs-lookup"><span data-stu-id="31718-163">Aggregates</span></span>

<span data-ttu-id="31718-164">El método de agregado del operador de consulta estándar <xref:System.Linq.Enumerable.Sum%2A> se evalúa como cero para una secuencia vacía o para una secuencia que solo contiene valores nulos.</span><span class="sxs-lookup"><span data-stu-id="31718-164">The Standard Query Operator aggregate method <xref:System.Linq.Enumerable.Sum%2A> evaluates to zero for an empty sequence or for a sequence that contains only nulls.</span></span> <span data-ttu-id="31718-165">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , la semántica de SQL se deja sin cambios y se <xref:System.Linq.Enumerable.Sum%2A> evalúa como en `null` lugar de cero para una secuencia vacía o para una secuencia que solo contiene valores NULL.</span><span class="sxs-lookup"><span data-stu-id="31718-165">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the semantics of SQL are left unchanged, and <xref:System.Linq.Enumerable.Sum%2A> evaluates to `null` instead of zero for an empty sequence or for a sequence that contains only nulls.</span></span>

<span data-ttu-id="31718-166">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se aplican las restricciones de SQL para los agregados en los resultados intermedios.</span><span class="sxs-lookup"><span data-stu-id="31718-166">SQL limitations on intermediate results apply to aggregates in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="31718-167"><xref:System.Linq.Enumerable.Sum%2A> para cantidades enteras de 32 bits no se calcula utilizando los resultados de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="31718-167">The <xref:System.Linq.Enumerable.Sum%2A> of 32-bit integer quantities is not computed by using 64-bit results.</span></span> <span data-ttu-id="31718-168">Puede producirse un desbordamiento en la conversión de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] que realiza <xref:System.Linq.Enumerable.Sum%2A> aun cuando la implementación del operador de consulta estándar no produce un desbordamiento para la secuencia en memoria correspondiente.</span><span class="sxs-lookup"><span data-stu-id="31718-168">Overflow might occur for a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of <xref:System.Linq.Enumerable.Sum%2A>, even if the Standard Query Operator implementation does not cause an overflow for the corresponding in-memory sequence.</span></span>

<span data-ttu-id="31718-169">De igual forma, la conversión que realiza [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] de <xref:System.Linq.Enumerable.Average%2A> de valores enteros se calcula como `integer`, no como `double`.</span><span class="sxs-lookup"><span data-stu-id="31718-169">Likewise, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of <xref:System.Linq.Enumerable.Average%2A> of integer values is computed as an `integer`, not as a `double`.</span></span>

### <a name="entity-arguments"></a><span data-ttu-id="31718-170">Argumentos de entidad</span><span class="sxs-lookup"><span data-stu-id="31718-170">Entity Arguments</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="31718-171">permite usar tipos de entidad en los <xref:System.Linq.Enumerable.GroupBy%2A> métodos y <xref:System.Linq.Enumerable.OrderBy%2A> .</span><span class="sxs-lookup"><span data-stu-id="31718-171">enables entity types to be used in the <xref:System.Linq.Enumerable.GroupBy%2A> and <xref:System.Linq.Enumerable.OrderBy%2A> methods.</span></span> <span data-ttu-id="31718-172">En la conversión de estos operadores, el uso de un argumento de un tipo se considera equivalente a especificar todos los miembros de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="31718-172">In the translation of these operators, the use of an argument of a type is considered to be the equivalent to specifying all members of that type.</span></span> <span data-ttu-id="31718-173">Por ejemplo, el código siguiente es equivalente:</span><span class="sxs-lookup"><span data-stu-id="31718-173">For example, the following code is equivalent:</span></span>

[!code-csharp[DLinqSQOTranslation#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#2)]
[!code-vb[DLinqSQOTranslation#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#2)]

### <a name="equatable--comparable-arguments"></a><span data-ttu-id="31718-174">Argumentos equivalentes o comparables</span><span class="sxs-lookup"><span data-stu-id="31718-174">Equatable / Comparable Arguments</span></span>

<span data-ttu-id="31718-175">La igualdad de los argumentos se requiere en la implementación de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="31718-175">Equality of arguments is required in the implementation of the following methods:</span></span>

- <xref:System.Linq.Enumerable.Contains%2A>

- <xref:System.Linq.Enumerable.Skip%2A>

- <xref:System.Linq.Enumerable.Union%2A>

- <xref:System.Linq.Enumerable.Intersect%2A>

- <xref:System.Linq.Enumerable.Except%2A>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="31718-176">admite la igualdad y comparación para los argumentos *planos* , pero no para los argumentos que son o contienen secuencias.</span><span class="sxs-lookup"><span data-stu-id="31718-176">supports equality and comparison for *flat* arguments, but not for arguments that are or contain sequences.</span></span> <span data-ttu-id="31718-177">Un argumento plano es un tipo que asignarse a una fila de SQL.</span><span class="sxs-lookup"><span data-stu-id="31718-177">A flat argument is a type that can be mapped to a SQL row.</span></span> <span data-ttu-id="31718-178">Una proyección de uno o más tipos de entidad que se pueden determinar estáticamente que no contiene una secuencia se considera un argumento plano.</span><span class="sxs-lookup"><span data-stu-id="31718-178">A projection of one or more entity types that can be statically determined not to contain a sequence is considered a flat argument.</span></span>

<span data-ttu-id="31718-179">A continuación se muestran ejemplos de argumentos planos:</span><span class="sxs-lookup"><span data-stu-id="31718-179">The following are examples of flat arguments:</span></span>

[!code-csharp[DLinqSQOTranslation#3](~/samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#3)]
[!code-vb[DLinqSQOTranslation#3](~/samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#3)]

<span data-ttu-id="31718-180">A continuación se muestran ejemplos de argumentos no planos (jerárquicos):</span><span class="sxs-lookup"><span data-stu-id="31718-180">The following are examples of non-flat (hierarchical) arguments:</span></span>

[!code-csharp[DLinqSQOTranslation#4](~/samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#4)]
[!code-vb[DLinqSQOTranslation#4](~/samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#4)]

### <a name="visual-basic-function-translation"></a><span data-ttu-id="31718-181">Conversión de funciones de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31718-181">Visual Basic Function Translation</span></span>

<span data-ttu-id="31718-182">Las siguientes funciones del asistente que utiliza el compilador de Visual Basic se convierten a las funciones y operadores de SQL correspondientes:</span><span class="sxs-lookup"><span data-stu-id="31718-182">The following helper functions that are used by the Visual Basic compiler are translated to corresponding SQL operators and functions:</span></span>

- `CompareString`

- `DateTime.Compare`

- `Decimal.Compare`

- `IIf (in Microsoft.VisualBasic.Interaction)`

<span data-ttu-id="31718-183">Métodos de conversión:</span><span class="sxs-lookup"><span data-stu-id="31718-183">Conversion methods:</span></span>

|||||
|-|-|-|-|
|<span data-ttu-id="31718-184">ToBoolean</span><span class="sxs-lookup"><span data-stu-id="31718-184">ToBoolean</span></span>|<span data-ttu-id="31718-185">ToSByte</span><span class="sxs-lookup"><span data-stu-id="31718-185">ToSByte</span></span>|<span data-ttu-id="31718-186">ToByte</span><span class="sxs-lookup"><span data-stu-id="31718-186">ToByte</span></span>|<span data-ttu-id="31718-187">ToChar</span><span class="sxs-lookup"><span data-stu-id="31718-187">ToChar</span></span>|
|<span data-ttu-id="31718-188">ToCharArrayRankOne</span><span class="sxs-lookup"><span data-stu-id="31718-188">ToCharArrayRankOne</span></span>|<span data-ttu-id="31718-189">ToDate</span><span class="sxs-lookup"><span data-stu-id="31718-189">ToDate</span></span>|<span data-ttu-id="31718-190">ToDecimal</span><span class="sxs-lookup"><span data-stu-id="31718-190">ToDecimal</span></span>|<span data-ttu-id="31718-191">ToDouble</span><span class="sxs-lookup"><span data-stu-id="31718-191">ToDouble</span></span>|
|<span data-ttu-id="31718-192">ToInteger</span><span class="sxs-lookup"><span data-stu-id="31718-192">ToInteger</span></span>|<span data-ttu-id="31718-193">ToUInteger</span><span class="sxs-lookup"><span data-stu-id="31718-193">ToUInteger</span></span>|<span data-ttu-id="31718-194">ToLong</span><span class="sxs-lookup"><span data-stu-id="31718-194">ToLong</span></span>|<span data-ttu-id="31718-195">ToULong</span><span class="sxs-lookup"><span data-stu-id="31718-195">ToULong</span></span>|
|<span data-ttu-id="31718-196">ToShort</span><span class="sxs-lookup"><span data-stu-id="31718-196">ToShort</span></span>|<span data-ttu-id="31718-197">ToUShort</span><span class="sxs-lookup"><span data-stu-id="31718-197">ToUShort</span></span>|<span data-ttu-id="31718-198">ToSingle</span><span class="sxs-lookup"><span data-stu-id="31718-198">ToSingle</span></span>|<span data-ttu-id="31718-199">ToString</span><span class="sxs-lookup"><span data-stu-id="31718-199">ToString</span></span>|

## <a name="inheritance-support"></a><span data-ttu-id="31718-200">Compatibilidad de herencia</span><span class="sxs-lookup"><span data-stu-id="31718-200">Inheritance Support</span></span>

### <a name="inheritance-mapping-restrictions"></a><span data-ttu-id="31718-201">Restricciones de la asignación de herencia</span><span class="sxs-lookup"><span data-stu-id="31718-201">Inheritance Mapping Restrictions</span></span>

<span data-ttu-id="31718-202">Para obtener más información, vea [Cómo: asignar jerarquías de herencia](how-to-map-inheritance-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="31718-202">For more information, see [How to: Map Inheritance Hierarchies](how-to-map-inheritance-hierarchies.md).</span></span>

### <a name="inheritance-in-queries"></a><span data-ttu-id="31718-203">Herencia en consultas</span><span class="sxs-lookup"><span data-stu-id="31718-203">Inheritance in Queries</span></span>

<span data-ttu-id="31718-204">Las conversión de tipos de C# solo se admite en la proyección.</span><span class="sxs-lookup"><span data-stu-id="31718-204">C# casts are supported only in projection.</span></span> <span data-ttu-id="31718-205">Las conversiones de tipos que se utilizan en otra parte no se convierten y se omiten.</span><span class="sxs-lookup"><span data-stu-id="31718-205">Casts that are used elsewhere are not translated and are ignored.</span></span> <span data-ttu-id="31718-206">Además de los nombres de función de SQL, SQL realmente solo realiza la operación equivalente a <xref:System.Convert> de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="31718-206">Aside from SQL function names, SQL really only performs the equivalent of the common language runtime (CLR) <xref:System.Convert>.</span></span> <span data-ttu-id="31718-207">Es decir, SQL puede cambiar el valor de un tipo a otro.</span><span class="sxs-lookup"><span data-stu-id="31718-207">That is, SQL can change the value of one type to another.</span></span> <span data-ttu-id="31718-208">No hay ningún equivalente de conversión de tipos de CLR porque no existe el concepto de reinterpretar los mismos bits que los de otro tipo.</span><span class="sxs-lookup"><span data-stu-id="31718-208">There is no equivalent of CLR cast because there is no concept of reinterpreting the same bits as those of another type.</span></span> <span data-ttu-id="31718-209">Por esa razón una conversión de tipos de C# solo funciona localmente.</span><span class="sxs-lookup"><span data-stu-id="31718-209">That is why a C# cast works only locally.</span></span> <span data-ttu-id="31718-210">No es remota.</span><span class="sxs-lookup"><span data-stu-id="31718-210">It is not remoted.</span></span>

<span data-ttu-id="31718-211">Los operadores, `is` y `as`, y el método `GetType` no están limitados al operador `Select`.</span><span class="sxs-lookup"><span data-stu-id="31718-211">The operators, `is` and `as`, and the `GetType` method are not restricted to the `Select` operator.</span></span> <span data-ttu-id="31718-212">También se pueden utilizar en otros operadores de consulta.</span><span class="sxs-lookup"><span data-stu-id="31718-212">They can be used in other query operators also.</span></span>

## <a name="sql-server-2008-support"></a><span data-ttu-id="31718-213">Compatibilidad con SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="31718-213">SQL Server 2008 Support</span></span>

<span data-ttu-id="31718-214">A partir de .NET Framework 3.5 Service Pack 1, LINQ to SQL admite la asignación a tipos nuevos de fecha y hora incorporados con SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="31718-214">Starting with the .NET Framework 3.5 SP1, LINQ to SQL supports mapping to new date and time types introduced with SQL Server 2008.</span></span> <span data-ttu-id="31718-215">Pero, hay algunas limitaciones en los operadores de consulta de LINQ to SQL que puede usar al operar con valores asignados a estos tipos nuevos.</span><span class="sxs-lookup"><span data-stu-id="31718-215">But, there are some limitations to the LINQ to SQL query operators that you can use when operating against values mapped to these new types.</span></span>

### <a name="unsupported-query-operators"></a><span data-ttu-id="31718-216">Operadores de consulta no admitidos</span><span class="sxs-lookup"><span data-stu-id="31718-216">Unsupported Query Operators</span></span>

<span data-ttu-id="31718-217">Los operadores de consulta siguientes no se admiten en valores asignados a los nuevos tipos de fecha y hora de SQL Server: `DATETIME2`, `DATE`, `TIME` y `DATETIMEOFFSET`.</span><span class="sxs-lookup"><span data-stu-id="31718-217">The following query operators are not supported on values mapped to the new SQL Server date and time types: `DATETIME2`, `DATE`, `TIME`, and `DATETIMEOFFSET`.</span></span>

- `Aggregate`

- `Average`

- `LastOrDefault`

- `OfType`

- `Sum`

<span data-ttu-id="31718-218">Para obtener más información sobre la asignación a estos SQL Server tipos de fecha y hora, vea [asignación de tipos de SQL-CLR](sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="31718-218">For more information about mapping to these SQL Server date and time types, see [SQL-CLR Type Mapping](sql-clr-type-mapping.md).</span></span>

## <a name="sql-server-2005-support"></a><span data-ttu-id="31718-219">Compatibilidad con SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="31718-219">SQL Server 2005 Support</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="31718-220">no admite las características de SQL Server 2005 siguientes:</span><span class="sxs-lookup"><span data-stu-id="31718-220">does not support the following SQL Server 2005 features:</span></span>

- <span data-ttu-id="31718-221">Procedimientos almacenados escritos para SQL CLR.</span><span class="sxs-lookup"><span data-stu-id="31718-221">Stored procedures written for SQL CLR.</span></span>

- <span data-ttu-id="31718-222">Tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="31718-222">User-defined type.</span></span>

- <span data-ttu-id="31718-223">Características de consulta XML.</span><span class="sxs-lookup"><span data-stu-id="31718-223">XML query features.</span></span>

## <a name="sql-server-2000-support"></a><span data-ttu-id="31718-224">Compatibilidad con SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="31718-224">SQL Server 2000 Support</span></span>

<span data-ttu-id="31718-225">Las siguientes limitaciones SQL Server 2000 (en comparación con Microsoft SQL Server 2005) afectan al [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="31718-225">The following SQL Server 2000 limitations (compared to Microsoft SQL Server 2005) affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>

### <a name="cross-apply-and-outer-apply-operators"></a><span data-ttu-id="31718-226">Operadores Cross Apply y Outer Apply</span><span class="sxs-lookup"><span data-stu-id="31718-226">Cross Apply and Outer Apply Operators</span></span>

<span data-ttu-id="31718-227">Estos operadores no están disponibles en SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="31718-227">These operators are not available in SQL Server 2000.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="31718-228">intenta una serie de operaciones de reescritura para sustituirlos por las combinaciones adecuadas.</span><span class="sxs-lookup"><span data-stu-id="31718-228">tries a series of rewrites to replace them with appropriate joins.</span></span>

<span data-ttu-id="31718-229">`Cross Apply` y `Outer Apply` se generan para la navegación de relaciones.</span><span class="sxs-lookup"><span data-stu-id="31718-229">`Cross Apply` and `Outer Apply` are generated for relationship navigations.</span></span> <span data-ttu-id="31718-230">El conjunto de consultas para el que son posibles tales operaciones de reescritura no está bien definido.</span><span class="sxs-lookup"><span data-stu-id="31718-230">The set of queries for which such rewrites are possible is not well defined.</span></span> <span data-ttu-id="31718-231">Por esta razón, el conjunto mínimo de consultas que se admite para SQL Server 2000 es el conjunto que no implica la navegación por la relación.</span><span class="sxs-lookup"><span data-stu-id="31718-231">For this reason, the minimal set of queries that is supported for SQL Server 2000 is the set that does not involve relationship navigation.</span></span>

### <a name="text--ntext"></a><span data-ttu-id="31718-232">text / ntext</span><span class="sxs-lookup"><span data-stu-id="31718-232">text / ntext</span></span>

<span data-ttu-id="31718-233">No se `text`  /  `ntext` pueden usar tipos de datos en determinadas operaciones de consulta en `varchar(max)`  /  `nvarchar(max)` , que son compatibles con Microsoft SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="31718-233">Data types `text` / `ntext` cannot be used in certain query operations against `varchar(max)` / `nvarchar(max)`, which are supported by Microsoft SQL Server 2005.</span></span>

<span data-ttu-id="31718-234">Esta limitación no tiene ninguna resolución.</span><span class="sxs-lookup"><span data-stu-id="31718-234">No resolution is available for this limitation.</span></span> <span data-ttu-id="31718-235">Concretamente, no puede utilizar `Distinct()` en ningún resultado que contenga miembros que se asignen a columnas `text` o `ntext`.</span><span class="sxs-lookup"><span data-stu-id="31718-235">Specifically, you cannot use `Distinct()` on any result that contains members that are mapped to `text` or `ntext` columns.</span></span>

### <a name="behavior-triggered-by-nested-queries"></a><span data-ttu-id="31718-236">Comportamiento desencadenado por las consultas anidadas</span><span class="sxs-lookup"><span data-stu-id="31718-236">Behavior Triggered by Nested Queries</span></span>

<span data-ttu-id="31718-237">SQL Server 2000 (a SP4) el enlazador tiene algunas idiosincrasias que se desencadenan mediante consultas anidadas.</span><span class="sxs-lookup"><span data-stu-id="31718-237">SQL Server 2000 (through SP4) binder has some idiosyncrasies that are triggered by nested queries.</span></span> <span data-ttu-id="31718-238">El conjunto de consultas SQL que las desencadenan no está bien definido.</span><span class="sxs-lookup"><span data-stu-id="31718-238">The set of SQL queries that triggers these idiosyncrasies is not well defined.</span></span> <span data-ttu-id="31718-239">Por esta razón, no se puede definir el conjunto de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] consultas que pueden provocar excepciones SQL Server.</span><span class="sxs-lookup"><span data-stu-id="31718-239">For this reason, you cannot define the set of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries that might cause SQL Server exceptions.</span></span>

### <a name="skip-and-take-operators"></a><span data-ttu-id="31718-240">Operadores Skip y Take</span><span class="sxs-lookup"><span data-stu-id="31718-240">Skip and Take Operators</span></span>

<span data-ttu-id="31718-241"><xref:System.Linq.Enumerable.Take%2A> y <xref:System.Linq.Enumerable.Skip%2A> tienen ciertas limitaciones cuando se utilizan en consultas en SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="31718-241"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="31718-242">Para obtener más información, vea la entrada sobre cómo omitir y tomar excepciones en SQL Server 2000 "en [solución de problemas](troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="31718-242">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](troubleshooting.md).</span></span>

## <a name="object-materialization"></a><span data-ttu-id="31718-243">Materialización de objetos</span><span class="sxs-lookup"><span data-stu-id="31718-243">Object Materialization</span></span>

<span data-ttu-id="31718-244">La materialización crea objetos CLR a partir de las filas devueltas por una o más consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="31718-244">Materialization creates CLR objects from rows that are returned by one or more SQL queries.</span></span>

- <span data-ttu-id="31718-245">Las llamadas siguientes se *ejecutan localmente* como parte de la materialización:</span><span class="sxs-lookup"><span data-stu-id="31718-245">The following calls are *executed locally* as a part of materialization:</span></span>

  - <span data-ttu-id="31718-246">Constructores</span><span class="sxs-lookup"><span data-stu-id="31718-246">Constructors</span></span>

  - <span data-ttu-id="31718-247">Métodos `ToString` en las proyecciones</span><span class="sxs-lookup"><span data-stu-id="31718-247">`ToString` methods in projections</span></span>

  - <span data-ttu-id="31718-248">Conversiones de tipos en las proyecciones</span><span class="sxs-lookup"><span data-stu-id="31718-248">Type casts in projections</span></span>

- <span data-ttu-id="31718-249">Los métodos que siguen al <xref:System.Linq.Enumerable.AsEnumerable%2A> método se *ejecutan localmente*.</span><span class="sxs-lookup"><span data-stu-id="31718-249">Methods that follow the <xref:System.Linq.Enumerable.AsEnumerable%2A> method are *executed locally*.</span></span> <span data-ttu-id="31718-250">Este método no produce la ejecución inmediata.</span><span class="sxs-lookup"><span data-stu-id="31718-250">This method does not cause immediate execution.</span></span>

- <span data-ttu-id="31718-251">Puede utilizar `struct` como tipo de valor devuelto en el resultado de una consulta o como un miembro del tipo de resultado.</span><span class="sxs-lookup"><span data-stu-id="31718-251">You can use a `struct` as the return type of a query result or as a member of the result type.</span></span> <span data-ttu-id="31718-252">Las entidades deben ser clases.</span><span class="sxs-lookup"><span data-stu-id="31718-252">Entities are required to be classes.</span></span> <span data-ttu-id="31718-253">Los tipos anónimos se materializan como instancias de clase, pero los structs con nombre (no entidades) se pueden utilizar en la proyección.</span><span class="sxs-lookup"><span data-stu-id="31718-253">Anonymous types are materialized as class instances, but named structs (non-entities) can be used in projection.</span></span>

- <span data-ttu-id="31718-254">Un miembro del tipo de valor devuelto en el resultado de una consulta puede ser de tipo <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="31718-254">A member of the return type of a query result can be of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="31718-255">Se materializa como una colección local.</span><span class="sxs-lookup"><span data-stu-id="31718-255">It is materialized as a local collection.</span></span>

- <span data-ttu-id="31718-256">Los métodos siguientes provocan la *materialización inmediata* de la secuencia a la que se aplican los métodos:</span><span class="sxs-lookup"><span data-stu-id="31718-256">The following methods cause the *immediate materialization* of the sequence that the methods are applied to:</span></span>

  - <xref:System.Linq.Enumerable.ToList%2A>

  - <xref:System.Linq.Enumerable.ToDictionary%2A>

  - <xref:System.Linq.Enumerable.ToArray%2A>

## <a name="see-also"></a><span data-ttu-id="31718-257">Vea también</span><span class="sxs-lookup"><span data-stu-id="31718-257">See also</span></span>

- [<span data-ttu-id="31718-258">Referencia</span><span class="sxs-lookup"><span data-stu-id="31718-258">Reference</span></span>](reference.md)
- [<span data-ttu-id="31718-259">Devolver u omitir elementos de una secuencia</span><span class="sxs-lookup"><span data-stu-id="31718-259">Return Or Skip Elements in a Sequence</span></span>](return-or-skip-elements-in-a-sequence.md)
- [<span data-ttu-id="31718-260">Concatenar dos secuencias</span><span class="sxs-lookup"><span data-stu-id="31718-260">Concatenate Two Sequences</span></span>](concatenate-two-sequences.md)
- [<span data-ttu-id="31718-261">Devolver la diferencia de conjuntos entre dos secuencias</span><span class="sxs-lookup"><span data-stu-id="31718-261">Return the Set Difference Between Two Sequences</span></span>](return-the-set-difference-between-two-sequences.md)
- [<span data-ttu-id="31718-262">Devolver la intersección de conjuntos de dos secuencias</span><span class="sxs-lookup"><span data-stu-id="31718-262">Return the Set Intersection of Two Sequences</span></span>](return-the-set-intersection-of-two-sequences.md)
- [<span data-ttu-id="31718-263">Devolver la unión de conjuntos de dos secuencias</span><span class="sxs-lookup"><span data-stu-id="31718-263">Return the Set Union of Two Sequences</span></span>](return-the-set-union-of-two-sequences.md)
