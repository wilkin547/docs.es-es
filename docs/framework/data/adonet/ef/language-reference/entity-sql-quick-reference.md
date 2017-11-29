---
title: "Referencia rápida de Entity SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 19be8e04f8bb0cb11c98d5361deb6deffe797fca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="d51ec-102">Referencia rápida de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d51ec-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="d51ec-103">Este tema proporciona una referencia rápida a las consultas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d51ec-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="d51ec-104">Las consultas en este tema se basan en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="d51ec-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="d51ec-105">Literales</span><span class="sxs-lookup"><span data-stu-id="d51ec-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="d51ec-106">String</span><span class="sxs-lookup"><span data-stu-id="d51ec-106">String</span></span>  
 <span data-ttu-id="d51ec-107">Hay literales de cadenas de caracteres Unicode y no Unicode.</span><span class="sxs-lookup"><span data-stu-id="d51ec-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="d51ec-108">Las cadenas Unicode van precedidas de N. Por ejemplo, `N'hello'`.</span><span class="sxs-lookup"><span data-stu-id="d51ec-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="d51ec-109">A continuación se incluye un ejemplo de un literal de cadena no Unicode:</span><span class="sxs-lookup"><span data-stu-id="d51ec-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="d51ec-110">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-110">Output:</span></span>  
  
|<span data-ttu-id="d51ec-111">Valor</span><span class="sxs-lookup"><span data-stu-id="d51ec-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="d51ec-112">hello</span><span class="sxs-lookup"><span data-stu-id="d51ec-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="d51ec-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="d51ec-113">DateTime</span></span>  
 <span data-ttu-id="d51ec-114">En los literales DateTime, las partes de fecha y hora son obligatorias.</span><span class="sxs-lookup"><span data-stu-id="d51ec-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="d51ec-115">No hay valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="d51ec-115">There are no default values.</span></span>  
  
 <span data-ttu-id="d51ec-116">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-116">Example:</span></span>  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="d51ec-117">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-117">Output:</span></span>  
  
|<span data-ttu-id="d51ec-118">Valor</span><span class="sxs-lookup"><span data-stu-id="d51ec-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="d51ec-119">25.12.06 01:01:00</span><span class="sxs-lookup"><span data-stu-id="d51ec-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="d51ec-120">Integer</span><span class="sxs-lookup"><span data-stu-id="d51ec-120">Integer</span></span>  
 <span data-ttu-id="d51ec-121">Los literales enteros pueden ser de tipo Int32 (123), UInt32 (123U), Int64 (123L) y UInt64 (123UL).</span><span class="sxs-lookup"><span data-stu-id="d51ec-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="d51ec-122">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-122">Example:</span></span>  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="d51ec-123">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-123">Output:</span></span>  
  
