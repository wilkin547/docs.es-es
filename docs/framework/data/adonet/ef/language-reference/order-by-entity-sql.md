---
description: 'Más información acerca de: ORDER BY (Entity SQL)'
title: ORDER BY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c0b61572-ecee-41eb-9d7f-74132ec8a26c
ms.openlocfilehash: 092850e864ae95d50b615839265041a7e32b39a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696326"
---
# <a name="order-by-entity-sql"></a><span data-ttu-id="27332-103">ORDER BY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="27332-103">ORDER BY (Entity SQL)</span></span>

<span data-ttu-id="27332-104">Especifica el criterio de ordenación utilizado en los objetos devueltos en una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="27332-104">Specifies the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27332-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27332-105">Syntax</span></span>  
  
```sql  
[ ORDER BY
   {  
      order_by_expression [SKIP n] [LIMIT n]  
      [ COLLATE collation_name ]  
      [ ASC | DESC ]  
   }  
   [ ,…n ]
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="27332-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="27332-106">Arguments</span></span>  

 `order_by_expression`  
 <span data-ttu-id="27332-107">Cualquier expresión de consulta válida que especifique una propiedad por la que se va a ordenar.</span><span class="sxs-lookup"><span data-stu-id="27332-107">Any valid query expression specifying a property on which to sort.</span></span> <span data-ttu-id="27332-108">Se pueden especificar varias expresiones de ordenación.</span><span class="sxs-lookup"><span data-stu-id="27332-108">Multiple sort expressions can be specified.</span></span> <span data-ttu-id="27332-109">La secuencia de las expresiones de ordenación de la cláusula ORDER BY define la organización del conjunto de resultados ordenado.</span><span class="sxs-lookup"><span data-stu-id="27332-109">The sequence of the sort expressions in the ORDER BY clause defines the organization of the sorted result set.</span></span>  
  
 <span data-ttu-id="27332-110">COLLATE {collation_name}</span><span class="sxs-lookup"><span data-stu-id="27332-110">COLLATE {collation_name}</span></span>  
 <span data-ttu-id="27332-111">Especifica que la operación ORDER BY se debe realizar de acuerdo con la intercalación especificada en `collation_name`.</span><span class="sxs-lookup"><span data-stu-id="27332-111">Specifies that the ORDER BY operation should be performed according to the collation specified in `collation_name`.</span></span> <span data-ttu-id="27332-112">COLLATE solo es aplicable para las expresiones de cadena.</span><span class="sxs-lookup"><span data-stu-id="27332-112">COLLATE is applicable only for string expressions.</span></span>  
  
 <span data-ttu-id="27332-113">ASC</span><span class="sxs-lookup"><span data-stu-id="27332-113">ASC</span></span>  
 <span data-ttu-id="27332-114">Especifica que los valores de la propiedad indicada se deben ordenar de forma ascendente, del valor más bajo al más alto.</span><span class="sxs-lookup"><span data-stu-id="27332-114">Specifies that the values in the specified property should be sorted in ascending order, from lowest value to highest value.</span></span> <span data-ttu-id="27332-115">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="27332-115">This is the default.</span></span>  
  
 <span data-ttu-id="27332-116">DESC</span><span class="sxs-lookup"><span data-stu-id="27332-116">DESC</span></span>  
 <span data-ttu-id="27332-117">Especifica que los valores de la propiedad indicada se deben ordenar de forma descendente, del valor más alto al más bajo.</span><span class="sxs-lookup"><span data-stu-id="27332-117">Specifies that the values in the specified property should be sorted in descending order, from highest value to lowest value.</span></span>  
  
 <span data-ttu-id="27332-118">LIMIT `n`</span><span class="sxs-lookup"><span data-stu-id="27332-118">LIMIT `n`</span></span>  
 <span data-ttu-id="27332-119">Solo se seleccionarán los `n` primeros elementos.</span><span class="sxs-lookup"><span data-stu-id="27332-119">Only the first `n` items will be selected.</span></span>  
  
 <span data-ttu-id="27332-120">SKIP `n`</span><span class="sxs-lookup"><span data-stu-id="27332-120">SKIP `n`</span></span>  
 <span data-ttu-id="27332-121">Omite los `n` primeros elementos.</span><span class="sxs-lookup"><span data-stu-id="27332-121">Skips the first `n` items.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27332-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="27332-122">Remarks</span></span>  

 <span data-ttu-id="27332-123">La cláusula ORDER BY se aplica lógicamente al resultado de la cláusula SELECT.</span><span class="sxs-lookup"><span data-stu-id="27332-123">The ORDER BY clause is logically applied to the result of the SELECT clause.</span></span> <span data-ttu-id="27332-124">La cláusula ORDER BY puede hacer referencia a los elementos de la lista de selección utilizando sus alias.</span><span class="sxs-lookup"><span data-stu-id="27332-124">The ORDER BY clause can reference items in the select list by using their aliases.</span></span> <span data-ttu-id="27332-125">La cláusula ORDER BY también puede hacer referencia a otras variables que estén actualmente en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="27332-125">The ORDER BY clause can also reference other variables that are currently in-scope.</span></span> <span data-ttu-id="27332-126">Sin embargo, si la cláusula SELECT se ha especificado con un modificador DISTINCT, la cláusula ORDER BY solo puede hacer referencia a los alias de la cláusula SELECT.</span><span class="sxs-lookup"><span data-stu-id="27332-126">However, if the SELECT clause has been specified with a DISTINCT modifier, the ORDER BY clause can only reference aliases from the SELECT clause.</span></span>  
  
 `SELECT c AS c1 FROM cs AS c ORDER BY c1.e1, c.e2`  
  
 <span data-ttu-id="27332-127">Cada expresión en la cláusula ORDER BY se debe evaluar como un tipo que se puede comparar a efectos de desigualdad ordenada (menor que o mayor que, etc.).</span><span class="sxs-lookup"><span data-stu-id="27332-127">Each expression in the ORDER BY clause must evaluate to some type that can be compared for ordered inequality (less than or greater than, and so on).</span></span> <span data-ttu-id="27332-128">Estos tipos son generalmente primitivos escalares, como números, cadenas y fechas.</span><span class="sxs-lookup"><span data-stu-id="27332-128">These types are generally scalar primitives such as numbers, strings, and dates.</span></span> <span data-ttu-id="27332-129">Los tipos de fila de tipos comparables también se pueden comparar según el orden.</span><span class="sxs-lookup"><span data-stu-id="27332-129">RowTypes of comparable types are also order comparable.</span></span>  
  
 <span data-ttu-id="27332-130">Si el código recorre en iteración un conjunto ordenado, que no sea para una proyección de nivel superior, no se garantiza que los resultados mantengan su orden.</span><span class="sxs-lookup"><span data-stu-id="27332-130">If your code iterates over an ordered set, other than for a top-level projection, the output is not guaranteed to have its order preserved.</span></span>  

<span data-ttu-id="27332-131">En el ejemplo siguiente, se garantiza que el orden se conserva:</span><span class="sxs-lookup"><span data-stu-id="27332-131">In the following sample, order is guaranteed to be preserved:</span></span>

```sql  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  

