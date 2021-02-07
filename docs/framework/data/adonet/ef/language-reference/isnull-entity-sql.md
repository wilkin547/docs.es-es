---
description: 'Más información acerca de: ISNULL (Entity SQL)'
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: 1dbaf964facf089ab6714ebd58baf8b040288cff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748497"
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="ea0ce-103">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ea0ce-103">ISNULL (Entity SQL)</span></span>

<span data-ttu-id="ea0ce-104">Determina si una expresión de consulta es nula.</span><span class="sxs-lookup"><span data-stu-id="ea0ce-104">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea0ce-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea0ce-105">Syntax</span></span>  
  
```sql  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="ea0ce-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ea0ce-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="ea0ce-107">Cualquier expresión de consulta válida.</span><span class="sxs-lookup"><span data-stu-id="ea0ce-107">Any valid query expression.</span></span> <span data-ttu-id="ea0ce-108">No puede ser una colección, tener miembros de una colección, o un tipo de registro con propiedades de tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="ea0ce-108">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="ea0ce-109">NOT</span><span class="sxs-lookup"><span data-stu-id="ea0ce-109">NOT</span></span>  
 <span data-ttu-id="ea0ce-110">Niega el resultado EDM.Boolean de IS NULL.</span><span class="sxs-lookup"><span data-stu-id="ea0ce-110">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea0ce-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ea0ce-111">Return Value</span></span>  

 <span data-ttu-id="ea0ce-112">`true` si `expression` devuelve null; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ea0ce-112">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea0ce-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ea0ce-113">Remarks</span></span>  

 <span data-ttu-id="ea0ce-114">Utilice `IS NULL` para determinar si el elemento de una combinación externa es nulo:</span><span class="sxs-lookup"><span data-stu-id="ea0ce-114">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```sql  
select c
      from LOB.Customers as c left outer join LOB.Orders as o
                              on c.ID = o.CustomerID
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="ea0ce-115">Utilice `IS NULL` para determinar si un miembro tiene un valor real:</span><span class="sxs-lookup"><span data-stu-id="ea0ce-115">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```sql  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="ea0ce-116">En la tabla siguiente se muestra el comportamiento de `IS NULL` en algunos patrones.</span><span class="sxs-lookup"><span data-stu-id="ea0ce-116">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="ea0ce-117">Todas las excepciones se producen en el cliente antes de que se llame al proveedor:</span><span class="sxs-lookup"><span data-stu-id="ea0ce-117">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="ea0ce-118">Patrón</span><span class="sxs-lookup"><span data-stu-id="ea0ce-118">Pattern</span></span>|<span data-ttu-id="ea0ce-119">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="ea0ce-119">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="ea0ce-120">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="ea0ce-120">null IS NULL</span></span>|<span data-ttu-id="ea0ce-121">Devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="ea0ce-121">Returns `true`.</span></span>|  
|<span data-ttu-id="ea0ce-122">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="ea0ce-122">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="ea0ce-123">Devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="ea0ce-123">Returns `true`.</span></span>|  
|<span data-ttu-id="ea0ce-124">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="ea0ce-124">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="ea0ce-125">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="ea0ce-125">Throws an error.</span></span>|  
|<span data-ttu-id="ea0ce-126">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="ea0ce-126">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="ea0ce-127">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="ea0ce-127">Throws an error.</span></span>|  
|<span data-ttu-id="ea0ce-128">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="ea0ce-128">EntityType IS NULL</span></span>|<span data-ttu-id="ea0ce-129">Devuelve `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="ea0ce-129">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="ea0ce-130">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="ea0ce-130">ComplexType IS NULL</span></span>|<span data-ttu-id="ea0ce-131">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="ea0ce-131">Throws an error.</span></span>|  
|<span data-ttu-id="ea0ce-132">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="ea0ce-132">RowType IS NULL</span></span>|<span data-ttu-id="ea0ce-133">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="ea0ce-133">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ea0ce-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea0ce-134">Example</span></span>  

 <span data-ttu-id="ea0ce-135">La siguiente [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta utiliza el operador is not null para determinar si una expresión de consulta no es NULL.</span><span class="sxs-lookup"><span data-stu-id="ea0ce-135">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="ea0ce-136">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="ea0ce-136">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ea0ce-137">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ea0ce-137">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ea0ce-138">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ea0ce-138">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ea0ce-139">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ea0ce-139">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#ISNULL](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="ea0ce-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea0ce-140">See also</span></span>

- [<span data-ttu-id="ea0ce-141">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ea0ce-141">Entity SQL Reference</span></span>](entity-sql-reference.md)
