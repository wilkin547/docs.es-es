---
title: Crear consultas anidadas de Entity SQL
ms.date: 03/30/2017
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
ms.openlocfilehash: 92e3153350787ef75c48ee52f1b6c68e09e15b4b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760861"
---
# <a name="composing-nested-entity-sql-queries"></a><span data-ttu-id="5356a-102">Crear consultas anidadas de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5356a-102">Composing Nested Entity SQL Queries</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="5356a-103"> es un lenguaje funcional enriquecido.</span><span class="sxs-lookup"><span data-stu-id="5356a-103"> is a rich functional language.</span></span> <span data-ttu-id="5356a-104">El bloque de creación de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] es una expresión.</span><span class="sxs-lookup"><span data-stu-id="5356a-104">The building block of [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is an expression.</span></span> <span data-ttu-id="5356a-105">A diferencia del SQL convencional, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no se limita a un conjunto de resultados tabular: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] permite crear expresiones complejas que pueden tener literales, parámetros o expresiones anidadas.</span><span class="sxs-lookup"><span data-stu-id="5356a-105">Unlike conventional SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not limited to a tabular result set: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports composing complex expressions that can have literals, parameters, or nested expressions.</span></span> <span data-ttu-id="5356a-106">Un valor de la expresión se puede parametrizar o formado por alguna otra expresión.</span><span class="sxs-lookup"><span data-stu-id="5356a-106">A value in the expression can be parameterized or composed of some other expression.</span></span>  
  
## <a name="nested-expressions"></a><span data-ttu-id="5356a-107">Expresiones anidadas</span><span class="sxs-lookup"><span data-stu-id="5356a-107">Nested Expressions</span></span>  
 <span data-ttu-id="5356a-108">Una expresión anidada se puede colocar en cualquier parte donde se acepte un valor del tipo que devuelve.</span><span class="sxs-lookup"><span data-stu-id="5356a-108">A nested expression can be placed anywhere a value of the type it returns is accepted.</span></span> <span data-ttu-id="5356a-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5356a-109">For example:</span></span>  
  
```  
-- Returns a hierarchical collection of three elements at top-level.   
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 <span data-ttu-id="5356a-110">Una consulta anidada se puede colocar en una cláusula de proyección.</span><span class="sxs-lookup"><span data-stu-id="5356a-110">A nested query can be placed in a projection clause.</span></span> <span data-ttu-id="5356a-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5356a-111">For example:</span></span>  
  
```  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)   
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)   
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 <span data-ttu-id="5356a-112">En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], las consultas anidadas siempre deben ir entre paréntesis:</span><span class="sxs-lookup"><span data-stu-id="5356a-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], nested queries must always be enclosed in parentheses:</span></span>  
  
```  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 <span data-ttu-id="5356a-113">En el ejemplo siguiente se muestra cómo anidar apropiadamente las expresiones en [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [Cómo: ordenar la unión de dos consultas](http://msdn.microsoft.com/library/853c583a-eaba-4400-830d-be974e735313).</span><span class="sxs-lookup"><span data-stu-id="5356a-113">The following example demonstrates how to properly nest expressions in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [How to: Order the Union of Two Queries](http://msdn.microsoft.com/library/853c583a-eaba-4400-830d-be974e735313).</span></span>  
  
## <a name="nested-queries-in-projection"></a><span data-ttu-id="5356a-114">Consultas anidadas en proyección</span><span class="sxs-lookup"><span data-stu-id="5356a-114">Nested Queries in Projection</span></span>  
 <span data-ttu-id="5356a-115">Las consultas anidadas en la cláusula del proyecto se podrían traducir en consultas de producto cartesiano en el servidor.</span><span class="sxs-lookup"><span data-stu-id="5356a-115">Nested queries in the project clause might get translated into Cartesian product queries on the server.</span></span> <span data-ttu-id="5356a-116">Esto puede hacer que la tabla TempDB aumente, lo que puede afectar adversamente al rendimiento del servidor en algunos servidores de servicios backend, incluido SLQ Server.</span><span class="sxs-lookup"><span data-stu-id="5356a-116">In some backend servers, including SLQ Server, this can cause the TempDB table to get very large, which can adversely affect server performance.</span></span>  
  
 <span data-ttu-id="5356a-117">A continuación se muestra un ejemplo de dicha consulta:</span><span class="sxs-lookup"><span data-stu-id="5356a-117">The following is an example of such a query:</span></span>  
  
```  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="5356a-118">Ordenar las consultas anidadas</span><span class="sxs-lookup"><span data-stu-id="5356a-118">Ordering Nested Queries</span></span>  
 <span data-ttu-id="5356a-119">En el Entity Framework, una expresión anidada se puede colocar en cualquier parte de la consulta.</span><span class="sxs-lookup"><span data-stu-id="5356a-119">In the Entity Framework, a nested expression can be placed anywhere in the query.</span></span> <span data-ttu-id="5356a-120">Dado que Entity SQL permite gran flexibilidad al escribir las consultas, es posible escribir una consulta que contenga una ordenación de las consultas anidadas.</span><span class="sxs-lookup"><span data-stu-id="5356a-120">Because Entity SQL allows great flexibility in writing queries, it is possible to write a query that contains an ordering of nested queries.</span></span> <span data-ttu-id="5356a-121">Sin embargo, el orden de una consulta anidada no se conserva.</span><span class="sxs-lookup"><span data-stu-id="5356a-121">However, the order of a nested query is not preserved.</span></span>  
  
```  
-- The following query will order the results by last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="see-also"></a><span data-ttu-id="5356a-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5356a-122">See Also</span></span>  
 [<span data-ttu-id="5356a-123">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5356a-123">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