<span data-ttu-id="27332-132">En la consulta siguiente, se omite el orden de la consulta anidada:</span><span class="sxs-lookup"><span data-stu-id="27332-132">In the following query, ordering of the nested query is ignored:</span></span>  

```sql  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
 <span data-ttu-id="27332-133">Para tener una operación UNION, UNION ALL, EXCEPT o INTERSECT ordenada, utilice el modelo siguiente:</span><span class="sxs-lookup"><span data-stu-id="27332-133">To have an ordered UNION, UNION ALL, EXCEPT, or INTERSECT operation, use the following pattern:</span></span>  
  
```sql  
SELECT ...  
FROM ( UNION/EXCEPT/INTERSECT operation )  
ORDER BY ...  
```  
  
## <a name="restricted-keywords"></a><span data-ttu-id="27332-134">Palabras clave restringidas</span><span class="sxs-lookup"><span data-stu-id="27332-134">Restricted keywords</span></span>  

 <span data-ttu-id="27332-135">Las palabras clave siguientes debe ir entre comillas cuando se utilizan en una cláusula `ORDER BY` :</span><span class="sxs-lookup"><span data-stu-id="27332-135">The following keywords must be enclosed in quotation marks when used in an `ORDER BY` clause:</span></span>  
  
- <span data-ttu-id="27332-136">CROSS</span><span class="sxs-lookup"><span data-stu-id="27332-136">CROSS</span></span>  
  
- <span data-ttu-id="27332-137">FULL</span><span class="sxs-lookup"><span data-stu-id="27332-137">FULL</span></span>  
  
- <span data-ttu-id="27332-138">KEY</span><span class="sxs-lookup"><span data-stu-id="27332-138">KEY</span></span>  
  
- <span data-ttu-id="27332-139">LEFT</span><span class="sxs-lookup"><span data-stu-id="27332-139">LEFT</span></span>  
  
- <span data-ttu-id="27332-140">ORDER</span><span class="sxs-lookup"><span data-stu-id="27332-140">ORDER</span></span>  
  
- <span data-ttu-id="27332-141">OUTER</span><span class="sxs-lookup"><span data-stu-id="27332-141">OUTER</span></span>  
  
- <span data-ttu-id="27332-142">RIGHT</span><span class="sxs-lookup"><span data-stu-id="27332-142">RIGHT</span></span>  
  
- <span data-ttu-id="27332-143">ROW</span><span class="sxs-lookup"><span data-stu-id="27332-143">ROW</span></span>  
  
- <span data-ttu-id="27332-144">VALOR</span><span class="sxs-lookup"><span data-stu-id="27332-144">VALUE</span></span>  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="27332-145">Ordenar las consultas anidadas</span><span class="sxs-lookup"><span data-stu-id="27332-145">Ordering Nested Queries</span></span>  

 <span data-ttu-id="27332-146">En Entity Framework, una expresión anidada se puede colocar en cualquier parte de la consulta; el orden de una consulta anidada no se conserva.</span><span class="sxs-lookup"><span data-stu-id="27332-146">In the Entity Framework, a nested expression can be placed anywhere in the query; the order of a nested query is not preserved.</span></span>  

<span data-ttu-id="27332-147">La siguiente consulta ordenará los resultados por apellidos:</span><span class="sxs-lookup"><span data-stu-id="27332-147">The following query will order the results by the last name:</span></span>  

```sql  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  

