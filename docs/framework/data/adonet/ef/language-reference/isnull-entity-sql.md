---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: 70ec49fd4643c67c6ad08fdda9166eeb8a64d254
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="d08a8-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d08a8-102">ISNULL (Entity SQL)</span></span>
<span data-ttu-id="d08a8-103">Determina si una expresión de consulta es nula.</span><span class="sxs-lookup"><span data-stu-id="d08a8-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d08a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d08a8-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="d08a8-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d08a8-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="d08a8-106">Cualquier expresión de consulta válida.</span><span class="sxs-lookup"><span data-stu-id="d08a8-106">Any valid query expression.</span></span> <span data-ttu-id="d08a8-107">No puede ser una colección, tener miembros de una colección, o un tipo de registro con propiedades de tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="d08a8-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="d08a8-108">NOT</span><span class="sxs-lookup"><span data-stu-id="d08a8-108">NOT</span></span>  
 <span data-ttu-id="d08a8-109">Niega el resultado EDM.Boolean de IS NULL.</span><span class="sxs-lookup"><span data-stu-id="d08a8-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d08a8-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d08a8-110">Return Value</span></span>  
 <span data-ttu-id="d08a8-111">`true` si `expression` devuelve null; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="d08a8-111">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d08a8-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d08a8-112">Remarks</span></span>  
 <span data-ttu-id="d08a8-113">Utilice `IS NULL` para determinar si el elemento de una combinación externa es nulo:</span><span class="sxs-lookup"><span data-stu-id="d08a8-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="d08a8-114">Utilice `IS NULL` para determinar si un miembro tiene un valor real:</span><span class="sxs-lookup"><span data-stu-id="d08a8-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="d08a8-115">En la tabla siguiente se muestra el comportamiento de `IS NULL` en algunos patrones.</span><span class="sxs-lookup"><span data-stu-id="d08a8-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="d08a8-116">Todas las excepciones se producen en el cliente antes de que se llame al proveedor:</span><span class="sxs-lookup"><span data-stu-id="d08a8-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="d08a8-117">Modelo</span><span class="sxs-lookup"><span data-stu-id="d08a8-117">Pattern</span></span>|<span data-ttu-id="d08a8-118">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="d08a8-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="d08a8-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="d08a8-119">null IS NULL</span></span>|<span data-ttu-id="d08a8-120">Devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="d08a8-120">Returns `true`.</span></span>|  
|<span data-ttu-id="d08a8-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="d08a8-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="d08a8-122">Devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="d08a8-122">Returns `true`.</span></span>|  
|<span data-ttu-id="d08a8-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="d08a8-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="d08a8-124">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="d08a8-124">Throws an error.</span></span>|  
|<span data-ttu-id="d08a8-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="d08a8-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="d08a8-126">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="d08a8-126">Throws an error.</span></span>|  
|<span data-ttu-id="d08a8-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="d08a8-127">EntityType IS NULL</span></span>|<span data-ttu-id="d08a8-128">Devuelve `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="d08a8-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="d08a8-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="d08a8-129">ComplexType IS NULL</span></span>|<span data-ttu-id="d08a8-130">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="d08a8-130">Throws an error.</span></span>|  
|<span data-ttu-id="d08a8-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="d08a8-131">RowType IS NULL</span></span>|<span data-ttu-id="d08a8-132">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="d08a8-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d08a8-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d08a8-133">Example</span></span>  
 <span data-ttu-id="d08a8-134">El siguiente [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta utiliza el operador IS NOT NULL para determinar si una expresión de consulta no es null.</span><span class="sxs-lookup"><span data-stu-id="d08a8-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="d08a8-135">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="d08a8-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d08a8-136">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d08a8-136">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="d08a8-137">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d08a8-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="d08a8-138">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="d08a8-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="d08a8-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="d08a8-139">See Also</span></span>  
 [<span data-ttu-id="d08a8-140">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d08a8-140">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
