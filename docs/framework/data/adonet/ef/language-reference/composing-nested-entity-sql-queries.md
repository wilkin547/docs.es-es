---
description: Más información acerca de cómo crear consultas de Entity SQL anidadas
title: Crear consultas anidadas de Entity SQL
ms.date: 03/30/2017
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
ms.openlocfilehash: 971625f0b1e82068192d4f8f74e2f1c55043d900
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724900"
---
# <a name="composing-nested-entity-sql-queries"></a><span data-ttu-id="5a0c6-103">Crear consultas anidadas de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5a0c6-103">Composing Nested Entity SQL Queries</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5a0c6-104">es un lenguaje funcional enriquecido.</span><span class="sxs-lookup"><span data-stu-id="5a0c6-104">is a rich functional language.</span></span> <span data-ttu-id="5a0c6-105">El bloque de creación de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] es una expresión.</span><span class="sxs-lookup"><span data-stu-id="5a0c6-105">The building block of [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is an expression.</span></span> <span data-ttu-id="5a0c6-106">A diferencia de SQL convencional, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no se limita a un conjunto de resultados tabular: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite expresiones complejas compuestas que pueden tener literales, parámetros o expresiones anidadas.</span><span class="sxs-lookup"><span data-stu-id="5a0c6-106">Unlike conventional SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not limited to a tabular result set: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports composing complex expressions that can have literals, parameters, or nested expressions.</span></span> <span data-ttu-id="5a0c6-107">Un valor de la expresión se puede parametrizar o componer con alguna otra expresión.</span><span class="sxs-lookup"><span data-stu-id="5a0c6-107">A value in the expression can be parameterized or composed of some other expression.</span></span>  
  
## <a name="nested-expressions"></a><span data-ttu-id="5a0c6-108">Expresiones anidadas</span><span class="sxs-lookup"><span data-stu-id="5a0c6-108">Nested Expressions</span></span>  

 <span data-ttu-id="5a0c6-109">Una expresión anidada se puede colocar en cualquier parte donde se acepte un valor del tipo que devuelve.</span><span class="sxs-lookup"><span data-stu-id="5a0c6-109">A nested expression can be placed anywhere a value of the type it returns is accepted.</span></span> <span data-ttu-id="5a0c6-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5a0c6-110">For example:</span></span>  
  
```sql  
-- Returns a hierarchical collection of three elements at top-level.
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 <span data-ttu-id="5a0c6-111">Una consulta anidada se puede colocar en una cláusula de proyección.</span><span class="sxs-lookup"><span data-stu-id="5a0c6-111">A nested query can be placed in a projection clause.</span></span> <span data-ttu-id="5a0c6-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5a0c6-112">For example:</span></span>  
  
```sql  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 <span data-ttu-id="5a0c6-113">En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], las consultas anidadas siempre deben ir entre paréntesis:</span><span class="sxs-lookup"><span data-stu-id="5a0c6-113">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], nested queries must always be enclosed in parentheses:</span></span>  
  
```sql  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 <span data-ttu-id="5a0c6-114">En el ejemplo siguiente se muestra cómo anidar correctamente [!INCLUDE[esql](../../../../../../includes/esql-md.md)] las expresiones en: [Cómo: ordenar la Unión de dos consultas](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="5a0c6-114">The following example demonstrates how to properly nest expressions in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [How to: Order the Union of Two Queries](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100)).</span></span>  
  
## <a name="nested-queries-in-projection"></a><span data-ttu-id="5a0c6-115">Consultas anidadas en proyección</span><span class="sxs-lookup"><span data-stu-id="5a0c6-115">Nested Queries in Projection</span></span>  

 <span data-ttu-id="5a0c6-116">Las consultas anidadas en la cláusula del proyecto se podrían traducir en consultas de producto cartesiano en el servidor.</span><span class="sxs-lookup"><span data-stu-id="5a0c6-116">Nested queries in the project clause might get translated into Cartesian product queries on the server.</span></span> <span data-ttu-id="5a0c6-117">En algunos servidores back-end, incluido SQL Server, esto puede hacer que la tabla TempDB sea muy grande, lo que puede afectar negativamente al rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="5a0c6-117">In some backend servers, including SQL Server, this can cause the TempDB table to get very large, which can adversely affect server performance.</span></span>  
  
 <span data-ttu-id="5a0c6-118">A continuación se muestra un ejemplo de dicha consulta:</span><span class="sxs-lookup"><span data-stu-id="5a0c6-118">The following is an example of such a query:</span></span>  
  
```sql  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="5a0c6-119">Ordenar las consultas anidadas</span><span class="sxs-lookup"><span data-stu-id="5a0c6-119">Ordering Nested Queries</span></span>  

 <span data-ttu-id="5a0c6-120">En el Entity Framework, una expresión anidada se puede colocar en cualquier parte de la consulta.</span><span class="sxs-lookup"><span data-stu-id="5a0c6-120">In the Entity Framework, a nested expression can be placed anywhere in the query.</span></span> <span data-ttu-id="5a0c6-121">Dado que Entity SQL permite gran flexibilidad al escribir las consultas, es posible escribir una consulta que contenga una ordenación de las consultas anidadas.</span><span class="sxs-lookup"><span data-stu-id="5a0c6-121">Because Entity SQL allows great flexibility in writing queries, it is possible to write a query that contains an ordering of nested queries.</span></span> <span data-ttu-id="5a0c6-122">Sin embargo, el orden de una consulta anidada no se conserva.</span><span class="sxs-lookup"><span data-stu-id="5a0c6-122">However, the order of a nested query is not preserved.</span></span>  
  
```sql  
-- The following query will order the results by last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```sql  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a0c6-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a0c6-123">See also</span></span>

- [<span data-ttu-id="5a0c6-124">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5a0c6-124">Entity SQL Overview</span></span>](entity-sql-overview.md)
