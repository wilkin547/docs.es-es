---
description: 'Más información acerca de: Entity SQL referencia rápida'
title: Referencia rápida de Entity SQL
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: ddac48bece1f0e9df737db295d4d028529ea290f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724562"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="8281f-103">Referencia rápida de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8281f-103">Entity SQL Quick Reference</span></span>

<span data-ttu-id="8281f-104">Este tema proporciona una referencia rápida a las consultas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8281f-104">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="8281f-105">Las consultas de este tema se basan en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="8281f-105">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="8281f-106">Literales</span><span class="sxs-lookup"><span data-stu-id="8281f-106">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="8281f-107">String</span><span class="sxs-lookup"><span data-stu-id="8281f-107">String</span></span>  

 <span data-ttu-id="8281f-108">Hay literales de cadenas de caracteres Unicode y no Unicode.</span><span class="sxs-lookup"><span data-stu-id="8281f-108">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="8281f-109">Las cadenas Unicode se anteponen a N. Por ejemplo, `N'hello'` .</span><span class="sxs-lookup"><span data-stu-id="8281f-109">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="8281f-110">A continuación se incluye un ejemplo de un literal de cadena no Unicode:</span><span class="sxs-lookup"><span data-stu-id="8281f-110">The following is an example of a Non-Unicode string literal:</span></span>  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="8281f-111">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-111">Output:</span></span>  
  
|<span data-ttu-id="8281f-112">Value</span><span class="sxs-lookup"><span data-stu-id="8281f-112">Value</span></span>|  
|-----------|  
|<span data-ttu-id="8281f-113">hello</span><span class="sxs-lookup"><span data-stu-id="8281f-113">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="8281f-114">DateTime</span><span class="sxs-lookup"><span data-stu-id="8281f-114">DateTime</span></span>  

 <span data-ttu-id="8281f-115">En los literales DateTime, las partes de fecha y hora son obligatorias.</span><span class="sxs-lookup"><span data-stu-id="8281f-115">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="8281f-116">No hay valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="8281f-116">There are no default values.</span></span>  
  
 <span data-ttu-id="8281f-117">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-117">Example:</span></span>  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="8281f-118">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-118">Output:</span></span>  
  
|<span data-ttu-id="8281f-119">Value</span><span class="sxs-lookup"><span data-stu-id="8281f-119">Value</span></span>|  
|-----------|  
|<span data-ttu-id="8281f-120">25.12.06 01:01:00</span><span class="sxs-lookup"><span data-stu-id="8281f-120">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="8281f-121">Entero</span><span class="sxs-lookup"><span data-stu-id="8281f-121">Integer</span></span>  

 <span data-ttu-id="8281f-122">Los literales enteros pueden ser de tipo Int32 (123), UInt32 (123U), Int64 (123L) y UInt64 (123UL).</span><span class="sxs-lookup"><span data-stu-id="8281f-122">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="8281f-123">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-123">Example:</span></span>  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="8281f-124">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-124">Output:</span></span>  
  