|<span data-ttu-id="d51ec-124">Valor</span><span class="sxs-lookup"><span data-stu-id="d51ec-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="d51ec-125">1</span><span class="sxs-lookup"><span data-stu-id="d51ec-125">1</span></span>|  
|<span data-ttu-id="d51ec-126">2</span><span class="sxs-lookup"><span data-stu-id="d51ec-126">2</span></span>|  
|<span data-ttu-id="d51ec-127">3</span><span class="sxs-lookup"><span data-stu-id="d51ec-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="d51ec-128">Otros</span><span class="sxs-lookup"><span data-stu-id="d51ec-128">Other</span></span>  
 <span data-ttu-id="d51ec-129">Los literales Other admitidos por [!INCLUDE[esql](../../../../../../includes/esql-md.md)] son Guid, Binary, Float/Double, Decimal y `null`.</span><span class="sxs-lookup"><span data-stu-id="d51ec-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="d51ec-130">Los literales NULL en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se consideran compatibles con todos los demás tipos del modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="d51ec-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="d51ec-131">Constructores de tipos</span><span class="sxs-lookup"><span data-stu-id="d51ec-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="d51ec-132">ROW</span><span class="sxs-lookup"><span data-stu-id="d51ec-132">ROW</span></span>  
 <span data-ttu-id="d51ec-133">[FILA](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) crea un valor (registro) anónimo, escrito estructuralmente como en:`ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="d51ec-133">[ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="d51ec-134">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-134">Example:</span></span>  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 <span data-ttu-id="d51ec-135">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-135">Output:</span></span>  
  
|<span data-ttu-id="d51ec-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="d51ec-136">ProductID</span></span>|<span data-ttu-id="d51ec-137">Name</span><span class="sxs-lookup"><span data-stu-id="d51ec-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="d51ec-138">1</span><span class="sxs-lookup"><span data-stu-id="d51ec-138">1</span></span>|<span data-ttu-id="d51ec-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="d51ec-139">Adjustable Race</span></span>|  
|<span data-ttu-id="d51ec-140">879</span><span class="sxs-lookup"><span data-stu-id="d51ec-140">879</span></span>|<span data-ttu-id="d51ec-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="d51ec-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="d51ec-142">712</span><span class="sxs-lookup"><span data-stu-id="d51ec-142">712</span></span>|<span data-ttu-id="d51ec-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="d51ec-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="d51ec-144">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-144">...</span></span>|<span data-ttu-id="d51ec-145">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="d51ec-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="d51ec-146">MULTISET</span></span>  
 <span data-ttu-id="d51ec-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) crea colecciones, como:</span><span class="sxs-lookup"><span data-stu-id="d51ec-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="d51ec-148">`MULTISET(1,2,2,3)``--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="d51ec-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="d51ec-149">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-149">Example:</span></span>  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="d51ec-150">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-150">Output:</span></span>  
  
|<span data-ttu-id="d51ec-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="d51ec-151">ProductID</span></span>|<span data-ttu-id="d51ec-152">Name</span><span class="sxs-lookup"><span data-stu-id="d51ec-152">Name</span></span>|<span data-ttu-id="d51ec-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="d51ec-153">ProductNumber</span></span>|<span data-ttu-id="d51ec-154">…</span><span class="sxs-lookup"><span data-stu-id="d51ec-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="d51ec-155">842</span><span class="sxs-lookup"><span data-stu-id="d51ec-155">842</span></span>|<span data-ttu-id="d51ec-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="d51ec-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="d51ec-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="d51ec-157">PA-T100</span></span>|<span data-ttu-id="d51ec-158">…</span><span class="sxs-lookup"><span data-stu-id="d51ec-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="d51ec-159">Objeto</span><span class="sxs-lookup"><span data-stu-id="d51ec-159">Object</span></span>  
 <span data-ttu-id="d51ec-160">[Con el nombre de tipo al Constructor de](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) construye objetos definidos por el usuario (con nombre), como `person("abc", 12)`.</span><span class="sxs-lookup"><span data-stu-id="d51ec-160">[Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="d51ec-161">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-161">Example:</span></span>  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="d51ec-162">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-162">Output:</span></span>  
  
|<span data-ttu-id="d51ec-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="d51ec-163">SalesOrderDetailID</span></span>|<span data-ttu-id="d51ec-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="d51ec-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="d51ec-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="d51ec-165">OrderQty</span></span>|<span data-ttu-id="d51ec-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="d51ec-166">ProductID</span></span>|<span data-ttu-id="d51ec-167">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="d51ec-168">1</span><span class="sxs-lookup"><span data-stu-id="d51ec-168">1</span></span>|<span data-ttu-id="d51ec-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="d51ec-169">4911-403C-98</span></span>|<span data-ttu-id="d51ec-170">1</span><span class="sxs-lookup"><span data-stu-id="d51ec-170">1</span></span>|<span data-ttu-id="d51ec-171">776</span><span class="sxs-lookup"><span data-stu-id="d51ec-171">776</span></span>|<span data-ttu-id="d51ec-172">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-172">...</span></span>|  
|<span data-ttu-id="d51ec-173">2</span><span class="sxs-lookup"><span data-stu-id="d51ec-173">2</span></span>|<span data-ttu-id="d51ec-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="d51ec-174">4911-403C-98</span></span>|<span data-ttu-id="d51ec-175">3</span><span class="sxs-lookup"><span data-stu-id="d51ec-175">3</span></span>|<span data-ttu-id="d51ec-176">777</span><span class="sxs-lookup"><span data-stu-id="d51ec-176">777</span></span>|<span data-ttu-id="d51ec-177">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-177">...</span></span>|  
|<span data-ttu-id="d51ec-178">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-178">...</span></span>|<span data-ttu-id="d51ec-179">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-179">...</span></span>|<span data-ttu-id="d51ec-180">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-180">...</span></span>|<span data-ttu-id="d51ec-181">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-181">...</span></span>|<span data-ttu-id="d51ec-182">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="d51ec-183">Referencias</span><span class="sxs-lookup"><span data-stu-id="d51ec-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="d51ec-184">REF</span><span class="sxs-lookup"><span data-stu-id="d51ec-184">REF</span></span>  
 <span data-ttu-id="d51ec-185">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) crea una referencia a una instancia de tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="d51ec-185">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="d51ec-186">Por ejemplo, la consulta siguiente devuelve referencias a cada entidad Order en el conjunto de entidades Orders:</span><span class="sxs-lookup"><span data-stu-id="d51ec-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="d51ec-187">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-187">Output:</span></span>  
  
