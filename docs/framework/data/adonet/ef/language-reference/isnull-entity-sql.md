---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: d54c350196ad1ef7cfafa6d931d9d1ad8f267177
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250556"
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="d1c95-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d1c95-102">ISNULL (Entity SQL)</span></span>
<span data-ttu-id="d1c95-103">Determina si una expresión de consulta es nula.</span><span class="sxs-lookup"><span data-stu-id="d1c95-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1c95-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1c95-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="d1c95-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d1c95-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="d1c95-106">Cualquier expresión de consulta válida.</span><span class="sxs-lookup"><span data-stu-id="d1c95-106">Any valid query expression.</span></span> <span data-ttu-id="d1c95-107">No puede ser una colección, tener miembros de una colección, o un tipo de registro con propiedades de tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="d1c95-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="d1c95-108">NOT</span><span class="sxs-lookup"><span data-stu-id="d1c95-108">NOT</span></span>  
 <span data-ttu-id="d1c95-109">Niega el resultado EDM.Boolean de IS NULL.</span><span class="sxs-lookup"><span data-stu-id="d1c95-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1c95-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d1c95-110">Return Value</span></span>  
 <span data-ttu-id="d1c95-111">`true` si `expression` devuelve null; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="d1c95-111">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1c95-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d1c95-112">Remarks</span></span>  
 <span data-ttu-id="d1c95-113">Utilice `IS NULL` para determinar si el elemento de una combinación externa es nulo:</span><span class="sxs-lookup"><span data-stu-id="d1c95-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="d1c95-114">Utilice `IS NULL` para determinar si un miembro tiene un valor real:</span><span class="sxs-lookup"><span data-stu-id="d1c95-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="d1c95-115">En la tabla siguiente se muestra el comportamiento de `IS NULL` en algunos patrones.</span><span class="sxs-lookup"><span data-stu-id="d1c95-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="d1c95-116">Todas las excepciones se producen en el cliente antes de que se llame al proveedor:</span><span class="sxs-lookup"><span data-stu-id="d1c95-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="d1c95-117">Modelo</span><span class="sxs-lookup"><span data-stu-id="d1c95-117">Pattern</span></span>|<span data-ttu-id="d1c95-118">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="d1c95-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="d1c95-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="d1c95-119">null IS NULL</span></span>|<span data-ttu-id="d1c95-120">Devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="d1c95-120">Returns `true`.</span></span>|  
|<span data-ttu-id="d1c95-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="d1c95-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="d1c95-122">Devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="d1c95-122">Returns `true`.</span></span>|  
|<span data-ttu-id="d1c95-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="d1c95-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="d1c95-124">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="d1c95-124">Throws an error.</span></span>|  
|<span data-ttu-id="d1c95-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="d1c95-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="d1c95-126">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="d1c95-126">Throws an error.</span></span>|  
|<span data-ttu-id="d1c95-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="d1c95-127">EntityType IS NULL</span></span>|<span data-ttu-id="d1c95-128">Devuelve `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="d1c95-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="d1c95-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="d1c95-129">ComplexType IS NULL</span></span>|<span data-ttu-id="d1c95-130">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="d1c95-130">Throws an error.</span></span>|  
|<span data-ttu-id="d1c95-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="d1c95-131">RowType IS NULL</span></span>|<span data-ttu-id="d1c95-132">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="d1c95-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d1c95-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1c95-133">Example</span></span>  
 <span data-ttu-id="d1c95-134">La siguiente [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta utiliza el operador is not null para determinar si una expresión de consulta no es NULL.</span><span class="sxs-lookup"><span data-stu-id="d1c95-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="d1c95-135">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="d1c95-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d1c95-136">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d1c95-136">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d1c95-137">Siga el procedimiento descrito [en cómo: Ejecute una consulta que devuelva resultados](../how-to-execute-a-query-that-returns-structuraltype-results.md)de StructuralType.</span><span class="sxs-lookup"><span data-stu-id="d1c95-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d1c95-138">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="d1c95-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="d1c95-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1c95-139">See also</span></span>

- [<span data-ttu-id="d1c95-140">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d1c95-140">Entity SQL Reference</span></span>](entity-sql-reference.md)
