---
description: 'Más información acerca de: ANYELEMENT (Entity SQL)'
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: 3330c1b0bed69084bc83c5a689762ff529539d54
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697158"
---
# <a name="anyelement-entity-sql"></a><span data-ttu-id="434ab-103">ANYELEMENT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="434ab-103">ANYELEMENT (Entity SQL)</span></span>

<span data-ttu-id="434ab-104">Extrae un elemento de una colección de varios valores.</span><span class="sxs-lookup"><span data-stu-id="434ab-104">Extracts an element from a multivalued collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="434ab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="434ab-105">Syntax</span></span>  
  
```csharp
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="434ab-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="434ab-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="434ab-107">Expresión de consulta válida que devuelve una colección de la que extraer un elemento.</span><span class="sxs-lookup"><span data-stu-id="434ab-107">Any valid query expression that returns a collection to extract an element from.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="434ab-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="434ab-108">Return Value</span></span>  

 <span data-ttu-id="434ab-109">Un único elemento de la colección o un elemento arbitrario si la colección tiene más de uno; si la colección está vacía, devuelve `null`.</span><span class="sxs-lookup"><span data-stu-id="434ab-109">A single element in the collection or an arbitrary element if the collection has more than one; if the collection is empty, returns `null`.</span></span> <span data-ttu-id="434ab-110">Si `collection` es una colección de tipo `Collection<T>` , entonces `ANYELEMENT(collection)` es una expresión válida que da como resultado una instancia de tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="434ab-110">If `collection` is a collection of type `Collection<T>`, then `ANYELEMENT(collection)` is a valid expression that yields an instance of type `T`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="434ab-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="434ab-111">Remarks</span></span>  

 <span data-ttu-id="434ab-112">ANYELEMENT extrae un elemento arbitrario de una colección de varios valores.</span><span class="sxs-lookup"><span data-stu-id="434ab-112">ANYELEMENT extracts an arbitrary element from a multivalued collection.</span></span> <span data-ttu-id="434ab-113">Por ejemplo, a continuación se intenta extraer un elemento singleton del conjunto `Customers`.</span><span class="sxs-lookup"><span data-stu-id="434ab-113">For example, the following example attempts to extract a singleton element from the set `Customers`.</span></span>  
  
```csharp
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a><span data-ttu-id="434ab-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="434ab-114">Example</span></span>  

 <span data-ttu-id="434ab-115">La siguiente consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] usa el operador ANYELEMENT para extraer un elemento de una colección de varios valores.</span><span class="sxs-lookup"><span data-stu-id="434ab-115">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ANYELEMENT operator to extract an element from a multivalued collection.</span></span> <span data-ttu-id="434ab-116">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="434ab-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="434ab-117">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="434ab-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="434ab-118">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="434ab-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="434ab-119">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="434ab-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a><span data-ttu-id="434ab-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="434ab-120">See also</span></span>

- [<span data-ttu-id="434ab-121">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="434ab-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="434ab-122">Tipos estructurados que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="434ab-122">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
