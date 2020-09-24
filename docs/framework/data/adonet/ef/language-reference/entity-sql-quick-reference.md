---
title: Referencia rápida de Entity SQL
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: 7ec3b6fc184b4f169d6f6489bda0ec8fa4abb4f5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148145"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="72b6e-102">Referencia rápida de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="72b6e-102">Entity SQL Quick Reference</span></span>

<span data-ttu-id="72b6e-103">Este tema proporciona una referencia rápida a las consultas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72b6e-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="72b6e-104">Las consultas de este tema se basan en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="72b6e-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="72b6e-105">Literales</span><span class="sxs-lookup"><span data-stu-id="72b6e-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="72b6e-106">String</span><span class="sxs-lookup"><span data-stu-id="72b6e-106">String</span></span>  

 <span data-ttu-id="72b6e-107">Hay literales de cadenas de caracteres Unicode y no Unicode.</span><span class="sxs-lookup"><span data-stu-id="72b6e-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="72b6e-108">Las cadenas Unicode se anteponen a N. Por ejemplo, `N'hello'` .</span><span class="sxs-lookup"><span data-stu-id="72b6e-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="72b6e-109">A continuación se incluye un ejemplo de un literal de cadena no Unicode:</span><span class="sxs-lookup"><span data-stu-id="72b6e-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="72b6e-110">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-110">Output:</span></span>  
  
|<span data-ttu-id="72b6e-111">Valor</span><span class="sxs-lookup"><span data-stu-id="72b6e-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="72b6e-112">hello</span><span class="sxs-lookup"><span data-stu-id="72b6e-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="72b6e-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="72b6e-113">DateTime</span></span>  

 <span data-ttu-id="72b6e-114">En los literales DateTime, las partes de fecha y hora son obligatorias.</span><span class="sxs-lookup"><span data-stu-id="72b6e-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="72b6e-115">No hay valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="72b6e-115">There are no default values.</span></span>  
  
 <span data-ttu-id="72b6e-116">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-116">Example:</span></span>  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="72b6e-117">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-117">Output:</span></span>  
  
|<span data-ttu-id="72b6e-118">Valor</span><span class="sxs-lookup"><span data-stu-id="72b6e-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="72b6e-119">25.12.06 01:01:00</span><span class="sxs-lookup"><span data-stu-id="72b6e-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="72b6e-120">Entero</span><span class="sxs-lookup"><span data-stu-id="72b6e-120">Integer</span></span>  

 <span data-ttu-id="72b6e-121">Los literales enteros pueden ser de tipo Int32 (123), UInt32 (123U), Int64 (123L) y UInt64 (123UL).</span><span class="sxs-lookup"><span data-stu-id="72b6e-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="72b6e-122">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-122">Example:</span></span>  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="72b6e-123">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-123">Output:</span></span>  
  
