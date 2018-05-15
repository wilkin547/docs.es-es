---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: 11d1dd4b09ff07519f3435d313de72c5b9a3edf4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="anyelement-entity-sql"></a><span data-ttu-id="eac42-102">ANYELEMENT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="eac42-102">ANYELEMENT (Entity SQL)</span></span>
<span data-ttu-id="eac42-103">Extrae un elemento de una colección de varios valores.</span><span class="sxs-lookup"><span data-stu-id="eac42-103">Extracts an element from a multivalued collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eac42-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eac42-104">Syntax</span></span>  
  
```  
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="eac42-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="eac42-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="eac42-106">Expresión de consulta válida que devuelve una colección de la que extraer un elemento.</span><span class="sxs-lookup"><span data-stu-id="eac42-106">Any valid query expression that returns a collection to extract an element from.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eac42-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="eac42-107">Return Value</span></span>  
 <span data-ttu-id="eac42-108">Un único elemento de la colección o un elemento arbitrario si la colección tiene más de uno; si la colección está vacía, devuelve `null`.</span><span class="sxs-lookup"><span data-stu-id="eac42-108">A single element in the collection or an arbitrary element if the collection has more than one; if the collection is empty, returns `null`.</span></span> <span data-ttu-id="eac42-109">Si `collection` es una colección de tipo `Collection<T>`, a continuación, `ANYELEMENT(collection)` es una expresión válida que produzca una instancia de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="eac42-109">If `collection` is a collection of type `Collection<T>`, then `ANYELEMENT(collection)` is a valid expression that yields an instance of type `T`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eac42-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eac42-110">Remarks</span></span>  
 <span data-ttu-id="eac42-111">ANYELEMENT extrae un elemento arbitrario de una colección de varios valores.</span><span class="sxs-lookup"><span data-stu-id="eac42-111">ANYELEMENT extracts an arbitrary element from a multivalued collection.</span></span> <span data-ttu-id="eac42-112">Por ejemplo, a continuación se intenta extraer un elemento singleton del conjunto `Customers`.</span><span class="sxs-lookup"><span data-stu-id="eac42-112">For example, the following example attempts to extract a singleton element from the set `Customers`.</span></span>  
  
```  
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a><span data-ttu-id="eac42-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eac42-113">Example</span></span>  
 <span data-ttu-id="eac42-114">La siguiente consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] usa el operador ANYELEMENT para extraer un elemento de una colección de varios valores.</span><span class="sxs-lookup"><span data-stu-id="eac42-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ANYELEMENT operator to extract an element from a multivalued collection.</span></span> <span data-ttu-id="eac42-115">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="eac42-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="eac42-116">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="eac42-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="eac42-117">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="eac42-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="eac42-118">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="eac42-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a><span data-ttu-id="eac42-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="eac42-119">See Also</span></span>  
 [<span data-ttu-id="eac42-120">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="eac42-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="eac42-121">Tipos estructurados que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="eac42-121">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
