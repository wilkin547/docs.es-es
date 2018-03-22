---
title: ORDER BY (Entity SQL)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0b61572-ecee-41eb-9d7f-74132ec8a26c
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 4321c5fd3f173b209d99e096ec0ebf8788437c3d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="order-by-entity-sql"></a><span data-ttu-id="067d4-102">ORDER BY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="067d4-102">ORDER BY (Entity SQL)</span></span>
<span data-ttu-id="067d4-103">Especifica el criterio de ordenación utilizado en los objetos devueltos en una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="067d4-103">Specifies the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="067d4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="067d4-104">Syntax</span></span>  
  
```  
[ ORDER BY   
   {  
      order_by_expression [SKIP n] [LIMIT n]  
      [ COLLATE collation_name ]  
      [ ASC | DESC ]  
   }  
   [ ,…n ]   
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="067d4-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="067d4-105">Arguments</span></span>  
 `order_by_expression`  
 <span data-ttu-id="067d4-106">Cualquier expresión de consulta válida que especifique una propiedad por la que se va a ordenar.</span><span class="sxs-lookup"><span data-stu-id="067d4-106">Any valid query expression specifying a property on which to sort.</span></span> <span data-ttu-id="067d4-107">Se pueden especificar varias expresiones de ordenación.</span><span class="sxs-lookup"><span data-stu-id="067d4-107">Multiple sort expressions can be specified.</span></span> <span data-ttu-id="067d4-108">La secuencia de las expresiones de ordenación de la cláusula ORDER BY define la organización del conjunto de resultados ordenado.</span><span class="sxs-lookup"><span data-stu-id="067d4-108">The sequence of the sort expressions in the ORDER BY clause defines the organization of the sorted result set.</span></span>  
  
 <span data-ttu-id="067d4-109">COLLATE {collation_name}</span><span class="sxs-lookup"><span data-stu-id="067d4-109">COLLATE {collation_name}</span></span>  
 <span data-ttu-id="067d4-110">Especifica que la operación ORDER BY se debe realizar de acuerdo con la intercalación especificada en `collation_name`.</span><span class="sxs-lookup"><span data-stu-id="067d4-110">Specifies that the ORDER BY operation should be performed according to the collation specified in `collation_name`.</span></span> <span data-ttu-id="067d4-111">COLLATE solo es aplicable para las expresiones de cadena.</span><span class="sxs-lookup"><span data-stu-id="067d4-111">COLLATE is applicable only for string expressions.</span></span>  
  
 <span data-ttu-id="067d4-112">ASC</span><span class="sxs-lookup"><span data-stu-id="067d4-112">ASC</span></span>  
 <span data-ttu-id="067d4-113">Especifica que los valores de la propiedad indicada se deben ordenar de forma ascendente, del valor más bajo al más alto.</span><span class="sxs-lookup"><span data-stu-id="067d4-113">Specifies that the values in the specified property should be sorted in ascending order, from lowest value to highest value.</span></span> <span data-ttu-id="067d4-114">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="067d4-114">This is the default.</span></span>  
  
 <span data-ttu-id="067d4-115">DESC</span><span class="sxs-lookup"><span data-stu-id="067d4-115">DESC</span></span>  
 <span data-ttu-id="067d4-116">Especifica que los valores de la propiedad indicada se deben ordenar de forma descendente, del valor más alto al más bajo.</span><span class="sxs-lookup"><span data-stu-id="067d4-116">Specifies that the values in the specified property should be sorted in descending order, from highest value to lowest value.</span></span>  
  
 <span data-ttu-id="067d4-117">LIMIT `n`</span><span class="sxs-lookup"><span data-stu-id="067d4-117">LIMIT `n`</span></span>  
 <span data-ttu-id="067d4-118">Solo se seleccionarán los `n` primeros elementos.</span><span class="sxs-lookup"><span data-stu-id="067d4-118">Only the first `n` items will be selected.</span></span>  
  
 <span data-ttu-id="067d4-119">SKIP `n`</span><span class="sxs-lookup"><span data-stu-id="067d4-119">SKIP `n`</span></span>  
 <span data-ttu-id="067d4-120">Omite los `n` primeros elementos.</span><span class="sxs-lookup"><span data-stu-id="067d4-120">Skips the first `n` items.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="067d4-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="067d4-121">Remarks</span></span>  
 <span data-ttu-id="067d4-122">La cláusula ORDER BY se aplica lógicamente al resultado de la cláusula SELECT.</span><span class="sxs-lookup"><span data-stu-id="067d4-122">The ORDER BY clause is logically applied to the result of the SELECT clause.</span></span> <span data-ttu-id="067d4-123">La cláusula ORDER BY puede hacer referencia a los elementos de la lista de selección utilizando sus alias.</span><span class="sxs-lookup"><span data-stu-id="067d4-123">The ORDER BY clause can reference items in the select list by using their aliases.</span></span> <span data-ttu-id="067d4-124">La cláusula ORDER BY también puede hacer referencia a otras variables que estén actualmente en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="067d4-124">The ORDER BY clause can also reference other variables that are currently in-scope.</span></span> <span data-ttu-id="067d4-125">Sin embargo, si la cláusula SELECT se ha especificado con un modificador DISTINCT, la cláusula ORDER BY solo puede hacer referencia a los alias de la cláusula SELECT.</span><span class="sxs-lookup"><span data-stu-id="067d4-125">However, if the SELECT clause has been specified with a DISTINCT modifier, the ORDER BY clause can only reference aliases from the SELECT clause.</span></span>  
  
 `SELECT c AS c1 FROM cs AS c ORDER BY c1.e1, c.e2`  
  
 <span data-ttu-id="067d4-126">Cada expresión en la cláusula ORDER BY se debe evaluar como un tipo que se puede comparar a efectos de desigualdad ordenada (menor que o mayor que, etc.).</span><span class="sxs-lookup"><span data-stu-id="067d4-126">Each expression in the ORDER BY clause must evaluate to some type that can be compared for ordered inequality (less than or greater than, and so on).</span></span> <span data-ttu-id="067d4-127">Estos tipos son generalmente primitivos escalares, como números, cadenas y fechas.</span><span class="sxs-lookup"><span data-stu-id="067d4-127">These types are generally scalar primitives such as numbers, strings, and dates.</span></span> <span data-ttu-id="067d4-128">Los tipos de fila de tipos comparables también se pueden comparar según el orden.</span><span class="sxs-lookup"><span data-stu-id="067d4-128">RowTypes of comparable types are also order comparable.</span></span>  
  
 <span data-ttu-id="067d4-129">Si el código recorre en iteración un conjunto ordenado, que no sea para una proyección de nivel superior, no se garantiza que los resultados mantengan su orden.</span><span class="sxs-lookup"><span data-stu-id="067d4-129">If your code iterates over an ordered set, other than for a top-level projection, the output is not guaranteed to have its order preserved.</span></span>  
  
```  
-- In the following sample, order is guaranteed to be preserved:  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
 <span data-ttu-id="067d4-130">Para tener una operación UNION, UNION ALL, EXCEPT o INTERSECT ordenada, utilice el modelo siguiente:</span><span class="sxs-lookup"><span data-stu-id="067d4-130">To have an ordered UNION, UNION ALL, EXCEPT, or INTERSECT operation, use the following pattern:</span></span>  
  
