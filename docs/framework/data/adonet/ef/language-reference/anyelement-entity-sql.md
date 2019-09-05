---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: 4eea3d43ef6ae9ea91432ea277326526e5e91fbc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251326"
---
# <a name="anyelement-entity-sql"></a><span data-ttu-id="ad08a-102">ANYELEMENT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ad08a-102">ANYELEMENT (Entity SQL)</span></span>
<span data-ttu-id="ad08a-103">Extrae un elemento de una colección de varios valores.</span><span class="sxs-lookup"><span data-stu-id="ad08a-103">Extracts an element from a multivalued collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad08a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad08a-104">Syntax</span></span>  
  
```  
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="ad08a-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ad08a-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ad08a-106">Expresión de consulta válida que devuelve una colección de la que extraer un elemento.</span><span class="sxs-lookup"><span data-stu-id="ad08a-106">Any valid query expression that returns a collection to extract an element from.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad08a-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ad08a-107">Return Value</span></span>  
 <span data-ttu-id="ad08a-108">Un único elemento de la colección o un elemento arbitrario si la colección tiene más de uno; si la colección está vacía, devuelve `null`.</span><span class="sxs-lookup"><span data-stu-id="ad08a-108">A single element in the collection or an arbitrary element if the collection has more than one; if the collection is empty, returns `null`.</span></span> <span data-ttu-id="ad08a-109">Si `collection` es una colección de tipo `Collection<T>`, entonces `ANYELEMENT(collection)` es una expresión válida que da como resultado una instancia de `T`tipo.</span><span class="sxs-lookup"><span data-stu-id="ad08a-109">If `collection` is a collection of type `Collection<T>`, then `ANYELEMENT(collection)` is a valid expression that yields an instance of type `T`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad08a-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ad08a-110">Remarks</span></span>  
 <span data-ttu-id="ad08a-111">ANYELEMENT extrae un elemento arbitrario de una colección de varios valores.</span><span class="sxs-lookup"><span data-stu-id="ad08a-111">ANYELEMENT extracts an arbitrary element from a multivalued collection.</span></span> <span data-ttu-id="ad08a-112">Por ejemplo, a continuación se intenta extraer un elemento singleton del conjunto `Customers`.</span><span class="sxs-lookup"><span data-stu-id="ad08a-112">For example, the following example attempts to extract a singleton element from the set `Customers`.</span></span>  
  
```  
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a><span data-ttu-id="ad08a-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad08a-113">Example</span></span>  
 <span data-ttu-id="ad08a-114">La siguiente consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] usa el operador ANYELEMENT para extraer un elemento de una colección de varios valores.</span><span class="sxs-lookup"><span data-stu-id="ad08a-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ANYELEMENT operator to extract an element from a multivalued collection.</span></span> <span data-ttu-id="ad08a-115">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="ad08a-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ad08a-116">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ad08a-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ad08a-117">Siga el procedimiento descrito [en cómo: Ejecute una consulta que devuelva resultados](../how-to-execute-a-query-that-returns-structuraltype-results.md)de StructuralType.</span><span class="sxs-lookup"><span data-stu-id="ad08a-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ad08a-118">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ad08a-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a><span data-ttu-id="ad08a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad08a-119">See also</span></span>

- [<span data-ttu-id="ad08a-120">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ad08a-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="ad08a-121">Tipos estructurados que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="ad08a-121">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