|<span data-ttu-id="72b6e-124">Valor</span><span class="sxs-lookup"><span data-stu-id="72b6e-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="72b6e-125">1</span><span class="sxs-lookup"><span data-stu-id="72b6e-125">1</span></span>|  
|<span data-ttu-id="72b6e-126">2</span><span class="sxs-lookup"><span data-stu-id="72b6e-126">2</span></span>|  
|<span data-ttu-id="72b6e-127">3</span><span class="sxs-lookup"><span data-stu-id="72b6e-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="72b6e-128">Otros</span><span class="sxs-lookup"><span data-stu-id="72b6e-128">Other</span></span>  

 <span data-ttu-id="72b6e-129">Los literales Other admitidos por [!INCLUDE[esql](../../../../../../includes/esql-md.md)] son Guid, Binary, Float/Double, Decimal y `null`.</span><span class="sxs-lookup"><span data-stu-id="72b6e-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="72b6e-130">Los literales NULL en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se consideran compatibles con todos los demás tipos del modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="72b6e-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="72b6e-131">Constructores de tipos</span><span class="sxs-lookup"><span data-stu-id="72b6e-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="72b6e-132">ROW</span><span class="sxs-lookup"><span data-stu-id="72b6e-132">ROW</span></span>  

 <span data-ttu-id="72b6e-133">La [fila](row-entity-sql.md) construye un valor anónimo, con tipo estructural (registro) como en:`ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="72b6e-133">[ROW](row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="72b6e-134">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-134">Example:</span></span>  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 <span data-ttu-id="72b6e-135">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-135">Output:</span></span>  
  
|<span data-ttu-id="72b6e-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="72b6e-136">ProductID</span></span>|<span data-ttu-id="72b6e-137">Nombre</span><span class="sxs-lookup"><span data-stu-id="72b6e-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="72b6e-138">1</span><span class="sxs-lookup"><span data-stu-id="72b6e-138">1</span></span>|<span data-ttu-id="72b6e-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="72b6e-139">Adjustable Race</span></span>|  
|<span data-ttu-id="72b6e-140">879</span><span class="sxs-lookup"><span data-stu-id="72b6e-140">879</span></span>|<span data-ttu-id="72b6e-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="72b6e-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="72b6e-142">712</span><span class="sxs-lookup"><span data-stu-id="72b6e-142">712</span></span>|<span data-ttu-id="72b6e-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="72b6e-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="72b6e-144">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-144">...</span></span>|<span data-ttu-id="72b6e-145">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="72b6e-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="72b6e-146">MULTISET</span></span>  

 <span data-ttu-id="72b6e-147">Las construcciones de conjuntos [MultiSet](multiset-entity-sql.md) , como:</span><span class="sxs-lookup"><span data-stu-id="72b6e-147">[MULTISET](multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="72b6e-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="72b6e-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="72b6e-149">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-149">Example:</span></span>  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="72b6e-150">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-150">Output:</span></span>  
  
|<span data-ttu-id="72b6e-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="72b6e-151">ProductID</span></span>|<span data-ttu-id="72b6e-152">Nombre</span><span class="sxs-lookup"><span data-stu-id="72b6e-152">Name</span></span>|<span data-ttu-id="72b6e-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="72b6e-153">ProductNumber</span></span>|<span data-ttu-id="72b6e-154">…</span><span class="sxs-lookup"><span data-stu-id="72b6e-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="72b6e-155">842</span><span class="sxs-lookup"><span data-stu-id="72b6e-155">842</span></span>|<span data-ttu-id="72b6e-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="72b6e-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="72b6e-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="72b6e-157">PA-T100</span></span>|<span data-ttu-id="72b6e-158">…</span><span class="sxs-lookup"><span data-stu-id="72b6e-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="72b6e-159">Objeto</span><span class="sxs-lookup"><span data-stu-id="72b6e-159">Object</span></span>  

 <span data-ttu-id="72b6e-160">El [constructor de tipo con nombre](named-type-constructor-entity-sql.md) crea objetos definidos por el usuario (con nombre), como `person("abc", 12)` .</span><span class="sxs-lookup"><span data-stu-id="72b6e-160">[Named Type Constructor](named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="72b6e-161">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-161">Example:</span></span>  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail
AS o  
```  
  
 <span data-ttu-id="72b6e-162">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-162">Output:</span></span>  
  
