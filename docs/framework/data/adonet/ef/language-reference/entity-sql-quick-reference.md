---
title: Referencia rápida de Entity SQL
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: fc7cf8f8f692f9dc4230569d5f575b6d5fad19fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150355"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="27b56-102">Referencia rápida de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="27b56-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="27b56-103">Este tema proporciona una referencia rápida a las consultas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27b56-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="27b56-104">Las consultas de este tema se basan en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="27b56-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="27b56-105">Literales</span><span class="sxs-lookup"><span data-stu-id="27b56-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="27b56-106">String</span><span class="sxs-lookup"><span data-stu-id="27b56-106">String</span></span>  
 <span data-ttu-id="27b56-107">Hay literales de cadenas de caracteres Unicode y no Unicode.</span><span class="sxs-lookup"><span data-stu-id="27b56-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="27b56-108">Las cadenas Unicode se antetienen con N. Por ejemplo, `N'hello'`.</span><span class="sxs-lookup"><span data-stu-id="27b56-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="27b56-109">A continuación se incluye un ejemplo de un literal de cadena no Unicode:</span><span class="sxs-lookup"><span data-stu-id="27b56-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="27b56-110">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-110">Output:</span></span>  
  
|<span data-ttu-id="27b56-111">Value</span><span class="sxs-lookup"><span data-stu-id="27b56-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="27b56-112">hello</span><span class="sxs-lookup"><span data-stu-id="27b56-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="27b56-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="27b56-113">DateTime</span></span>  
 <span data-ttu-id="27b56-114">En los literales DateTime, las partes de fecha y hora son obligatorias.</span><span class="sxs-lookup"><span data-stu-id="27b56-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="27b56-115">No hay valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="27b56-115">There are no default values.</span></span>  
  
 <span data-ttu-id="27b56-116">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-116">Example:</span></span>  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="27b56-117">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-117">Output:</span></span>  
  
|<span data-ttu-id="27b56-118">Value</span><span class="sxs-lookup"><span data-stu-id="27b56-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="27b56-119">25.12.06 01:01:00</span><span class="sxs-lookup"><span data-stu-id="27b56-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="27b56-120">Entero</span><span class="sxs-lookup"><span data-stu-id="27b56-120">Integer</span></span>  
 <span data-ttu-id="27b56-121">Los literales enteros pueden ser de tipo Int32 (123), UInt32 (123U), Int64 (123L) y UInt64 (123UL).</span><span class="sxs-lookup"><span data-stu-id="27b56-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="27b56-122">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-122">Example:</span></span>  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="27b56-123">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-123">Output:</span></span>  
  