|<span data-ttu-id="d51ec-188">Valor</span><span class="sxs-lookup"><span data-stu-id="d51ec-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="d51ec-189">1</span><span class="sxs-lookup"><span data-stu-id="d51ec-189">1</span></span>|  
|<span data-ttu-id="d51ec-190">2</span><span class="sxs-lookup"><span data-stu-id="d51ec-190">2</span></span>|  
|<span data-ttu-id="d51ec-191">3</span><span class="sxs-lookup"><span data-stu-id="d51ec-191">3</span></span>|  
|<span data-ttu-id="d51ec-192">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-192">...</span></span>|  
  
 <span data-ttu-id="d51ec-193">En el ejemplo siguiente se usa el operador de extracción de propiedades (.) para tener acceso a una propiedad de una entidad.</span><span class="sxs-lookup"><span data-stu-id="d51ec-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="d51ec-194">Cuando se utiliza el operador de extracción de propiedades, la referencia se desreferencia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d51ec-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="d51ec-195">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-195">Example:</span></span>  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="d51ec-196">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-196">Output:</span></span>  
  
|<span data-ttu-id="d51ec-197">Valor</span><span class="sxs-lookup"><span data-stu-id="d51ec-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="d51ec-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="d51ec-198">Adjustable Race</span></span>|  
|<span data-ttu-id="d51ec-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="d51ec-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="d51ec-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="d51ec-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="d51ec-201">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="d51ec-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="d51ec-202">DEREF</span></span>  
 <span data-ttu-id="d51ec-203">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) desreferencia un valor de referencia y genera el resultado de dicha desreferenciación.</span><span class="sxs-lookup"><span data-stu-id="d51ec-203">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="d51ec-204">Por ejemplo, la consulta siguiente genera las entidades Order para cada entidad Order en el conjunto de entidades Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.</span><span class="sxs-lookup"><span data-stu-id="d51ec-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="d51ec-205">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-205">Example:</span></span>  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="d51ec-206">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-206">Output:</span></span>  
  