|<span data-ttu-id="72b6e-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="72b6e-163">SalesOrderDetailID</span></span>|<span data-ttu-id="72b6e-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="72b6e-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="72b6e-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="72b6e-165">OrderQty</span></span>|<span data-ttu-id="72b6e-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="72b6e-166">ProductID</span></span>|<span data-ttu-id="72b6e-167">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="72b6e-168">1</span><span class="sxs-lookup"><span data-stu-id="72b6e-168">1</span></span>|<span data-ttu-id="72b6e-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="72b6e-169">4911-403C-98</span></span>|<span data-ttu-id="72b6e-170">1</span><span class="sxs-lookup"><span data-stu-id="72b6e-170">1</span></span>|<span data-ttu-id="72b6e-171">776</span><span class="sxs-lookup"><span data-stu-id="72b6e-171">776</span></span>|<span data-ttu-id="72b6e-172">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-172">...</span></span>|  
|<span data-ttu-id="72b6e-173">2</span><span class="sxs-lookup"><span data-stu-id="72b6e-173">2</span></span>|<span data-ttu-id="72b6e-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="72b6e-174">4911-403C-98</span></span>|<span data-ttu-id="72b6e-175">3</span><span class="sxs-lookup"><span data-stu-id="72b6e-175">3</span></span>|<span data-ttu-id="72b6e-176">777</span><span class="sxs-lookup"><span data-stu-id="72b6e-176">777</span></span>|<span data-ttu-id="72b6e-177">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-177">...</span></span>|  
|<span data-ttu-id="72b6e-178">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-178">...</span></span>|<span data-ttu-id="72b6e-179">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-179">...</span></span>|<span data-ttu-id="72b6e-180">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-180">...</span></span>|<span data-ttu-id="72b6e-181">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-181">...</span></span>|<span data-ttu-id="72b6e-182">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="72b6e-183">Referencias</span><span class="sxs-lookup"><span data-stu-id="72b6e-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="72b6e-184">REF</span><span class="sxs-lookup"><span data-stu-id="72b6e-184">REF</span></span>  

 <span data-ttu-id="72b6e-185">[Ref](ref-entity-sql.md) crea una referencia a una instancia de tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="72b6e-185">[REF](ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="72b6e-186">Por ejemplo, la consulta siguiente devuelve referencias a cada entidad Order en el conjunto de entidades Orders:</span><span class="sxs-lookup"><span data-stu-id="72b6e-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="72b6e-187">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-187">Output:</span></span>  
  
|<span data-ttu-id="72b6e-188">Valor</span><span class="sxs-lookup"><span data-stu-id="72b6e-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="72b6e-189">1</span><span class="sxs-lookup"><span data-stu-id="72b6e-189">1</span></span>|  
|<span data-ttu-id="72b6e-190">2</span><span class="sxs-lookup"><span data-stu-id="72b6e-190">2</span></span>|  
|<span data-ttu-id="72b6e-191">3</span><span class="sxs-lookup"><span data-stu-id="72b6e-191">3</span></span>|  
|<span data-ttu-id="72b6e-192">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-192">...</span></span>|  
  
 <span data-ttu-id="72b6e-193">En el ejemplo siguiente se usa el operador de extracción de propiedades (.) para tener acceso a una propiedad de una entidad.</span><span class="sxs-lookup"><span data-stu-id="72b6e-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="72b6e-194">Cuando se utiliza el operador de extracción de propiedades, la referencia se desreferencia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="72b6e-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="72b6e-195">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-195">Example:</span></span>  
  
```sql  
SELECT VALUE REF(p).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="72b6e-196">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-196">Output:</span></span>  
  
|<span data-ttu-id="72b6e-197">Valor</span><span class="sxs-lookup"><span data-stu-id="72b6e-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="72b6e-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="72b6e-198">Adjustable Race</span></span>|  
|<span data-ttu-id="72b6e-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="72b6e-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="72b6e-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="72b6e-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="72b6e-201">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="72b6e-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="72b6e-202">DEREF</span></span>  

 <span data-ttu-id="72b6e-203">[Deref](deref-entity-sql.md) desreferencia un valor de referencia y genera el resultado de dicha desreferenciación.</span><span class="sxs-lookup"><span data-stu-id="72b6e-203">[DEREF](deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="72b6e-204">Por ejemplo, la consulta siguiente genera las entidades Order para cada entidad Order en el conjunto de entidades Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.</span><span class="sxs-lookup"><span data-stu-id="72b6e-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="72b6e-205">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-205">Example:</span></span>  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="72b6e-206">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-206">Output:</span></span>  
  
|<span data-ttu-id="72b6e-207">Valor</span><span class="sxs-lookup"><span data-stu-id="72b6e-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="72b6e-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="72b6e-208">Adjustable Race</span></span>|  
|<span data-ttu-id="72b6e-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="72b6e-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="72b6e-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="72b6e-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="72b6e-211">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="72b6e-212">CREATEREF y KEY</span><span class="sxs-lookup"><span data-stu-id="72b6e-212">CREATEREF AND KEY</span></span>  

 <span data-ttu-id="72b6e-213">[CREATEREF](createref-entity-sql.md) crea una referencia que pasa una clave.</span><span class="sxs-lookup"><span data-stu-id="72b6e-213">[CREATEREF](createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="72b6e-214">La [clave](key-entity-sql.md) extrae la parte de la clave de una expresión con referencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="72b6e-214">[KEY](key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="72b6e-215">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-215">Example:</span></span>  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))
    FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="72b6e-216">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-216">Output:</span></span>  
  
|<span data-ttu-id="72b6e-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="72b6e-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="72b6e-218">980</span><span class="sxs-lookup"><span data-stu-id="72b6e-218">980</span></span>|  
|<span data-ttu-id="72b6e-219">365</span><span class="sxs-lookup"><span data-stu-id="72b6e-219">365</span></span>|  
|<span data-ttu-id="72b6e-220">771</span><span class="sxs-lookup"><span data-stu-id="72b6e-220">771</span></span>|  
|<span data-ttu-id="72b6e-221">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="72b6e-222">Funciones</span><span class="sxs-lookup"><span data-stu-id="72b6e-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="72b6e-223">Canonical</span><span class="sxs-lookup"><span data-stu-id="72b6e-223">Canonical</span></span>  

 <span data-ttu-id="72b6e-224">El espacio de nombres para [las funciones canónicas](canonical-functions.md) es EDM, como en `Edm.Length("string")` .</span><span class="sxs-lookup"><span data-stu-id="72b6e-224">The namespace for [canonical functions](canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="72b6e-225">No es necesario especificar el espacio de nombres a no ser que se importe otro espacio de nombres que contenga una función con el mismo nombre que una función canónica.</span><span class="sxs-lookup"><span data-stu-id="72b6e-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="72b6e-226">Si dos espacios de nombres tienen la misma función, el usuario debe especificar el nombre completo.</span><span class="sxs-lookup"><span data-stu-id="72b6e-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="72b6e-227">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-227">Example:</span></span>  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="72b6e-228">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-228">Output:</span></span>  
  
|<span data-ttu-id="72b6e-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="72b6e-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="72b6e-230">6</span><span class="sxs-lookup"><span data-stu-id="72b6e-230">6</span></span>|  
|<span data-ttu-id="72b6e-231">6</span><span class="sxs-lookup"><span data-stu-id="72b6e-231">6</span></span>|  
|<span data-ttu-id="72b6e-232">5</span><span class="sxs-lookup"><span data-stu-id="72b6e-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="72b6e-233">Específicas de proveedores de Microsoft</span><span class="sxs-lookup"><span data-stu-id="72b6e-233">Microsoft Provider-Specific</span></span>  

 <span data-ttu-id="72b6e-234">[Las funciones específicas del proveedor de Microsoft](../sqlclient-for-ef-functions.md) se encuentran en el `SqlServer` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="72b6e-234">[Microsoft provider-specific functions](../sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="72b6e-235">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-235">Example:</span></span>  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="72b6e-236">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-236">Output:</span></span>  
  
|<span data-ttu-id="72b6e-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="72b6e-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="72b6e-238">27</span><span class="sxs-lookup"><span data-stu-id="72b6e-238">27</span></span>|  
|<span data-ttu-id="72b6e-239">27</span><span class="sxs-lookup"><span data-stu-id="72b6e-239">27</span></span>|  
|<span data-ttu-id="72b6e-240">26</span><span class="sxs-lookup"><span data-stu-id="72b6e-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="72b6e-241">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="72b6e-241">Namespaces</span></span>  

 <span data-ttu-id="72b6e-242">El [uso](using-entity-sql.md) de especifica espacios de nombres utilizados en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="72b6e-242">[USING](using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="72b6e-243">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-243">Example:</span></span>  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="72b6e-244">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-244">Output:</span></span>  
  
|<span data-ttu-id="72b6e-245">Valor</span><span class="sxs-lookup"><span data-stu-id="72b6e-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="72b6e-246">aa</span><span class="sxs-lookup"><span data-stu-id="72b6e-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="72b6e-247">Paginación</span><span class="sxs-lookup"><span data-stu-id="72b6e-247">Paging</span></span>  

 <span data-ttu-id="72b6e-248">La paginación se puede expresar declarando una cláusula [SKIP](skip-entity-sql.md) y [Limit](limit-entity-sql.md) en la cláusula [order by](order-by-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="72b6e-248">Paging can be expressed by declaring a [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses to the [ORDER BY](order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="72b6e-249">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-249">Example:</span></span>  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="72b6e-250">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-250">Output:</span></span>  
  
|<span data-ttu-id="72b6e-251">ID</span><span class="sxs-lookup"><span data-stu-id="72b6e-251">ID</span></span>|<span data-ttu-id="72b6e-252">Nombre</span><span class="sxs-lookup"><span data-stu-id="72b6e-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="72b6e-253">10</span><span class="sxs-lookup"><span data-stu-id="72b6e-253">10</span></span>|<span data-ttu-id="72b6e-254">Adina</span><span class="sxs-lookup"><span data-stu-id="72b6e-254">Adina</span></span>|  
|<span data-ttu-id="72b6e-255">11</span><span class="sxs-lookup"><span data-stu-id="72b6e-255">11</span></span>|<span data-ttu-id="72b6e-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="72b6e-256">Agcaoili</span></span>|  
|<span data-ttu-id="72b6e-257">12</span><span class="sxs-lookup"><span data-stu-id="72b6e-257">12</span></span>|<span data-ttu-id="72b6e-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="72b6e-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="72b6e-259">Agrupar</span><span class="sxs-lookup"><span data-stu-id="72b6e-259">Grouping</span></span>  

 <span data-ttu-id="72b6e-260">La [agrupación por](group-by-entity-sql.md) especifica los grupos en los que se van a colocar los objetos devueltos por una expresión de consulta ([Select](select-entity-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="72b6e-260">[GROUPING BY](group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="72b6e-261">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-261">Example:</span></span>  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="72b6e-262">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-262">Output:</span></span>  
  
|<span data-ttu-id="72b6e-263">name</span><span class="sxs-lookup"><span data-stu-id="72b6e-263">name</span></span>|  
|----------|  
|<span data-ttu-id="72b6e-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="72b6e-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="72b6e-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="72b6e-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="72b6e-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="72b6e-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="72b6e-267">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="72b6e-268">Navegación</span><span class="sxs-lookup"><span data-stu-id="72b6e-268">Navigation</span></span>  

 <span data-ttu-id="72b6e-269">El operador de navegación por relaciones permite navegar por la relación de un tipo de entidad (extremo inicial) a otro (extremo final).</span><span class="sxs-lookup"><span data-stu-id="72b6e-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="72b6e-270">[Navigate](navigate-entity-sql.md) toma el tipo de relación calificado como \<namespace> . \<relationship type name> .</span><span class="sxs-lookup"><span data-stu-id="72b6e-270">[NAVIGATE](navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="72b6e-271">Navigate devuelve Ref \<T> si la cardinalidad del extremo final es 1.</span><span class="sxs-lookup"><span data-stu-id="72b6e-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="72b6e-272">Si la cardinalidad del extremo final es n, se devolverá la colección<> de referencia \<T> .</span><span class="sxs-lookup"><span data-stu-id="72b6e-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="72b6e-273">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-273">Example:</span></span>  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="72b6e-274">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-274">Output:</span></span>  
  
|<span data-ttu-id="72b6e-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="72b6e-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="72b6e-276">1</span><span class="sxs-lookup"><span data-stu-id="72b6e-276">1</span></span>|  
|<span data-ttu-id="72b6e-277">2</span><span class="sxs-lookup"><span data-stu-id="72b6e-277">2</span></span>|  
|<span data-ttu-id="72b6e-278">3</span><span class="sxs-lookup"><span data-stu-id="72b6e-278">3</span></span>|  
|<span data-ttu-id="72b6e-279">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="72b6e-280">SELECT VALUE y SELECT</span><span class="sxs-lookup"><span data-stu-id="72b6e-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="72b6e-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="72b6e-281">SELECT VALUE</span></span>  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="72b6e-282">proporciona la cláusula SELECT VALUE para omitir la creación de filas implícitas.</span><span class="sxs-lookup"><span data-stu-id="72b6e-282">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="72b6e-283">Solo se puede especificar un elemento en una cláusula SELECT VALUE.</span><span class="sxs-lookup"><span data-stu-id="72b6e-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="72b6e-284">Cuando se utiliza este tipo de cláusula, no se crea ningún contenedor de filas en torno a los elementos de la cláusula SELECT y se puede generar una colección de la forma deseada, por ejemplo: `SELECT VALUE a` .</span><span class="sxs-lookup"><span data-stu-id="72b6e-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="72b6e-285">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-285">Example:</span></span>  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="72b6e-286">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-286">Output:</span></span>  
  
|<span data-ttu-id="72b6e-287">Nombre</span><span class="sxs-lookup"><span data-stu-id="72b6e-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="72b6e-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="72b6e-288">Adjustable Race</span></span>|  
|<span data-ttu-id="72b6e-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="72b6e-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="72b6e-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="72b6e-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="72b6e-291">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="72b6e-292">SELECT</span><span class="sxs-lookup"><span data-stu-id="72b6e-292">SELECT</span></span>  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="72b6e-293">también proporciona el constructor de filas para crear filas arbitrarias.</span><span class="sxs-lookup"><span data-stu-id="72b6e-293">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="72b6e-294">SELECT toma uno o más elementos en la proyección y devuelve un registro de datos con campos, por ejemplo: `SELECT a, b, c`.</span><span class="sxs-lookup"><span data-stu-id="72b6e-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="72b6e-295">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-295">Example:</span></span>  
  
 <span data-ttu-id="72b6e-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="72b6e-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="72b6e-297">Nombre</span><span class="sxs-lookup"><span data-stu-id="72b6e-297">Name</span></span>|<span data-ttu-id="72b6e-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="72b6e-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="72b6e-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="72b6e-299">Adjustable Race</span></span>|<span data-ttu-id="72b6e-300">1</span><span class="sxs-lookup"><span data-stu-id="72b6e-300">1</span></span>|  
|<span data-ttu-id="72b6e-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="72b6e-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="72b6e-302">879</span><span class="sxs-lookup"><span data-stu-id="72b6e-302">879</span></span>|  
|<span data-ttu-id="72b6e-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="72b6e-303">AWC Logo Cap</span></span>|<span data-ttu-id="72b6e-304">712</span><span class="sxs-lookup"><span data-stu-id="72b6e-304">712</span></span>|  
|<span data-ttu-id="72b6e-305">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-305">...</span></span>|<span data-ttu-id="72b6e-306">...</span><span class="sxs-lookup"><span data-stu-id="72b6e-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="72b6e-307">EXPRESIÓN CASE</span><span class="sxs-lookup"><span data-stu-id="72b6e-307">CASE EXPRESSION</span></span>  

 <span data-ttu-id="72b6e-308">La [expresión Case](case-entity-sql.md) evalúa un conjunto de Expresiones booleanas para determinar el resultado.</span><span class="sxs-lookup"><span data-stu-id="72b6e-308">The [case expression](case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="72b6e-309">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="72b6e-309">Example:</span></span>  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="72b6e-310">Salida:</span><span class="sxs-lookup"><span data-stu-id="72b6e-310">Output:</span></span>  
  
|<span data-ttu-id="72b6e-311">Valor</span><span class="sxs-lookup"><span data-stu-id="72b6e-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="72b6e-312">TRUE</span><span class="sxs-lookup"><span data-stu-id="72b6e-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="72b6e-313">Vea también</span><span class="sxs-lookup"><span data-stu-id="72b6e-313">See also</span></span>

- [<span data-ttu-id="72b6e-314">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="72b6e-314">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="72b6e-315">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="72b6e-315">Entity SQL Overview</span></span>](entity-sql-overview.md)