<span data-ttu-id="27332-148">En la consulta siguiente, se omite el orden de la consulta anidada:</span><span class="sxs-lookup"><span data-stu-id="27332-148">In the following query, ordering of the nested query is ignored:</span></span>  

```sql  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="example"></a><span data-ttu-id="27332-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="27332-149">Example</span></span>  

 <span data-ttu-id="27332-150">La consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguiente usa el operador ORDER BY para especificar el criterio de ordenación utilizado en los objetos devueltos en una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="27332-150">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ORDER BY operator to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="27332-151">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="27332-151">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="27332-152">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="27332-152">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="27332-153">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="27332-153">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="27332-154">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="27332-154">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#ORDERBY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#orderby)]  
  
## <a name="see-also"></a><span data-ttu-id="27332-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="27332-155">See also</span></span>

- [<span data-ttu-id="27332-156">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="27332-156">Query Expressions</span></span>](query-expressions-entity-sql.md)
- [<span data-ttu-id="27332-157">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="27332-157">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="27332-158">IRÁ</span><span class="sxs-lookup"><span data-stu-id="27332-158">SKIP</span></span>](skip-entity-sql.md)
- [<span data-ttu-id="27332-159">ILIMITADO</span><span class="sxs-lookup"><span data-stu-id="27332-159">LIMIT</span></span>](limit-entity-sql.md)
- [<span data-ttu-id="27332-160">TOP</span><span class="sxs-lookup"><span data-stu-id="27332-160">TOP</span></span>](top-entity-sql.md)