|<span data-ttu-id="27b56-124">Value</span><span class="sxs-lookup"><span data-stu-id="27b56-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="27b56-125">1</span><span class="sxs-lookup"><span data-stu-id="27b56-125">1</span></span>|  
|<span data-ttu-id="27b56-126">2</span><span class="sxs-lookup"><span data-stu-id="27b56-126">2</span></span>|  
|<span data-ttu-id="27b56-127">3</span><span class="sxs-lookup"><span data-stu-id="27b56-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="27b56-128">Otros</span><span class="sxs-lookup"><span data-stu-id="27b56-128">Other</span></span>  
 <span data-ttu-id="27b56-129">Los literales Other admitidos por [!INCLUDE[esql](../../../../../../includes/esql-md.md)] son Guid, Binary, Float/Double, Decimal y `null`.</span><span class="sxs-lookup"><span data-stu-id="27b56-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="27b56-130">Los literales NULL en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se consideran compatibles con todos los demás tipos del modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="27b56-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="27b56-131">Constructores de tipos</span><span class="sxs-lookup"><span data-stu-id="27b56-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="27b56-132">ROW</span><span class="sxs-lookup"><span data-stu-id="27b56-132">ROW</span></span>  
 <span data-ttu-id="27b56-133">[ROW](row-entity-sql.md) construye un valor anónimo de tipo estructural (registro) como en:`ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="27b56-133">[ROW](row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="27b56-134">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-134">Example:</span></span>  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 <span data-ttu-id="27b56-135">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-135">Output:</span></span>  
  
|<span data-ttu-id="27b56-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="27b56-136">ProductID</span></span>|<span data-ttu-id="27b56-137">Nombre</span><span class="sxs-lookup"><span data-stu-id="27b56-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="27b56-138">1</span><span class="sxs-lookup"><span data-stu-id="27b56-138">1</span></span>|<span data-ttu-id="27b56-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="27b56-139">Adjustable Race</span></span>|  
|<span data-ttu-id="27b56-140">879</span><span class="sxs-lookup"><span data-stu-id="27b56-140">879</span></span>|<span data-ttu-id="27b56-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="27b56-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="27b56-142">712</span><span class="sxs-lookup"><span data-stu-id="27b56-142">712</span></span>|<span data-ttu-id="27b56-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="27b56-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="27b56-144">...</span><span class="sxs-lookup"><span data-stu-id="27b56-144">...</span></span>|<span data-ttu-id="27b56-145">...</span><span class="sxs-lookup"><span data-stu-id="27b56-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="27b56-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="27b56-146">MULTISET</span></span>  
 <span data-ttu-id="27b56-147">[MULTISET](multiset-entity-sql.md) construye colecciones, tales como:</span><span class="sxs-lookup"><span data-stu-id="27b56-147">[MULTISET](multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="27b56-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="27b56-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="27b56-149">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-149">Example:</span></span>  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="27b56-150">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-150">Output:</span></span>  
  
|<span data-ttu-id="27b56-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="27b56-151">ProductID</span></span>|<span data-ttu-id="27b56-152">Nombre</span><span class="sxs-lookup"><span data-stu-id="27b56-152">Name</span></span>|<span data-ttu-id="27b56-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="27b56-153">ProductNumber</span></span>|<span data-ttu-id="27b56-154">…</span><span class="sxs-lookup"><span data-stu-id="27b56-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="27b56-155">842</span><span class="sxs-lookup"><span data-stu-id="27b56-155">842</span></span>|<span data-ttu-id="27b56-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="27b56-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="27b56-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="27b56-157">PA-T100</span></span>|<span data-ttu-id="27b56-158">…</span><span class="sxs-lookup"><span data-stu-id="27b56-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="27b56-159">Object</span><span class="sxs-lookup"><span data-stu-id="27b56-159">Object</span></span>  
 <span data-ttu-id="27b56-160">[El constructor](named-type-constructor-entity-sql.md) de tipos con nombre construye (con nombre) objetos definidos por el usuario, como `person("abc", 12)`.</span><span class="sxs-lookup"><span data-stu-id="27b56-160">[Named Type Constructor](named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="27b56-161">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-161">Example:</span></span>  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail
AS o  
```  
  
 <span data-ttu-id="27b56-162">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-162">Output:</span></span>  
  
