---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: 3360ad4ca7306a8cc1b7d6948204f825ff9a93c6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203623"
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="6acc3-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6acc3-102">ISNULL (Entity SQL)</span></span>

<span data-ttu-id="6acc3-103">Determina si una expresión de consulta es nula.</span><span class="sxs-lookup"><span data-stu-id="6acc3-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6acc3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6acc3-104">Syntax</span></span>  
  
```sql  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="6acc3-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6acc3-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="6acc3-106">Cualquier expresión de consulta válida.</span><span class="sxs-lookup"><span data-stu-id="6acc3-106">Any valid query expression.</span></span> <span data-ttu-id="6acc3-107">No puede ser una colección, tener miembros de una colección, o un tipo de registro con propiedades de tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="6acc3-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="6acc3-108">NOT</span><span class="sxs-lookup"><span data-stu-id="6acc3-108">NOT</span></span>  
 <span data-ttu-id="6acc3-109">Niega el resultado EDM.Boolean de IS NULL.</span><span class="sxs-lookup"><span data-stu-id="6acc3-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6acc3-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6acc3-110">Return Value</span></span>  

 <span data-ttu-id="6acc3-111">`true` si `expression` devuelve null; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="6acc3-111">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6acc3-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6acc3-112">Remarks</span></span>  

 <span data-ttu-id="6acc3-113">Utilice `IS NULL` para determinar si el elemento de una combinación externa es nulo:</span><span class="sxs-lookup"><span data-stu-id="6acc3-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```sql  
select c
      from LOB.Customers as c left outer join LOB.Orders as o
                              on c.ID = o.CustomerID
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="6acc3-114">Utilice `IS NULL` para determinar si un miembro tiene un valor real:</span><span class="sxs-lookup"><span data-stu-id="6acc3-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```sql  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="6acc3-115">En la tabla siguiente se muestra el comportamiento de `IS NULL` en algunos patrones.</span><span class="sxs-lookup"><span data-stu-id="6acc3-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="6acc3-116">Todas las excepciones se producen en el cliente antes de que se llame al proveedor:</span><span class="sxs-lookup"><span data-stu-id="6acc3-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="6acc3-117">Modelo</span><span class="sxs-lookup"><span data-stu-id="6acc3-117">Pattern</span></span>|<span data-ttu-id="6acc3-118">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="6acc3-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="6acc3-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="6acc3-119">null IS NULL</span></span>|<span data-ttu-id="6acc3-120">Devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="6acc3-120">Returns `true`.</span></span>|  
|<span data-ttu-id="6acc3-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="6acc3-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="6acc3-122">Devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="6acc3-122">Returns `true`.</span></span>|  
|<span data-ttu-id="6acc3-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="6acc3-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="6acc3-124">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="6acc3-124">Throws an error.</span></span>|  
|<span data-ttu-id="6acc3-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="6acc3-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="6acc3-126">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="6acc3-126">Throws an error.</span></span>|  
|<span data-ttu-id="6acc3-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="6acc3-127">EntityType IS NULL</span></span>|<span data-ttu-id="6acc3-128">Devuelve `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="6acc3-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="6acc3-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="6acc3-129">ComplexType IS NULL</span></span>|<span data-ttu-id="6acc3-130">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="6acc3-130">Throws an error.</span></span>|  
|<span data-ttu-id="6acc3-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="6acc3-131">RowType IS NULL</span></span>|<span data-ttu-id="6acc3-132">Produce un error.</span><span class="sxs-lookup"><span data-stu-id="6acc3-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6acc3-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6acc3-133">Example</span></span>  

 <span data-ttu-id="6acc3-134">La siguiente [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta utiliza el operador is not null para determinar si una expresión de consulta no es NULL.</span><span class="sxs-lookup"><span data-stu-id="6acc3-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="6acc3-135">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="6acc3-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6acc3-136">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6acc3-136">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6acc3-137">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6acc3-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="6acc3-138">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="6acc3-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#ISNULL](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="6acc3-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6acc3-139">See also</span></span>

- [<span data-ttu-id="6acc3-140">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6acc3-140">Entity SQL Reference</span></span>](entity-sql-reference.md)
