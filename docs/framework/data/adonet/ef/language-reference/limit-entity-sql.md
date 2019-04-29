---
title: LIMIT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
ms.openlocfilehash: b267e97860a2cb071b857224455f01b73115c72d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760680"
---
# <a name="limit-entity-sql"></a><span data-ttu-id="eba87-102">LIMIT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="eba87-102">LIMIT (Entity SQL)</span></span>
<span data-ttu-id="eba87-103">La paginación física se puede realizar utilizando la subcláusula LIMIT en la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="eba87-103">Physical paging can be performed by using LIMIT sub-clause in ORDER BY clause.</span></span> <span data-ttu-id="eba87-104">LIMIT no se puede utilizar por separado de la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="eba87-104">LIMIT can not be used separately from ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eba87-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eba87-105">Syntax</span></span>  
  
```  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="eba87-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="eba87-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="eba87-107">Número de elementos que se seleccionarán.</span><span class="sxs-lookup"><span data-stu-id="eba87-107">The number of items that will be selected.</span></span>  
  
 <span data-ttu-id="eba87-108">Si en una cláusula ORDER BY hay una subcláusula de expresión LIMIT, la consulta se ordenará en función de la especificación de clasificación, y el número de filas resultante se limitará mediante la expresión LIMIT.</span><span class="sxs-lookup"><span data-stu-id="eba87-108">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="eba87-109">Por ejemplo, LIMIT 5 limitará el conjunto de resultados a 5 instancias o filas.</span><span class="sxs-lookup"><span data-stu-id="eba87-109">For instance, LIMIT 5 will restrict the result set to 5 instances or rows.</span></span> <span data-ttu-id="eba87-110">LIMIT es funcionalmente equivalente a TOP con la excepción de que LIMIT exige la presencia de la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="eba87-110">LIMIT is functionally equivalent to TOP with the exception that LIMIT requires ORDER BY clause to be present.</span></span> <span data-ttu-id="eba87-111">SKIP y LIMIT se pueden utilizar independientemente junto con la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="eba87-111">SKIP and LIMIT can be used independently along with ORDER BY clause.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eba87-112">Una consulta de Entity SQL se considerará no válida si el modificador TOP y la subcláusula SKIP están presentes en la misma expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="eba87-112">An Entity Sql query will be considered invalid if TOP modifier and SKIP sub-clause is present in the same query expression.</span></span> <span data-ttu-id="eba87-113">La consulta se debe volver a escribir cambiando la expresión TOP a la expresión LIMIT.</span><span class="sxs-lookup"><span data-stu-id="eba87-113">The query should be rewritten by changing TOP expression to LIMIT expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eba87-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eba87-114">Example</span></span>  
 <span data-ttu-id="eba87-115">La consulta de Entity SQL siguiente usa el operador ORDER BY con LIMIT para especificar el criterio de ordenación utilizado en los objetos devueltos en una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="eba87-115">The following Entity SQL query uses the ORDER BY operator with LIMIT to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="eba87-116">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="eba87-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="eba87-117">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="eba87-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="eba87-118">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="eba87-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="eba87-119">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="eba87-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a><span data-ttu-id="eba87-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="eba87-120">See also</span></span>

- [<span data-ttu-id="eba87-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="eba87-121">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- <span data-ttu-id="eba87-122">[Cómo: Página de resultados de la consulta](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eba87-122">[How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="eba87-123">Paginación</span><span class="sxs-lookup"><span data-stu-id="eba87-123">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [<span data-ttu-id="eba87-124">TOP</span><span class="sxs-lookup"><span data-stu-id="eba87-124">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