|<span data-ttu-id="d51ec-207">Valor</span><span class="sxs-lookup"><span data-stu-id="d51ec-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="d51ec-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="d51ec-208">Adjustable Race</span></span>|  
|<span data-ttu-id="d51ec-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="d51ec-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="d51ec-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="d51ec-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="d51ec-211">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="d51ec-212">CREATEREF y KEY</span><span class="sxs-lookup"><span data-stu-id="d51ec-212">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="d51ec-213">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) crea una referencia que pasa una clave.</span><span class="sxs-lookup"><span data-stu-id="d51ec-213">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="d51ec-214">[CLAVE](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extrae la parte de una expresión con referencia de tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="d51ec-214">[KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="d51ec-215">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-215">Example:</span></span>  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="d51ec-216">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-216">Output:</span></span>  
  
|<span data-ttu-id="d51ec-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="d51ec-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="d51ec-218">980</span><span class="sxs-lookup"><span data-stu-id="d51ec-218">980</span></span>|  
|<span data-ttu-id="d51ec-219">365</span><span class="sxs-lookup"><span data-stu-id="d51ec-219">365</span></span>|  
|<span data-ttu-id="d51ec-220">771</span><span class="sxs-lookup"><span data-stu-id="d51ec-220">771</span></span>|  
|<span data-ttu-id="d51ec-221">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="d51ec-222">Funciones</span><span class="sxs-lookup"><span data-stu-id="d51ec-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="d51ec-223">Canónicas</span><span class="sxs-lookup"><span data-stu-id="d51ec-223">Canonical</span></span>  
 <span data-ttu-id="d51ec-224">El espacio de nombres [funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) es Edm, como en `Edm.Length("string")`.</span><span class="sxs-lookup"><span data-stu-id="d51ec-224">The namespace for [canonical functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="d51ec-225">No es necesario especificar el espacio de nombres a no ser que se importe otro espacio de nombres que contenga una función con el mismo nombre que una función canónica.</span><span class="sxs-lookup"><span data-stu-id="d51ec-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="d51ec-226">Si dos espacios de nombres tienen la misma función, el usuario debe especificar el nombre completo.</span><span class="sxs-lookup"><span data-stu-id="d51ec-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="d51ec-227">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-227">Example:</span></span>  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="d51ec-228">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-228">Output:</span></span>  
  
|<span data-ttu-id="d51ec-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="d51ec-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="d51ec-230">6</span><span class="sxs-lookup"><span data-stu-id="d51ec-230">6</span></span>|  
|<span data-ttu-id="d51ec-231">6</span><span class="sxs-lookup"><span data-stu-id="d51ec-231">6</span></span>|  
|<span data-ttu-id="d51ec-232">5</span><span class="sxs-lookup"><span data-stu-id="d51ec-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="d51ec-233">Específicas de proveedores de Microsoft</span><span class="sxs-lookup"><span data-stu-id="d51ec-233">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="d51ec-234">[Funciones específicas del proveedor de Microsoft](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) están en el `SqlServer` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d51ec-234">[Microsoft provider-specific functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="d51ec-235">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-235">Example:</span></span>  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="d51ec-236">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-236">Output:</span></span>  
  
|<span data-ttu-id="d51ec-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="d51ec-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="d51ec-238">27</span><span class="sxs-lookup"><span data-stu-id="d51ec-238">27</span></span>|  
|<span data-ttu-id="d51ec-239">27</span><span class="sxs-lookup"><span data-stu-id="d51ec-239">27</span></span>|  
|<span data-ttu-id="d51ec-240">26</span><span class="sxs-lookup"><span data-stu-id="d51ec-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="d51ec-241">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="d51ec-241">Namespaces</span></span>  
 <span data-ttu-id="d51ec-242">[USAR](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) especifica los espacios de nombres utilizados en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="d51ec-242">[USING](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="d51ec-243">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-243">Example:</span></span>  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="d51ec-244">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-244">Output:</span></span>  
  
|<span data-ttu-id="d51ec-245">Valor</span><span class="sxs-lookup"><span data-stu-id="d51ec-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="d51ec-246">aa</span><span class="sxs-lookup"><span data-stu-id="d51ec-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="d51ec-247">Paginación</span><span class="sxs-lookup"><span data-stu-id="d51ec-247">Paging</span></span>  
 <span data-ttu-id="d51ec-248">Paginación se puede expresar declarando un [omitir](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) y [límite](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) subcláusulas a la [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) cláusula.</span><span class="sxs-lookup"><span data-stu-id="d51ec-248">Paging can be expressed by declaring a [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses to the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="d51ec-249">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-249">Example:</span></span>  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="d51ec-250">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-250">Output:</span></span>  
  
|<span data-ttu-id="d51ec-251">Id.</span><span class="sxs-lookup"><span data-stu-id="d51ec-251">ID</span></span>|<span data-ttu-id="d51ec-252">Name</span><span class="sxs-lookup"><span data-stu-id="d51ec-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="d51ec-253">10</span><span class="sxs-lookup"><span data-stu-id="d51ec-253">10</span></span>|<span data-ttu-id="d51ec-254">Adina</span><span class="sxs-lookup"><span data-stu-id="d51ec-254">Adina</span></span>|  
|<span data-ttu-id="d51ec-255">11</span><span class="sxs-lookup"><span data-stu-id="d51ec-255">11</span></span>|<span data-ttu-id="d51ec-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="d51ec-256">Agcaoili</span></span>|  
|<span data-ttu-id="d51ec-257">12</span><span class="sxs-lookup"><span data-stu-id="d51ec-257">12</span></span>|<span data-ttu-id="d51ec-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="d51ec-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="d51ec-259">Agrupar</span><span class="sxs-lookup"><span data-stu-id="d51ec-259">Grouping</span></span>  
 <span data-ttu-id="d51ec-260">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) especifica los grupos en los objetos devueltos por una consulta ([seleccione](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expresión que se van a colocar.</span><span class="sxs-lookup"><span data-stu-id="d51ec-260">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="d51ec-261">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-261">Example:</span></span>  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="d51ec-262">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-262">Output:</span></span>  
  
|<span data-ttu-id="d51ec-263">name</span><span class="sxs-lookup"><span data-stu-id="d51ec-263">name</span></span>|  
|----------|  
|<span data-ttu-id="d51ec-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="d51ec-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="d51ec-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="d51ec-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="d51ec-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="d51ec-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="d51ec-267">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="d51ec-268">Navegación</span><span class="sxs-lookup"><span data-stu-id="d51ec-268">Navigation</span></span>  
 <span data-ttu-id="d51ec-269">El operador de navegación por relaciones permite navegar por la relación de un tipo de entidad (extremo inicial) a otro (extremo final).</span><span class="sxs-lookup"><span data-stu-id="d51ec-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="d51ec-270">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) toma el tipo de relación calificado como \<espacio de nombres >.\< nombre de tipo de relación >.</span><span class="sxs-lookup"><span data-stu-id="d51ec-270">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="d51ec-271">Navegue devuelve Ref\<T > Si la cardinalidad del extremo final es 1.</span><span class="sxs-lookup"><span data-stu-id="d51ec-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="d51ec-272">Si la cardinalidad del extremo final es n, la colección < Ref\<T >> se devolverá.</span><span class="sxs-lookup"><span data-stu-id="d51ec-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="d51ec-273">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-273">Example:</span></span>  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="d51ec-274">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-274">Output:</span></span>  
  
|<span data-ttu-id="d51ec-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="d51ec-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="d51ec-276">1</span><span class="sxs-lookup"><span data-stu-id="d51ec-276">1</span></span>|  
|<span data-ttu-id="d51ec-277">2</span><span class="sxs-lookup"><span data-stu-id="d51ec-277">2</span></span>|  
|<span data-ttu-id="d51ec-278">3</span><span class="sxs-lookup"><span data-stu-id="d51ec-278">3</span></span>|  
|<span data-ttu-id="d51ec-279">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="d51ec-280">SELECT VALUE y SELECT</span><span class="sxs-lookup"><span data-stu-id="d51ec-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="d51ec-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="d51ec-281">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="d51ec-282"> proporciona la cláusula SELECT VALUE para omitir la creación de filas implícitas.</span><span class="sxs-lookup"><span data-stu-id="d51ec-282"> provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="d51ec-283">Solo se puede especificar un elemento en una cláusula SELECT VALUE.</span><span class="sxs-lookup"><span data-stu-id="d51ec-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="d51ec-284">Cuando se utiliza una cláusula de ese tipo, no se crea ningún contenedor de filas en torno a los elementos en la cláusula SELECT y se puede generar una colección de la forma deseada, por ejemplo: `SELECT VALUE a`.</span><span class="sxs-lookup"><span data-stu-id="d51ec-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="d51ec-285">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-285">Example:</span></span>  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="d51ec-286">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-286">Output:</span></span>  
  
|<span data-ttu-id="d51ec-287">Name</span><span class="sxs-lookup"><span data-stu-id="d51ec-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="d51ec-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="d51ec-288">Adjustable Race</span></span>|  
|<span data-ttu-id="d51ec-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="d51ec-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="d51ec-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="d51ec-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="d51ec-291">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="d51ec-292">SELECT</span><span class="sxs-lookup"><span data-stu-id="d51ec-292">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="d51ec-293"> también proporciona el constructor de filas para crear filas arbitrarias.</span><span class="sxs-lookup"><span data-stu-id="d51ec-293"> also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="d51ec-294">SELECT toma uno o más elementos en la proyección y devuelve un registro de datos con campos, por ejemplo: `SELECT a, b, c`.</span><span class="sxs-lookup"><span data-stu-id="d51ec-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="d51ec-295">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-295">Example:</span></span>  
  
 <span data-ttu-id="d51ec-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="d51ec-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="d51ec-297">Name</span><span class="sxs-lookup"><span data-stu-id="d51ec-297">Name</span></span>|<span data-ttu-id="d51ec-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="d51ec-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="d51ec-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="d51ec-299">Adjustable Race</span></span>|<span data-ttu-id="d51ec-300">1</span><span class="sxs-lookup"><span data-stu-id="d51ec-300">1</span></span>|  
|<span data-ttu-id="d51ec-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="d51ec-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="d51ec-302">879</span><span class="sxs-lookup"><span data-stu-id="d51ec-302">879</span></span>|  
|<span data-ttu-id="d51ec-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="d51ec-303">AWC Logo Cap</span></span>|<span data-ttu-id="d51ec-304">712</span><span class="sxs-lookup"><span data-stu-id="d51ec-304">712</span></span>|  
|<span data-ttu-id="d51ec-305">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-305">...</span></span>|<span data-ttu-id="d51ec-306">...</span><span class="sxs-lookup"><span data-stu-id="d51ec-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="d51ec-307">EXPRESIÓN CASE</span><span class="sxs-lookup"><span data-stu-id="d51ec-307">CASE EXPRESSION</span></span>  
 <span data-ttu-id="d51ec-308">El [caso expresión](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) se evalúa como un conjunto de expresiones booleanas para determinar el resultado.</span><span class="sxs-lookup"><span data-stu-id="d51ec-308">The [case expression](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="d51ec-309">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d51ec-309">Example:</span></span>  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="d51ec-310">Resultado:</span><span class="sxs-lookup"><span data-stu-id="d51ec-310">Output:</span></span>  
  
|<span data-ttu-id="d51ec-311">Valor</span><span class="sxs-lookup"><span data-stu-id="d51ec-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="d51ec-312">true</span><span class="sxs-lookup"><span data-stu-id="d51ec-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d51ec-313">Vea también</span><span class="sxs-lookup"><span data-stu-id="d51ec-313">See Also</span></span>  
 [<span data-ttu-id="d51ec-314">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d51ec-314">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="d51ec-315">Información general sobre de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d51ec-315">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