|<span data-ttu-id="8281f-125">Value</span><span class="sxs-lookup"><span data-stu-id="8281f-125">Value</span></span>|  
|-----------|  
|<span data-ttu-id="8281f-126">1</span><span class="sxs-lookup"><span data-stu-id="8281f-126">1</span></span>|  
|<span data-ttu-id="8281f-127">2</span><span class="sxs-lookup"><span data-stu-id="8281f-127">2</span></span>|  
|<span data-ttu-id="8281f-128">3</span><span class="sxs-lookup"><span data-stu-id="8281f-128">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="8281f-129">Otros</span><span class="sxs-lookup"><span data-stu-id="8281f-129">Other</span></span>  

 <span data-ttu-id="8281f-130">Los literales Other admitidos por [!INCLUDE[esql](../../../../../../includes/esql-md.md)] son Guid, Binary, Float/Double, Decimal y `null`.</span><span class="sxs-lookup"><span data-stu-id="8281f-130">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="8281f-131">Los literales NULL en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se consideran compatibles con todos los demás tipos del modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="8281f-131">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="8281f-132">Constructores de tipos</span><span class="sxs-lookup"><span data-stu-id="8281f-132">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="8281f-133">ROW</span><span class="sxs-lookup"><span data-stu-id="8281f-133">ROW</span></span>  

 <span data-ttu-id="8281f-134">La [fila](row-entity-sql.md) construye un valor anónimo, con tipo estructural (registro) como en:`ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="8281f-134">[ROW](row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="8281f-135">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-135">Example:</span></span>  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 <span data-ttu-id="8281f-136">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-136">Output:</span></span>  
  
|<span data-ttu-id="8281f-137">ProductID</span><span class="sxs-lookup"><span data-stu-id="8281f-137">ProductID</span></span>|<span data-ttu-id="8281f-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="8281f-138">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="8281f-139">1</span><span class="sxs-lookup"><span data-stu-id="8281f-139">1</span></span>|<span data-ttu-id="8281f-140">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="8281f-140">Adjustable Race</span></span>|  
|<span data-ttu-id="8281f-141">879</span><span class="sxs-lookup"><span data-stu-id="8281f-141">879</span></span>|<span data-ttu-id="8281f-142">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="8281f-142">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="8281f-143">712</span><span class="sxs-lookup"><span data-stu-id="8281f-143">712</span></span>|<span data-ttu-id="8281f-144">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="8281f-144">AWC Logo Cap</span></span>|  
|<span data-ttu-id="8281f-145">...</span><span class="sxs-lookup"><span data-stu-id="8281f-145">...</span></span>|<span data-ttu-id="8281f-146">...</span><span class="sxs-lookup"><span data-stu-id="8281f-146">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="8281f-147">MULTISET</span><span class="sxs-lookup"><span data-stu-id="8281f-147">MULTISET</span></span>  

 <span data-ttu-id="8281f-148">Las construcciones de conjuntos [MultiSet](multiset-entity-sql.md) , como:</span><span class="sxs-lookup"><span data-stu-id="8281f-148">[MULTISET](multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="8281f-149">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="8281f-149">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="8281f-150">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-150">Example:</span></span>  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="8281f-151">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-151">Output:</span></span>  
  
|<span data-ttu-id="8281f-152">ProductID</span><span class="sxs-lookup"><span data-stu-id="8281f-152">ProductID</span></span>|<span data-ttu-id="8281f-153">Nombre</span><span class="sxs-lookup"><span data-stu-id="8281f-153">Name</span></span>|<span data-ttu-id="8281f-154">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="8281f-154">ProductNumber</span></span>|<span data-ttu-id="8281f-155">…</span><span class="sxs-lookup"><span data-stu-id="8281f-155">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="8281f-156">842</span><span class="sxs-lookup"><span data-stu-id="8281f-156">842</span></span>|<span data-ttu-id="8281f-157">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="8281f-157">Touring-Panniers, Large</span></span>|<span data-ttu-id="8281f-158">PA-T100</span><span class="sxs-lookup"><span data-stu-id="8281f-158">PA-T100</span></span>|<span data-ttu-id="8281f-159">…</span><span class="sxs-lookup"><span data-stu-id="8281f-159">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="8281f-160">Object</span><span class="sxs-lookup"><span data-stu-id="8281f-160">Object</span></span>  

 <span data-ttu-id="8281f-161">El [constructor de tipo con nombre](named-type-constructor-entity-sql.md) crea objetos definidos por el usuario (con nombre), como `person("abc", 12)` .</span><span class="sxs-lookup"><span data-stu-id="8281f-161">[Named Type Constructor](named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="8281f-162">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-162">Example:</span></span>  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail
AS o  
```  
  
 <span data-ttu-id="8281f-163">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-163">Output:</span></span>  
  
