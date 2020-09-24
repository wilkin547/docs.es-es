---
title: LIMIT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
ms.openlocfilehash: 81d135785e567d46a105adcafbf083f48cb4868e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161768"
---
# <a name="limit-entity-sql"></a><span data-ttu-id="c2e61-102">LIMIT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c2e61-102">LIMIT (Entity SQL)</span></span>

<span data-ttu-id="c2e61-103">La paginación física se puede realizar utilizando la subcláusula LIMIT en la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="c2e61-103">Physical paging can be performed by using LIMIT sub-clause in ORDER BY clause.</span></span> <span data-ttu-id="c2e61-104">LIMIT no se puede utilizar por separado de la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="c2e61-104">LIMIT can not be used separately from ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2e61-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2e61-105">Syntax</span></span>  
  
```sql  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c2e61-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c2e61-106">Arguments</span></span>  

 `n`  
 <span data-ttu-id="c2e61-107">Número de elementos que se seleccionarán.</span><span class="sxs-lookup"><span data-stu-id="c2e61-107">The number of items that will be selected.</span></span>  
  
 <span data-ttu-id="c2e61-108">Si en una cláusula ORDER BY hay una subcláusula de expresión LIMIT, la consulta se ordenará en función de la especificación de clasificación, y el número de filas resultante se limitará mediante la expresión LIMIT.</span><span class="sxs-lookup"><span data-stu-id="c2e61-108">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="c2e61-109">Por ejemplo, LIMIT 5 limitará el conjunto de resultados a 5 instancias o filas.</span><span class="sxs-lookup"><span data-stu-id="c2e61-109">For instance, LIMIT 5 will restrict the result set to 5 instances or rows.</span></span> <span data-ttu-id="c2e61-110">LIMIT es funcionalmente equivalente a TOP con la excepción de que LIMIT exige la presencia de la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="c2e61-110">LIMIT is functionally equivalent to TOP with the exception that LIMIT requires ORDER BY clause to be present.</span></span> <span data-ttu-id="c2e61-111">SKIP y LIMIT se pueden utilizar independientemente junto con la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="c2e61-111">SKIP and LIMIT can be used independently along with ORDER BY clause.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2e61-112">Una consulta de Entity SQL se considerará no válida si el modificador TOP y la subcláusula SKIP están presentes en la misma expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="c2e61-112">An Entity Sql query will be considered invalid if TOP modifier and SKIP sub-clause is present in the same query expression.</span></span> <span data-ttu-id="c2e61-113">La consulta se debe volver a escribir cambiando la expresión TOP a la expresión LIMIT.</span><span class="sxs-lookup"><span data-stu-id="c2e61-113">The query should be rewritten by changing TOP expression to LIMIT expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2e61-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2e61-114">Example</span></span>  

 <span data-ttu-id="c2e61-115">La consulta de Entity SQL siguiente usa el operador ORDER BY con LIMIT para especificar el criterio de ordenación utilizado en los objetos devueltos en una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="c2e61-115">The following Entity SQL query uses the ORDER BY operator with LIMIT to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="c2e61-116">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="c2e61-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c2e61-117">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c2e61-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="c2e61-118">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c2e61-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="c2e61-119">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="c2e61-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LIMIT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#limit)]  
  
## <a name="see-also"></a><span data-ttu-id="c2e61-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2e61-120">See also</span></span>

- [<span data-ttu-id="c2e61-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="c2e61-121">ORDER BY</span></span>](order-by-entity-sql.md)
- <span data-ttu-id="c2e61-122">[Cómo hojear los resultados de la consulta](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c2e61-122">[How to: Page Through Query Results](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="c2e61-123">Paginación</span><span class="sxs-lookup"><span data-stu-id="c2e61-123">Paging</span></span>](paging-entity-sql.md)
- [<span data-ttu-id="c2e61-124">TOP</span><span class="sxs-lookup"><span data-stu-id="c2e61-124">TOP</span></span>](top-entity-sql.md)