```  
SELECT ...  
FROM ( UNION/EXCEPT/INTERSECT operation )  
ORDER BY ...  
```  
  
## <a name="restricted-keywords"></a><span data-ttu-id="067d4-131">Palabras clave restringidas</span><span class="sxs-lookup"><span data-stu-id="067d4-131">Restricted keywords</span></span>  
 <span data-ttu-id="067d4-132">Las palabras clave siguientes debe ir entre comillas cuando se utilizan en una cláusula `ORDER BY` :</span><span class="sxs-lookup"><span data-stu-id="067d4-132">The following keywords must be enclosed in quotation marks when used in an `ORDER BY` clause:</span></span>  
  
-   <span data-ttu-id="067d4-133">CROSS</span><span class="sxs-lookup"><span data-stu-id="067d4-133">CROSS</span></span>  
  
-   <span data-ttu-id="067d4-134">FULL</span><span class="sxs-lookup"><span data-stu-id="067d4-134">FULL</span></span>  
  
-   <span data-ttu-id="067d4-135">KEY</span><span class="sxs-lookup"><span data-stu-id="067d4-135">KEY</span></span>  
  
-   <span data-ttu-id="067d4-136">IZQUIERDA</span><span class="sxs-lookup"><span data-stu-id="067d4-136">LEFT</span></span>  
  
-   <span data-ttu-id="067d4-137">ORDER</span><span class="sxs-lookup"><span data-stu-id="067d4-137">ORDER</span></span>  
  
-   <span data-ttu-id="067d4-138">OUTER</span><span class="sxs-lookup"><span data-stu-id="067d4-138">OUTER</span></span>  
  
-   <span data-ttu-id="067d4-139">DERECHA</span><span class="sxs-lookup"><span data-stu-id="067d4-139">RIGHT</span></span>  
  
-   <span data-ttu-id="067d4-140">ROW</span><span class="sxs-lookup"><span data-stu-id="067d4-140">ROW</span></span>  
  
-   <span data-ttu-id="067d4-141">VALUE</span><span class="sxs-lookup"><span data-stu-id="067d4-141">VALUE</span></span>  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="067d4-142">Ordenar las consultas anidadas</span><span class="sxs-lookup"><span data-stu-id="067d4-142">Ordering Nested Queries</span></span>  
 <span data-ttu-id="067d4-143">En Entity Framework, una expresión anidada se puede colocar en cualquier parte de la consulta; el orden de una consulta anidada no se conserva.</span><span class="sxs-lookup"><span data-stu-id="067d4-143">In the Entity Framework, a nested expression can be placed anywhere in the query; the order of a nested query is not preserved.</span></span>  
  
```  
-- The following query will order the results by the last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="example"></a><span data-ttu-id="067d4-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="067d4-144">Example</span></span>  
 <span data-ttu-id="067d4-145">La consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguiente usa el operador ORDER BY para especificar el criterio de ordenación utilizado en los objetos devueltos en una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="067d4-145">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ORDER BY operator to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="067d4-146">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="067d4-146">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="067d4-147">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="067d4-147">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="067d4-148">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="067d4-148">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="067d4-149">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="067d4-149">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ORDERBY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#orderby)]  
  
## <a name="see-also"></a><span data-ttu-id="067d4-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="067d4-150">See Also</span></span>  
 [<span data-ttu-id="067d4-151">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="067d4-151">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
 [<span data-ttu-id="067d4-152">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="067d4-152">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="067d4-153">SKIP</span><span class="sxs-lookup"><span data-stu-id="067d4-153">SKIP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
 [<span data-ttu-id="067d4-154">LIMIT</span><span class="sxs-lookup"><span data-stu-id="067d4-154">LIMIT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
 [<span data-ttu-id="067d4-155">TOP</span><span class="sxs-lookup"><span data-stu-id="067d4-155">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