|<span data-ttu-id="8281f-164">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="8281f-164">SalesOrderDetailID</span></span>|<span data-ttu-id="8281f-165">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="8281f-165">CarrierTrackingNumber</span></span>|<span data-ttu-id="8281f-166">OrderQty</span><span class="sxs-lookup"><span data-stu-id="8281f-166">OrderQty</span></span>|<span data-ttu-id="8281f-167">ProductID</span><span class="sxs-lookup"><span data-stu-id="8281f-167">ProductID</span></span>|<span data-ttu-id="8281f-168">...</span><span class="sxs-lookup"><span data-stu-id="8281f-168">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="8281f-169">1</span><span class="sxs-lookup"><span data-stu-id="8281f-169">1</span></span>|<span data-ttu-id="8281f-170">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="8281f-170">4911-403C-98</span></span>|<span data-ttu-id="8281f-171">1</span><span class="sxs-lookup"><span data-stu-id="8281f-171">1</span></span>|<span data-ttu-id="8281f-172">776</span><span class="sxs-lookup"><span data-stu-id="8281f-172">776</span></span>|<span data-ttu-id="8281f-173">...</span><span class="sxs-lookup"><span data-stu-id="8281f-173">...</span></span>|  
|<span data-ttu-id="8281f-174">2</span><span class="sxs-lookup"><span data-stu-id="8281f-174">2</span></span>|<span data-ttu-id="8281f-175">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="8281f-175">4911-403C-98</span></span>|<span data-ttu-id="8281f-176">3</span><span class="sxs-lookup"><span data-stu-id="8281f-176">3</span></span>|<span data-ttu-id="8281f-177">777</span><span class="sxs-lookup"><span data-stu-id="8281f-177">777</span></span>|<span data-ttu-id="8281f-178">...</span><span class="sxs-lookup"><span data-stu-id="8281f-178">...</span></span>|  
|<span data-ttu-id="8281f-179">...</span><span class="sxs-lookup"><span data-stu-id="8281f-179">...</span></span>|<span data-ttu-id="8281f-180">...</span><span class="sxs-lookup"><span data-stu-id="8281f-180">...</span></span>|<span data-ttu-id="8281f-181">...</span><span class="sxs-lookup"><span data-stu-id="8281f-181">...</span></span>|<span data-ttu-id="8281f-182">...</span><span class="sxs-lookup"><span data-stu-id="8281f-182">...</span></span>|<span data-ttu-id="8281f-183">...</span><span class="sxs-lookup"><span data-stu-id="8281f-183">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="8281f-184">Referencias</span><span class="sxs-lookup"><span data-stu-id="8281f-184">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="8281f-185">REF</span><span class="sxs-lookup"><span data-stu-id="8281f-185">REF</span></span>  

 <span data-ttu-id="8281f-186">[Ref](ref-entity-sql.md) crea una referencia a una instancia de tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="8281f-186">[REF](ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="8281f-187">Por ejemplo, la consulta siguiente devuelve referencias a cada entidad Order en el conjunto de entidades Orders:</span><span class="sxs-lookup"><span data-stu-id="8281f-187">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="8281f-188">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-188">Output:</span></span>  
  
|<span data-ttu-id="8281f-189">Value</span><span class="sxs-lookup"><span data-stu-id="8281f-189">Value</span></span>|  
|-----------|  
|<span data-ttu-id="8281f-190">1</span><span class="sxs-lookup"><span data-stu-id="8281f-190">1</span></span>|  
|<span data-ttu-id="8281f-191">2</span><span class="sxs-lookup"><span data-stu-id="8281f-191">2</span></span>|  
|<span data-ttu-id="8281f-192">3</span><span class="sxs-lookup"><span data-stu-id="8281f-192">3</span></span>|  
|<span data-ttu-id="8281f-193">...</span><span class="sxs-lookup"><span data-stu-id="8281f-193">...</span></span>|  
  
 <span data-ttu-id="8281f-194">En el ejemplo siguiente se usa el operador de extracción de propiedades (.) para tener acceso a una propiedad de una entidad.</span><span class="sxs-lookup"><span data-stu-id="8281f-194">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="8281f-195">Cuando se utiliza el operador de extracción de propiedades, la referencia se desreferencia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8281f-195">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="8281f-196">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-196">Example:</span></span>  
  
```sql  
SELECT VALUE REF(p).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="8281f-197">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-197">Output:</span></span>  
  
|<span data-ttu-id="8281f-198">Value</span><span class="sxs-lookup"><span data-stu-id="8281f-198">Value</span></span>|  
|-----------|  
|<span data-ttu-id="8281f-199">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="8281f-199">Adjustable Race</span></span>|  
|<span data-ttu-id="8281f-200">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="8281f-200">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="8281f-201">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="8281f-201">AWC Logo Cap</span></span>|  
|<span data-ttu-id="8281f-202">...</span><span class="sxs-lookup"><span data-stu-id="8281f-202">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="8281f-203">DEREF</span><span class="sxs-lookup"><span data-stu-id="8281f-203">DEREF</span></span>  

 <span data-ttu-id="8281f-204">[Deref](deref-entity-sql.md) desreferencia un valor de referencia y genera el resultado de dicha desreferenciación.</span><span class="sxs-lookup"><span data-stu-id="8281f-204">[DEREF](deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="8281f-205">Por ejemplo, la consulta siguiente genera las entidades Order para cada entidad Order en el conjunto de entidades Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.</span><span class="sxs-lookup"><span data-stu-id="8281f-205">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="8281f-206">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-206">Example:</span></span>  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="8281f-207">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-207">Output:</span></span>  
  
|<span data-ttu-id="8281f-208">Value</span><span class="sxs-lookup"><span data-stu-id="8281f-208">Value</span></span>|  
|-----------|  
|<span data-ttu-id="8281f-209">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="8281f-209">Adjustable Race</span></span>|  
|<span data-ttu-id="8281f-210">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="8281f-210">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="8281f-211">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="8281f-211">AWC Logo Cap</span></span>|  
|<span data-ttu-id="8281f-212">...</span><span class="sxs-lookup"><span data-stu-id="8281f-212">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="8281f-213">CREATEREF y KEY</span><span class="sxs-lookup"><span data-stu-id="8281f-213">CREATEREF AND KEY</span></span>  

 <span data-ttu-id="8281f-214">[CREATEREF](createref-entity-sql.md) crea una referencia que pasa una clave.</span><span class="sxs-lookup"><span data-stu-id="8281f-214">[CREATEREF](createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="8281f-215">La [clave](key-entity-sql.md) extrae la parte de la clave de una expresión con referencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="8281f-215">[KEY](key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="8281f-216">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-216">Example:</span></span>  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))
    FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="8281f-217">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-217">Output:</span></span>  
  
|<span data-ttu-id="8281f-218">ProductID</span><span class="sxs-lookup"><span data-stu-id="8281f-218">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="8281f-219">980</span><span class="sxs-lookup"><span data-stu-id="8281f-219">980</span></span>|  
|<span data-ttu-id="8281f-220">365</span><span class="sxs-lookup"><span data-stu-id="8281f-220">365</span></span>|  
|<span data-ttu-id="8281f-221">771</span><span class="sxs-lookup"><span data-stu-id="8281f-221">771</span></span>|  
|<span data-ttu-id="8281f-222">...</span><span class="sxs-lookup"><span data-stu-id="8281f-222">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="8281f-223">Functions</span><span class="sxs-lookup"><span data-stu-id="8281f-223">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="8281f-224">Canonical</span><span class="sxs-lookup"><span data-stu-id="8281f-224">Canonical</span></span>  

 <span data-ttu-id="8281f-225">El espacio de nombres para [las funciones canónicas](canonical-functions.md) es EDM, como en `Edm.Length("string")` .</span><span class="sxs-lookup"><span data-stu-id="8281f-225">The namespace for [canonical functions](canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="8281f-226">No es necesario especificar el espacio de nombres a no ser que se importe otro espacio de nombres que contenga una función con el mismo nombre que una función canónica.</span><span class="sxs-lookup"><span data-stu-id="8281f-226">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="8281f-227">Si dos espacios de nombres tienen la misma función, el usuario debe especificar el nombre completo.</span><span class="sxs-lookup"><span data-stu-id="8281f-227">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="8281f-228">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-228">Example:</span></span>  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="8281f-229">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-229">Output:</span></span>  
  
|<span data-ttu-id="8281f-230">NameLen</span><span class="sxs-lookup"><span data-stu-id="8281f-230">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="8281f-231">6</span><span class="sxs-lookup"><span data-stu-id="8281f-231">6</span></span>|  
|<span data-ttu-id="8281f-232">6</span><span class="sxs-lookup"><span data-stu-id="8281f-232">6</span></span>|  
|<span data-ttu-id="8281f-233">5</span><span class="sxs-lookup"><span data-stu-id="8281f-233">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="8281f-234">Específicas de proveedores de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8281f-234">Microsoft Provider-Specific</span></span>  

 <span data-ttu-id="8281f-235">[Las funciones específicas del proveedor de Microsoft](../sqlclient-for-ef-functions.md) se encuentran en el `SqlServer` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="8281f-235">[Microsoft provider-specific functions](../sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="8281f-236">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-236">Example:</span></span>  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="8281f-237">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-237">Output:</span></span>  
  
|<span data-ttu-id="8281f-238">EmailLen</span><span class="sxs-lookup"><span data-stu-id="8281f-238">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="8281f-239">27</span><span class="sxs-lookup"><span data-stu-id="8281f-239">27</span></span>|  
|<span data-ttu-id="8281f-240">27</span><span class="sxs-lookup"><span data-stu-id="8281f-240">27</span></span>|  
|<span data-ttu-id="8281f-241">26</span><span class="sxs-lookup"><span data-stu-id="8281f-241">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="8281f-242">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="8281f-242">Namespaces</span></span>  

 <span data-ttu-id="8281f-243">El [uso](using-entity-sql.md) de especifica espacios de nombres utilizados en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="8281f-243">[USING](using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="8281f-244">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-244">Example:</span></span>  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="8281f-245">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-245">Output:</span></span>  
  
|<span data-ttu-id="8281f-246">Value</span><span class="sxs-lookup"><span data-stu-id="8281f-246">Value</span></span>|  
|-----------|  
|<span data-ttu-id="8281f-247">aa</span><span class="sxs-lookup"><span data-stu-id="8281f-247">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="8281f-248">Paginación</span><span class="sxs-lookup"><span data-stu-id="8281f-248">Paging</span></span>  

 <span data-ttu-id="8281f-249">La paginación se puede expresar declarando una cláusula [SKIP](skip-entity-sql.md) y [Limit](limit-entity-sql.md) en la cláusula [order by](order-by-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="8281f-249">Paging can be expressed by declaring a [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses to the [ORDER BY](order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="8281f-250">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-250">Example:</span></span>  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="8281f-251">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-251">Output:</span></span>  
  
|<span data-ttu-id="8281f-252">ID</span><span class="sxs-lookup"><span data-stu-id="8281f-252">ID</span></span>|<span data-ttu-id="8281f-253">Nombre</span><span class="sxs-lookup"><span data-stu-id="8281f-253">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="8281f-254">10</span><span class="sxs-lookup"><span data-stu-id="8281f-254">10</span></span>|<span data-ttu-id="8281f-255">Adina</span><span class="sxs-lookup"><span data-stu-id="8281f-255">Adina</span></span>|  
|<span data-ttu-id="8281f-256">11</span><span class="sxs-lookup"><span data-stu-id="8281f-256">11</span></span>|<span data-ttu-id="8281f-257">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="8281f-257">Agcaoili</span></span>|  
|<span data-ttu-id="8281f-258">12</span><span class="sxs-lookup"><span data-stu-id="8281f-258">12</span></span>|<span data-ttu-id="8281f-259">Aguilar</span><span class="sxs-lookup"><span data-stu-id="8281f-259">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="8281f-260">Agrupar</span><span class="sxs-lookup"><span data-stu-id="8281f-260">Grouping</span></span>  

 <span data-ttu-id="8281f-261">La [agrupación por](group-by-entity-sql.md) especifica los grupos en los que se van a colocar los objetos devueltos por una expresión de consulta ([Select](select-entity-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="8281f-261">[GROUPING BY](group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="8281f-262">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-262">Example:</span></span>  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="8281f-263">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-263">Output:</span></span>  
  
|<span data-ttu-id="8281f-264">name</span><span class="sxs-lookup"><span data-stu-id="8281f-264">name</span></span>|  
|----------|  
|<span data-ttu-id="8281f-265">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="8281f-265">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="8281f-266">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="8281f-266">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="8281f-267">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="8281f-267">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="8281f-268">...</span><span class="sxs-lookup"><span data-stu-id="8281f-268">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="8281f-269">Navegación</span><span class="sxs-lookup"><span data-stu-id="8281f-269">Navigation</span></span>  

 <span data-ttu-id="8281f-270">El operador de navegación por relaciones permite navegar por la relación de un tipo de entidad (extremo inicial) a otro (extremo final).</span><span class="sxs-lookup"><span data-stu-id="8281f-270">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="8281f-271">[Navigate](navigate-entity-sql.md) toma el tipo de relación calificado como \<namespace> . \<relationship type name> .</span><span class="sxs-lookup"><span data-stu-id="8281f-271">[NAVIGATE](navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="8281f-272">Navigate devuelve Ref \<T> si la cardinalidad del extremo final es 1.</span><span class="sxs-lookup"><span data-stu-id="8281f-272">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="8281f-273">Si la cardinalidad del extremo final es n, se devolverá la colección<> de referencia \<T> .</span><span class="sxs-lookup"><span data-stu-id="8281f-273">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="8281f-274">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-274">Example:</span></span>  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="8281f-275">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-275">Output:</span></span>  
  
|<span data-ttu-id="8281f-276">AddressID</span><span class="sxs-lookup"><span data-stu-id="8281f-276">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="8281f-277">1</span><span class="sxs-lookup"><span data-stu-id="8281f-277">1</span></span>|  
|<span data-ttu-id="8281f-278">2</span><span class="sxs-lookup"><span data-stu-id="8281f-278">2</span></span>|  
|<span data-ttu-id="8281f-279">3</span><span class="sxs-lookup"><span data-stu-id="8281f-279">3</span></span>|  
|<span data-ttu-id="8281f-280">...</span><span class="sxs-lookup"><span data-stu-id="8281f-280">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="8281f-281">SELECT VALUE y SELECT</span><span class="sxs-lookup"><span data-stu-id="8281f-281">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="8281f-282">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="8281f-282">SELECT VALUE</span></span>  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="8281f-283">proporciona la cláusula SELECT VALUE para omitir la creación de filas implícitas.</span><span class="sxs-lookup"><span data-stu-id="8281f-283">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="8281f-284">Solo se puede especificar un elemento en una cláusula SELECT VALUE.</span><span class="sxs-lookup"><span data-stu-id="8281f-284">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="8281f-285">Cuando se utiliza este tipo de cláusula, no se crea ningún contenedor de filas en torno a los elementos de la cláusula SELECT y se puede generar una colección de la forma deseada, por ejemplo: `SELECT VALUE a` .</span><span class="sxs-lookup"><span data-stu-id="8281f-285">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="8281f-286">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-286">Example:</span></span>  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="8281f-287">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-287">Output:</span></span>  
  
|<span data-ttu-id="8281f-288">Nombre</span><span class="sxs-lookup"><span data-stu-id="8281f-288">Name</span></span>|  
|----------|  
|<span data-ttu-id="8281f-289">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="8281f-289">Adjustable Race</span></span>|  
|<span data-ttu-id="8281f-290">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="8281f-290">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="8281f-291">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="8281f-291">AWC Logo Cap</span></span>|  
|<span data-ttu-id="8281f-292">...</span><span class="sxs-lookup"><span data-stu-id="8281f-292">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="8281f-293">SELECT</span><span class="sxs-lookup"><span data-stu-id="8281f-293">SELECT</span></span>  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="8281f-294">también proporciona el constructor de filas para crear filas arbitrarias.</span><span class="sxs-lookup"><span data-stu-id="8281f-294">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="8281f-295">SELECT toma uno o más elementos en la proyección y devuelve un registro de datos con campos, por ejemplo: `SELECT a, b, c`.</span><span class="sxs-lookup"><span data-stu-id="8281f-295">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="8281f-296">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-296">Example:</span></span>  
  
 <span data-ttu-id="8281f-297">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="8281f-297">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="8281f-298">Nombre</span><span class="sxs-lookup"><span data-stu-id="8281f-298">Name</span></span>|<span data-ttu-id="8281f-299">ProductID</span><span class="sxs-lookup"><span data-stu-id="8281f-299">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="8281f-300">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="8281f-300">Adjustable Race</span></span>|<span data-ttu-id="8281f-301">1</span><span class="sxs-lookup"><span data-stu-id="8281f-301">1</span></span>|  
|<span data-ttu-id="8281f-302">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="8281f-302">All-Purpose Bike Stand</span></span>|<span data-ttu-id="8281f-303">879</span><span class="sxs-lookup"><span data-stu-id="8281f-303">879</span></span>|  
|<span data-ttu-id="8281f-304">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="8281f-304">AWC Logo Cap</span></span>|<span data-ttu-id="8281f-305">712</span><span class="sxs-lookup"><span data-stu-id="8281f-305">712</span></span>|  
|<span data-ttu-id="8281f-306">...</span><span class="sxs-lookup"><span data-stu-id="8281f-306">...</span></span>|<span data-ttu-id="8281f-307">...</span><span class="sxs-lookup"><span data-stu-id="8281f-307">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="8281f-308">EXPRESIÓN CASE</span><span class="sxs-lookup"><span data-stu-id="8281f-308">CASE EXPRESSION</span></span>  

 <span data-ttu-id="8281f-309">La [expresión Case](case-entity-sql.md) evalúa un conjunto de Expresiones booleanas para determinar el resultado.</span><span class="sxs-lookup"><span data-stu-id="8281f-309">The [case expression](case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="8281f-310">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8281f-310">Example:</span></span>  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="8281f-311">Salida:</span><span class="sxs-lookup"><span data-stu-id="8281f-311">Output:</span></span>  
  
|<span data-ttu-id="8281f-312">Value</span><span class="sxs-lookup"><span data-stu-id="8281f-312">Value</span></span>|  
|-----------|  
|<span data-ttu-id="8281f-313">true</span><span class="sxs-lookup"><span data-stu-id="8281f-313">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8281f-314">Vea también</span><span class="sxs-lookup"><span data-stu-id="8281f-314">See also</span></span>

- [<span data-ttu-id="8281f-315">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8281f-315">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="8281f-316">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8281f-316">Entity SQL Overview</span></span>](entity-sql-overview.md)
