---
title: LIMIT (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c890bf6950f94c04350902276193f5a43239f63f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="limit-entity-sql"></a><span data-ttu-id="3cceb-102">LIMIT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3cceb-102">LIMIT (Entity SQL)</span></span>
<span data-ttu-id="3cceb-103">La paginación física se puede realizar utilizando la subcláusula LIMIT en la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="3cceb-103">Physical paging can be performed by using LIMIT sub-clause in ORDER BY clause.</span></span> <span data-ttu-id="3cceb-104">LIMIT no se puede utilizar por separado de la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="3cceb-104">LIMIT can not be used separately from ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cceb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cceb-105">Syntax</span></span>  
  
```  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="3cceb-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3cceb-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="3cceb-107">Número de elementos que se seleccionarán.</span><span class="sxs-lookup"><span data-stu-id="3cceb-107">The number of items that will be selected.</span></span>  
  
 <span data-ttu-id="3cceb-108">Si en una cláusula ORDER BY hay una subcláusula de expresión LIMIT, la consulta se ordenará en función de la especificación de clasificación, y el número de filas resultante se limitará mediante la expresión LIMIT.</span><span class="sxs-lookup"><span data-stu-id="3cceb-108">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="3cceb-109">Por ejemplo, LIMIT 5 limitará el conjunto de resultados a 5 instancias o filas.</span><span class="sxs-lookup"><span data-stu-id="3cceb-109">For instance, LIMIT 5 will restrict the result set to 5 instances or rows.</span></span> <span data-ttu-id="3cceb-110">LIMIT es funcionalmente equivalente a TOP con la excepción de que LIMIT exige la presencia de la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="3cceb-110">LIMIT is functionally equivalent to TOP with the exception that LIMIT requires ORDER BY clause to be present.</span></span> <span data-ttu-id="3cceb-111">SKIP y LIMIT se pueden utilizar independientemente junto con la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="3cceb-111">SKIP and LIMIT can be used independently along with ORDER BY clause.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3cceb-112">Una consulta de Entity SQL se considerará no válida si el modificador TOP y la subcláusula SKIP están presentes en la misma expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="3cceb-112">An Entity Sql query will be considered invalid if TOP modifier and SKIP sub-clause is present in the same query expression.</span></span> <span data-ttu-id="3cceb-113">La consulta se debe volver a escribir cambiando la expresión TOP a la expresión LIMIT.</span><span class="sxs-lookup"><span data-stu-id="3cceb-113">The query should be rewritten by changing TOP expression to LIMIT expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cceb-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3cceb-114">Example</span></span>  
 <span data-ttu-id="3cceb-115">La consulta de Entity SQL siguiente usa el operador ORDER BY con LIMIT para especificar el criterio de ordenación utilizado en los objetos devueltos en una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="3cceb-115">The following Entity SQL query uses the ORDER BY operator with LIMIT to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="3cceb-116">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="3cceb-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3cceb-117">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3cceb-117">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="3cceb-118">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3cceb-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="3cceb-119">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="3cceb-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a><span data-ttu-id="3cceb-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cceb-120">See Also</span></span>  
 [<span data-ttu-id="3cceb-121">ORDENAR POR</span><span class="sxs-lookup"><span data-stu-id="3cceb-121">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [<span data-ttu-id="3cceb-122">Cómo: resultados de la página a través de consulta</span><span class="sxs-lookup"><span data-stu-id="3cceb-122">How to: Page Through Query Results</span></span>](http://msdn.microsoft.com/en-us/ffc0f920-e7de-42e0-9b12-ef356421d030)  
 [<span data-ttu-id="3cceb-123">Paginación</span><span class="sxs-lookup"><span data-stu-id="3cceb-123">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
 [<span data-ttu-id="3cceb-124">ARRIBA</span><span class="sxs-lookup"><span data-stu-id="3cceb-124">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