|<span data-ttu-id="27b56-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="27b56-163">SalesOrderDetailID</span></span>|<span data-ttu-id="27b56-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="27b56-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="27b56-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="27b56-165">OrderQty</span></span>|<span data-ttu-id="27b56-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="27b56-166">ProductID</span></span>|<span data-ttu-id="27b56-167">...</span><span class="sxs-lookup"><span data-stu-id="27b56-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="27b56-168">1</span><span class="sxs-lookup"><span data-stu-id="27b56-168">1</span></span>|<span data-ttu-id="27b56-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="27b56-169">4911-403C-98</span></span>|<span data-ttu-id="27b56-170">1</span><span class="sxs-lookup"><span data-stu-id="27b56-170">1</span></span>|<span data-ttu-id="27b56-171">776</span><span class="sxs-lookup"><span data-stu-id="27b56-171">776</span></span>|<span data-ttu-id="27b56-172">...</span><span class="sxs-lookup"><span data-stu-id="27b56-172">...</span></span>|  
|<span data-ttu-id="27b56-173">2</span><span class="sxs-lookup"><span data-stu-id="27b56-173">2</span></span>|<span data-ttu-id="27b56-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="27b56-174">4911-403C-98</span></span>|<span data-ttu-id="27b56-175">3</span><span class="sxs-lookup"><span data-stu-id="27b56-175">3</span></span>|<span data-ttu-id="27b56-176">777</span><span class="sxs-lookup"><span data-stu-id="27b56-176">777</span></span>|<span data-ttu-id="27b56-177">...</span><span class="sxs-lookup"><span data-stu-id="27b56-177">...</span></span>|  
|<span data-ttu-id="27b56-178">...</span><span class="sxs-lookup"><span data-stu-id="27b56-178">...</span></span>|<span data-ttu-id="27b56-179">...</span><span class="sxs-lookup"><span data-stu-id="27b56-179">...</span></span>|<span data-ttu-id="27b56-180">...</span><span class="sxs-lookup"><span data-stu-id="27b56-180">...</span></span>|<span data-ttu-id="27b56-181">...</span><span class="sxs-lookup"><span data-stu-id="27b56-181">...</span></span>|<span data-ttu-id="27b56-182">...</span><span class="sxs-lookup"><span data-stu-id="27b56-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="27b56-183">Referencias</span><span class="sxs-lookup"><span data-stu-id="27b56-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="27b56-184">REF</span><span class="sxs-lookup"><span data-stu-id="27b56-184">REF</span></span>  
 <span data-ttu-id="27b56-185">[REF](ref-entity-sql.md) crea una referencia a una instancia de tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="27b56-185">[REF](ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="27b56-186">Por ejemplo, la consulta siguiente devuelve referencias a cada entidad Order en el conjunto de entidades Orders:</span><span class="sxs-lookup"><span data-stu-id="27b56-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="27b56-187">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-187">Output:</span></span>  
  
|<span data-ttu-id="27b56-188">Value</span><span class="sxs-lookup"><span data-stu-id="27b56-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="27b56-189">1</span><span class="sxs-lookup"><span data-stu-id="27b56-189">1</span></span>|  
|<span data-ttu-id="27b56-190">2</span><span class="sxs-lookup"><span data-stu-id="27b56-190">2</span></span>|  
|<span data-ttu-id="27b56-191">3</span><span class="sxs-lookup"><span data-stu-id="27b56-191">3</span></span>|  
|<span data-ttu-id="27b56-192">...</span><span class="sxs-lookup"><span data-stu-id="27b56-192">...</span></span>|  
  
 <span data-ttu-id="27b56-193">En el ejemplo siguiente se usa el operador de extracción de propiedades (.) para tener acceso a una propiedad de una entidad.</span><span class="sxs-lookup"><span data-stu-id="27b56-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="27b56-194">Cuando se utiliza el operador de extracción de propiedades, la referencia se desreferencia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="27b56-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="27b56-195">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-195">Example:</span></span>  
  
```sql  
SELECT VALUE REF(p).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="27b56-196">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-196">Output:</span></span>  
  
|<span data-ttu-id="27b56-197">Value</span><span class="sxs-lookup"><span data-stu-id="27b56-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="27b56-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="27b56-198">Adjustable Race</span></span>|  
|<span data-ttu-id="27b56-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="27b56-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="27b56-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="27b56-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="27b56-201">...</span><span class="sxs-lookup"><span data-stu-id="27b56-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="27b56-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="27b56-202">DEREF</span></span>  
 <span data-ttu-id="27b56-203">[DEREF](deref-entity-sql.md) desreferencia un valor de referencia y produce el resultado de esa desreferencia.</span><span class="sxs-lookup"><span data-stu-id="27b56-203">[DEREF](deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="27b56-204">Por ejemplo, la consulta siguiente genera las entidades Order para cada entidad Order en el conjunto de entidades Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.</span><span class="sxs-lookup"><span data-stu-id="27b56-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="27b56-205">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-205">Example:</span></span>  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="27b56-206">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-206">Output:</span></span>  
  
|<span data-ttu-id="27b56-207">Value</span><span class="sxs-lookup"><span data-stu-id="27b56-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="27b56-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="27b56-208">Adjustable Race</span></span>|  
|<span data-ttu-id="27b56-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="27b56-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="27b56-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="27b56-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="27b56-211">...</span><span class="sxs-lookup"><span data-stu-id="27b56-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="27b56-212">CREATEREF y KEY</span><span class="sxs-lookup"><span data-stu-id="27b56-212">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="27b56-213">[CREATEREF](createref-entity-sql.md) crea una referencia pasando una clave.</span><span class="sxs-lookup"><span data-stu-id="27b56-213">[CREATEREF](createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="27b56-214">[KEY](key-entity-sql.md) extrae la parte clave de una expresión con referencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="27b56-214">[KEY](key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="27b56-215">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-215">Example:</span></span>  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))
    FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="27b56-216">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-216">Output:</span></span>  
  
|<span data-ttu-id="27b56-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="27b56-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="27b56-218">980</span><span class="sxs-lookup"><span data-stu-id="27b56-218">980</span></span>|  
|<span data-ttu-id="27b56-219">365</span><span class="sxs-lookup"><span data-stu-id="27b56-219">365</span></span>|  
|<span data-ttu-id="27b56-220">771</span><span class="sxs-lookup"><span data-stu-id="27b56-220">771</span></span>|  
|<span data-ttu-id="27b56-221">...</span><span class="sxs-lookup"><span data-stu-id="27b56-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="27b56-222">Functions</span><span class="sxs-lookup"><span data-stu-id="27b56-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="27b56-223">Canonical</span><span class="sxs-lookup"><span data-stu-id="27b56-223">Canonical</span></span>  
 <span data-ttu-id="27b56-224">El espacio de nombres para las `Edm.Length("string")` [funciones canónicas](canonical-functions.md) es Edm, como en .</span><span class="sxs-lookup"><span data-stu-id="27b56-224">The namespace for [canonical functions](canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="27b56-225">No es necesario especificar el espacio de nombres a no ser que se importe otro espacio de nombres que contenga una función con el mismo nombre que una función canónica.</span><span class="sxs-lookup"><span data-stu-id="27b56-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="27b56-226">Si dos espacios de nombres tienen la misma función, el usuario debe especificar el nombre completo.</span><span class="sxs-lookup"><span data-stu-id="27b56-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="27b56-227">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-227">Example:</span></span>  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="27b56-228">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-228">Output:</span></span>  
  
|<span data-ttu-id="27b56-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="27b56-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="27b56-230">6</span><span class="sxs-lookup"><span data-stu-id="27b56-230">6</span></span>|  
|<span data-ttu-id="27b56-231">6</span><span class="sxs-lookup"><span data-stu-id="27b56-231">6</span></span>|  
|<span data-ttu-id="27b56-232">5</span><span class="sxs-lookup"><span data-stu-id="27b56-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="27b56-233">Específicas de proveedores de Microsoft</span><span class="sxs-lookup"><span data-stu-id="27b56-233">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="27b56-234">Las [funciones específicas del proveedor de Microsoft](../sqlclient-for-ef-functions.md) se encuentran en el `SqlServer` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="27b56-234">[Microsoft provider-specific functions](../sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="27b56-235">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-235">Example:</span></span>  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="27b56-236">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-236">Output:</span></span>  
  
|<span data-ttu-id="27b56-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="27b56-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="27b56-238">27</span><span class="sxs-lookup"><span data-stu-id="27b56-238">27</span></span>|  
|<span data-ttu-id="27b56-239">27</span><span class="sxs-lookup"><span data-stu-id="27b56-239">27</span></span>|  
|<span data-ttu-id="27b56-240">26</span><span class="sxs-lookup"><span data-stu-id="27b56-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="27b56-241">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="27b56-241">Namespaces</span></span>  
 <span data-ttu-id="27b56-242">[USING](using-entity-sql.md) especifica los espacios de nombres utilizados en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="27b56-242">[USING](using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="27b56-243">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-243">Example:</span></span>  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="27b56-244">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-244">Output:</span></span>  
  
|<span data-ttu-id="27b56-245">Value</span><span class="sxs-lookup"><span data-stu-id="27b56-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="27b56-246">aa</span><span class="sxs-lookup"><span data-stu-id="27b56-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="27b56-247">Paginación</span><span class="sxs-lookup"><span data-stu-id="27b56-247">Paging</span></span>  
 <span data-ttu-id="27b56-248">La paginación se puede expresar declarando una subcláusula [SKIP](skip-entity-sql.md) y [LIMIT](limit-entity-sql.md) a la cláusula [ORDER BY.](order-by-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="27b56-248">Paging can be expressed by declaring a [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses to the [ORDER BY](order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="27b56-249">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-249">Example:</span></span>  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="27b56-250">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-250">Output:</span></span>  
  
|<span data-ttu-id="27b56-251">id</span><span class="sxs-lookup"><span data-stu-id="27b56-251">ID</span></span>|<span data-ttu-id="27b56-252">Nombre</span><span class="sxs-lookup"><span data-stu-id="27b56-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="27b56-253">10</span><span class="sxs-lookup"><span data-stu-id="27b56-253">10</span></span>|<span data-ttu-id="27b56-254">Adina</span><span class="sxs-lookup"><span data-stu-id="27b56-254">Adina</span></span>|  
|<span data-ttu-id="27b56-255">11</span><span class="sxs-lookup"><span data-stu-id="27b56-255">11</span></span>|<span data-ttu-id="27b56-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="27b56-256">Agcaoili</span></span>|  
|<span data-ttu-id="27b56-257">12</span><span class="sxs-lookup"><span data-stu-id="27b56-257">12</span></span>|<span data-ttu-id="27b56-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="27b56-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="27b56-259">Agrupación</span><span class="sxs-lookup"><span data-stu-id="27b56-259">Grouping</span></span>  
 <span data-ttu-id="27b56-260">[GROUPING BY](group-by-entity-sql.md) especifica los grupos en los que se van a colocar los objetos devueltos por una expresión de consulta ([SELECT](select-entity-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="27b56-260">[GROUPING BY](group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="27b56-261">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-261">Example:</span></span>  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="27b56-262">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-262">Output:</span></span>  
  
|<span data-ttu-id="27b56-263">name</span><span class="sxs-lookup"><span data-stu-id="27b56-263">name</span></span>|  
|----------|  
|<span data-ttu-id="27b56-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="27b56-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="27b56-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="27b56-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="27b56-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="27b56-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="27b56-267">...</span><span class="sxs-lookup"><span data-stu-id="27b56-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="27b56-268">Navegación</span><span class="sxs-lookup"><span data-stu-id="27b56-268">Navigation</span></span>  
 <span data-ttu-id="27b56-269">El operador de navegación por relaciones permite navegar por la relación de un tipo de entidad (extremo inicial) a otro (extremo final).</span><span class="sxs-lookup"><span data-stu-id="27b56-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="27b56-270">[NAVIGATE](navigate-entity-sql.md) toma el tipo \<de relación calificado como espacio de nombres>. \<nombre de tipo de relación>.</span><span class="sxs-lookup"><span data-stu-id="27b56-270">[NAVIGATE](navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="27b56-271">Navigate devuelve\<Ref T> si la cardinalidad del extremo es 1.</span><span class="sxs-lookup"><span data-stu-id="27b56-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="27b56-272">Si la cardinalidad del final es n,\<se devolverá la<de colección Ref T>> .</span><span class="sxs-lookup"><span data-stu-id="27b56-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="27b56-273">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-273">Example:</span></span>  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="27b56-274">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-274">Output:</span></span>  
  
|<span data-ttu-id="27b56-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="27b56-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="27b56-276">1</span><span class="sxs-lookup"><span data-stu-id="27b56-276">1</span></span>|  
|<span data-ttu-id="27b56-277">2</span><span class="sxs-lookup"><span data-stu-id="27b56-277">2</span></span>|  
|<span data-ttu-id="27b56-278">3</span><span class="sxs-lookup"><span data-stu-id="27b56-278">3</span></span>|  
|<span data-ttu-id="27b56-279">...</span><span class="sxs-lookup"><span data-stu-id="27b56-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="27b56-280">SELECT VALUE y SELECT</span><span class="sxs-lookup"><span data-stu-id="27b56-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="27b56-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="27b56-281">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="27b56-282">proporciona la cláusula SELECT VALUE para omitir la creación de filas implícitas.</span><span class="sxs-lookup"><span data-stu-id="27b56-282">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="27b56-283">Solo se puede especificar un elemento en una cláusula SELECT VALUE.</span><span class="sxs-lookup"><span data-stu-id="27b56-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="27b56-284">Cuando se utiliza una cláusula de este tipo, no se construye ningún contenedor de filas alrededor de los `SELECT VALUE a`elementos de la cláusula SELECT y se puede producir una colección de la forma deseada, por ejemplo: .</span><span class="sxs-lookup"><span data-stu-id="27b56-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="27b56-285">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-285">Example:</span></span>  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="27b56-286">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-286">Output:</span></span>  
  
|<span data-ttu-id="27b56-287">Nombre</span><span class="sxs-lookup"><span data-stu-id="27b56-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="27b56-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="27b56-288">Adjustable Race</span></span>|  
|<span data-ttu-id="27b56-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="27b56-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="27b56-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="27b56-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="27b56-291">...</span><span class="sxs-lookup"><span data-stu-id="27b56-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="27b56-292">SELECT</span><span class="sxs-lookup"><span data-stu-id="27b56-292">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="27b56-293">también proporciona el constructor de filas para crear filas arbitrarias.</span><span class="sxs-lookup"><span data-stu-id="27b56-293">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="27b56-294">SELECT toma uno o más elementos en la proyección y devuelve un registro de datos con campos, por ejemplo: `SELECT a, b, c`.</span><span class="sxs-lookup"><span data-stu-id="27b56-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="27b56-295">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-295">Example:</span></span>  
  
 <span data-ttu-id="27b56-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="27b56-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="27b56-297">Nombre</span><span class="sxs-lookup"><span data-stu-id="27b56-297">Name</span></span>|<span data-ttu-id="27b56-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="27b56-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="27b56-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="27b56-299">Adjustable Race</span></span>|<span data-ttu-id="27b56-300">1</span><span class="sxs-lookup"><span data-stu-id="27b56-300">1</span></span>|  
|<span data-ttu-id="27b56-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="27b56-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="27b56-302">879</span><span class="sxs-lookup"><span data-stu-id="27b56-302">879</span></span>|  
|<span data-ttu-id="27b56-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="27b56-303">AWC Logo Cap</span></span>|<span data-ttu-id="27b56-304">712</span><span class="sxs-lookup"><span data-stu-id="27b56-304">712</span></span>|  
|<span data-ttu-id="27b56-305">...</span><span class="sxs-lookup"><span data-stu-id="27b56-305">...</span></span>|<span data-ttu-id="27b56-306">...</span><span class="sxs-lookup"><span data-stu-id="27b56-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="27b56-307">EXPRESIÓN CASE</span><span class="sxs-lookup"><span data-stu-id="27b56-307">CASE EXPRESSION</span></span>  
 <span data-ttu-id="27b56-308">La [expresión case](case-entity-sql.md) evalúa un conjunto de expresiones booleanas para determinar el resultado.</span><span class="sxs-lookup"><span data-stu-id="27b56-308">The [case expression](case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="27b56-309">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27b56-309">Example:</span></span>  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="27b56-310">Salida:</span><span class="sxs-lookup"><span data-stu-id="27b56-310">Output:</span></span>  
  
|<span data-ttu-id="27b56-311">Value</span><span class="sxs-lookup"><span data-stu-id="27b56-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="27b56-312">TRUE</span><span class="sxs-lookup"><span data-stu-id="27b56-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27b56-313">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27b56-313">See also</span></span>

- [<span data-ttu-id="27b56-314">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="27b56-314">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="27b56-315">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="27b56-315">Entity SQL Overview</span></span>](entity-sql-overview.md)
