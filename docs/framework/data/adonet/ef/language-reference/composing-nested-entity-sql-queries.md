---
title: Crear consultas anidadas de Entity SQL
ms.date: 03/30/2017
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
ms.openlocfilehash: 6b2fc9a32fc30d205b9c33257bf98781cfa07499
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150394"
---
# <a name="composing-nested-entity-sql-queries"></a><span data-ttu-id="8a494-102">Crear consultas anidadas de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8a494-102">Composing Nested Entity SQL Queries</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="8a494-103">es un lenguaje funcional enriquecido.</span><span class="sxs-lookup"><span data-stu-id="8a494-103">is a rich functional language.</span></span> <span data-ttu-id="8a494-104">El bloque [!INCLUDE[esql](../../../../../../includes/esql-md.md)] de construcción de es una expresión.</span><span class="sxs-lookup"><span data-stu-id="8a494-104">The building block of [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is an expression.</span></span> <span data-ttu-id="8a494-105">A diferencia [!INCLUDE[esql](../../../../../../includes/esql-md.md)] de SQL convencional, no [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se limita a un conjunto de resultados tabulares: admite la composición de expresiones complejas que pueden tener literales, parámetros o expresiones anidadas.</span><span class="sxs-lookup"><span data-stu-id="8a494-105">Unlike conventional SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not limited to a tabular result set: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports composing complex expressions that can have literals, parameters, or nested expressions.</span></span> <span data-ttu-id="8a494-106">Un valor de la expresión se puede parametrizar o componer con alguna otra expresión.</span><span class="sxs-lookup"><span data-stu-id="8a494-106">A value in the expression can be parameterized or composed of some other expression.</span></span>  
  
## <a name="nested-expressions"></a><span data-ttu-id="8a494-107">Expresiones anidadas</span><span class="sxs-lookup"><span data-stu-id="8a494-107">Nested Expressions</span></span>  
 <span data-ttu-id="8a494-108">Una expresión anidada se puede colocar en cualquier parte donde se acepte un valor del tipo que devuelve.</span><span class="sxs-lookup"><span data-stu-id="8a494-108">A nested expression can be placed anywhere a value of the type it returns is accepted.</span></span> <span data-ttu-id="8a494-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8a494-109">For example:</span></span>  
  
```sql  
-- Returns a hierarchical collection of three elements at top-level.
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 <span data-ttu-id="8a494-110">Una consulta anidada se puede colocar en una cláusula de proyección.</span><span class="sxs-lookup"><span data-stu-id="8a494-110">A nested query can be placed in a projection clause.</span></span> <span data-ttu-id="8a494-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8a494-111">For example:</span></span>  
  
```sql  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 <span data-ttu-id="8a494-112">En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], las consultas anidadas siempre deben ir entre paréntesis:</span><span class="sxs-lookup"><span data-stu-id="8a494-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], nested queries must always be enclosed in parentheses:</span></span>  
  
```sql  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 <span data-ttu-id="8a494-113">En el ejemplo siguiente se muestra [!INCLUDE[esql](../../../../../../includes/esql-md.md)]cómo anidar correctamente expresiones en: [Cómo: Ordenar la unión de dos consultas](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8a494-113">The following example demonstrates how to properly nest expressions in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [How to: Order the Union of Two Queries](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100)).</span></span>  
  
## <a name="nested-queries-in-projection"></a><span data-ttu-id="8a494-114">Consultas anidadas en proyección</span><span class="sxs-lookup"><span data-stu-id="8a494-114">Nested Queries in Projection</span></span>  
 <span data-ttu-id="8a494-115">Las consultas anidadas en la cláusula del proyecto se podrían traducir en consultas de producto cartesiano en el servidor.</span><span class="sxs-lookup"><span data-stu-id="8a494-115">Nested queries in the project clause might get translated into Cartesian product queries on the server.</span></span> <span data-ttu-id="8a494-116">En algunos servidores back-end, incluido SQL Server, esto puede hacer que la tabla TempDB obtenga muy grande, lo que puede afectar negativamente al rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="8a494-116">In some backend servers, including SQL Server, this can cause the TempDB table to get very large, which can adversely affect server performance.</span></span>  
  
 <span data-ttu-id="8a494-117">A continuación se muestra un ejemplo de dicha consulta:</span><span class="sxs-lookup"><span data-stu-id="8a494-117">The following is an example of such a query:</span></span>  
  
```sql  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="8a494-118">Ordenar las consultas anidadas</span><span class="sxs-lookup"><span data-stu-id="8a494-118">Ordering Nested Queries</span></span>  
 <span data-ttu-id="8a494-119">En el Entity Framework, una expresión anidada se puede colocar en cualquier parte de la consulta.</span><span class="sxs-lookup"><span data-stu-id="8a494-119">In the Entity Framework, a nested expression can be placed anywhere in the query.</span></span> <span data-ttu-id="8a494-120">Dado que Entity SQL permite gran flexibilidad al escribir las consultas, es posible escribir una consulta que contenga una ordenación de las consultas anidadas.</span><span class="sxs-lookup"><span data-stu-id="8a494-120">Because Entity SQL allows great flexibility in writing queries, it is possible to write a query that contains an ordering of nested queries.</span></span> <span data-ttu-id="8a494-121">Sin embargo, el orden de una consulta anidada no se conserva.</span><span class="sxs-lookup"><span data-stu-id="8a494-121">However, the order of a nested query is not preserved.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8a494-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a494-122">See also</span></span>

- [<span data-ttu-id="8a494-123">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8a494-123">Entity SQL Overview</span></span>](entity-sql-overview.md)
