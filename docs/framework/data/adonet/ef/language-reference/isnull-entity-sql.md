---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: 1b728e170968e2fbeb67eef3f8f940c64816ff0d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528737"
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="37812-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="37812-102">ISNULL (Entity SQL)</span></span>
<span data-ttu-id="37812-103">Determina si una expresión de consulta es nula.</span><span class="sxs-lookup"><span data-stu-id="37812-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37812-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37812-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="37812-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="37812-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="37812-106">Cualquier expresión de consulta válida.</span><span class="sxs-lookup"><span data-stu-id="37812-106">Any valid query expression.</span></span> <span data-ttu-id="37812-107">No puede ser una colección, tener miembros de una colección, o un tipo de registro con propiedades de tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="37812-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="37812-108">NOT</span><span class="sxs-lookup"><span data-stu-id="37812-108">NOT</span></span>  
 <span data-ttu-id="37812-109">Niega el resultado EDM.Boolean de IS NULL.</span><span class="sxs-lookup"><span data-stu-id="37812-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37812-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="37812-110">Return Value</span></span>  
 <span data-ttu-id="37812-111">`true` si `expression` devuelve null; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="37812-111">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37812-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="37812-112">Remarks</span></span>  
 <span data-ttu-id="37812-113">Utilice `IS NULL` para determinar si el elemento de una combinación externa es nulo:</span><span class="sxs-lookup"><span data-stu-id="37812-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="37812-114">Utilice `IS NULL` para determinar si un miembro tiene un valor real:</span><span class="sxs-lookup"><span data-stu-id="37812-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="37812-115">En la tabla siguiente se muestra el comportamiento de `IS NULL` en algunos patrones.</span><span class="sxs-lookup"><span data-stu-id="37812-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="37812-116">Todas las excepciones se producen en el cliente antes de que se llame al proveedor:</span><span class="sxs-lookup"><span data-stu-id="37812-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="37812-117">Modelo</span><span class="sxs-lookup"><span data-stu-id="37812-117">Pattern</span></span>|<span data-ttu-id="37812-118">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="37812-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="37812-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="37812-119">null IS NULL</span></span>|<span data-ttu-id="37812-120">Devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="37812-120">Returns `true`.</span></span>|  
|<span data-ttu-id="37812-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="37812-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="37812-122">Devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="37812-122">Returns `true`.</span></span>|  
|<span data-ttu-id="37812-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="37812-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="37812-124">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="37812-124">Throws an error.</span></span>|  
|<span data-ttu-id="37812-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="37812-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="37812-126">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="37812-126">Throws an error.</span></span>|  
|<span data-ttu-id="37812-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="37812-127">EntityType IS NULL</span></span>|<span data-ttu-id="37812-128">Devuelve `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="37812-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="37812-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="37812-129">ComplexType IS NULL</span></span>|<span data-ttu-id="37812-130">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="37812-130">Throws an error.</span></span>|  
|<span data-ttu-id="37812-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="37812-131">RowType IS NULL</span></span>|<span data-ttu-id="37812-132">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="37812-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="37812-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37812-133">Example</span></span>  
 <span data-ttu-id="37812-134">La siguiente [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta usa el operador IS NOT NULL para determinar si una expresión de consulta no es null.</span><span class="sxs-lookup"><span data-stu-id="37812-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="37812-135">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="37812-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="37812-136">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="37812-136">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="37812-137">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="37812-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="37812-138">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="37812-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="37812-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="37812-139">See also</span></span>
- [<span data-ttu-id="37812-140">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="37812-140">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
