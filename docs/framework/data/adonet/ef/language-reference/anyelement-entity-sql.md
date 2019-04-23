---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: ff79417008b7807fbf206d4bcb65b4e5ea1cc576
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296139"
---
# <a name="anyelement-entity-sql"></a><span data-ttu-id="1965f-102">ANYELEMENT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1965f-102">ANYELEMENT (Entity SQL)</span></span>
<span data-ttu-id="1965f-103">Extrae un elemento de una colección de varios valores.</span><span class="sxs-lookup"><span data-stu-id="1965f-103">Extracts an element from a multivalued collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1965f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1965f-104">Syntax</span></span>  
  
```  
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="1965f-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1965f-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="1965f-106">Expresión de consulta válida que devuelve una colección de la que extraer un elemento.</span><span class="sxs-lookup"><span data-stu-id="1965f-106">Any valid query expression that returns a collection to extract an element from.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1965f-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1965f-107">Return Value</span></span>  
 <span data-ttu-id="1965f-108">Un único elemento de la colección o un elemento arbitrario si la colección tiene más de uno; si la colección está vacía, devuelve `null`.</span><span class="sxs-lookup"><span data-stu-id="1965f-108">A single element in the collection or an arbitrary element if the collection has more than one; if the collection is empty, returns `null`.</span></span> <span data-ttu-id="1965f-109">Si `collection` es una colección de tipo `Collection<T>`, a continuación, `ANYELEMENT(collection)` es una expresión válida que da como resultado una instancia de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="1965f-109">If `collection` is a collection of type `Collection<T>`, then `ANYELEMENT(collection)` is a valid expression that yields an instance of type `T`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1965f-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1965f-110">Remarks</span></span>  
 <span data-ttu-id="1965f-111">ANYELEMENT extrae un elemento arbitrario de una colección de varios valores.</span><span class="sxs-lookup"><span data-stu-id="1965f-111">ANYELEMENT extracts an arbitrary element from a multivalued collection.</span></span> <span data-ttu-id="1965f-112">Por ejemplo, a continuación se intenta extraer un elemento singleton del conjunto `Customers`.</span><span class="sxs-lookup"><span data-stu-id="1965f-112">For example, the following example attempts to extract a singleton element from the set `Customers`.</span></span>  
  
```  
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a><span data-ttu-id="1965f-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1965f-113">Example</span></span>  
 <span data-ttu-id="1965f-114">La siguiente consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] usa el operador ANYELEMENT para extraer un elemento de una colección de varios valores.</span><span class="sxs-lookup"><span data-stu-id="1965f-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ANYELEMENT operator to extract an element from a multivalued collection.</span></span> <span data-ttu-id="1965f-115">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="1965f-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1965f-116">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1965f-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="1965f-117">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="1965f-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="1965f-118">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="1965f-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a><span data-ttu-id="1965f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1965f-119">See also</span></span>

- [<span data-ttu-id="1965f-120">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1965f-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="1965f-121">Tipos estructurados que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="1965f-121">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
