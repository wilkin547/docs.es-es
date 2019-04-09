---
title: Referencia rápida de Entity SQL
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: b4e3eaf8abd82b63fa2663b47f878ecfa9584897
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207076"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="a7986-102">Referencia rápida de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a7986-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="a7986-103">Este tema proporciona una referencia rápida a las consultas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7986-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="a7986-104">Las consultas en este tema se basan en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="a7986-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="a7986-105">Literales</span><span class="sxs-lookup"><span data-stu-id="a7986-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="a7986-106">String</span><span class="sxs-lookup"><span data-stu-id="a7986-106">String</span></span>  
 <span data-ttu-id="a7986-107">Hay literales de cadenas de caracteres Unicode y no Unicode.</span><span class="sxs-lookup"><span data-stu-id="a7986-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="a7986-108">Las cadenas Unicode van precedidas de N. Por ejemplo, `N'hello'`.</span><span class="sxs-lookup"><span data-stu-id="a7986-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="a7986-109">A continuación se incluye un ejemplo de un literal de cadena no Unicode:</span><span class="sxs-lookup"><span data-stu-id="a7986-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="a7986-110">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-110">Output:</span></span>  
  
|<span data-ttu-id="a7986-111">Valor</span><span class="sxs-lookup"><span data-stu-id="a7986-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a7986-112">hello</span><span class="sxs-lookup"><span data-stu-id="a7986-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="a7986-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="a7986-113">DateTime</span></span>  
 <span data-ttu-id="a7986-114">En los literales DateTime, las partes de fecha y hora son obligatorias.</span><span class="sxs-lookup"><span data-stu-id="a7986-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="a7986-115">No hay valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a7986-115">There are no default values.</span></span>  
  
 <span data-ttu-id="a7986-116">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-116">Example:</span></span>  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="a7986-117">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-117">Output:</span></span>  
  
|<span data-ttu-id="a7986-118">Valor</span><span class="sxs-lookup"><span data-stu-id="a7986-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a7986-119">25.12.06 01:01:00</span><span class="sxs-lookup"><span data-stu-id="a7986-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="a7986-120">Integer</span><span class="sxs-lookup"><span data-stu-id="a7986-120">Integer</span></span>  
 <span data-ttu-id="a7986-121">Los literales enteros pueden ser de tipo Int32 (123), UInt32 (123U), Int64 (123L) y UInt64 (123UL).</span><span class="sxs-lookup"><span data-stu-id="a7986-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="a7986-122">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-122">Example:</span></span>  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="a7986-123">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-123">Output:</span></span>  
  
|<span data-ttu-id="a7986-124">Valor</span><span class="sxs-lookup"><span data-stu-id="a7986-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a7986-125">1</span><span class="sxs-lookup"><span data-stu-id="a7986-125">1</span></span>|  
|<span data-ttu-id="a7986-126">2</span><span class="sxs-lookup"><span data-stu-id="a7986-126">2</span></span>|  
|<span data-ttu-id="a7986-127">3</span><span class="sxs-lookup"><span data-stu-id="a7986-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="a7986-128">Otros</span><span class="sxs-lookup"><span data-stu-id="a7986-128">Other</span></span>  
 <span data-ttu-id="a7986-129">Los literales Other admitidos por [!INCLUDE[esql](../../../../../../includes/esql-md.md)] son Guid, Binary, Float/Double, Decimal y `null`.</span><span class="sxs-lookup"><span data-stu-id="a7986-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="a7986-130">Los literales NULL en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se consideran compatibles con todos los demás tipos del modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="a7986-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="a7986-131">Constructores de tipos</span><span class="sxs-lookup"><span data-stu-id="a7986-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="a7986-132">ROW</span><span class="sxs-lookup"><span data-stu-id="a7986-132">ROW</span></span>  
 <span data-ttu-id="a7986-133">[FILA](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) crea un valor (registro) anónimo, escrito estructuralmente como en:</span><span class="sxs-lookup"><span data-stu-id="a7986-133">[ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in:</span></span> `ROW(1 AS myNumber, ‘Name’ AS myName).`  
  
 <span data-ttu-id="a7986-134">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-134">Example:</span></span>  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 <span data-ttu-id="a7986-135">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-135">Output:</span></span>  
  
|<span data-ttu-id="a7986-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="a7986-136">ProductID</span></span>|<span data-ttu-id="a7986-137">Name</span><span class="sxs-lookup"><span data-stu-id="a7986-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="a7986-138">1</span><span class="sxs-lookup"><span data-stu-id="a7986-138">1</span></span>|<span data-ttu-id="a7986-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="a7986-139">Adjustable Race</span></span>|  
|<span data-ttu-id="a7986-140">879</span><span class="sxs-lookup"><span data-stu-id="a7986-140">879</span></span>|<span data-ttu-id="a7986-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="a7986-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="a7986-142">712</span><span class="sxs-lookup"><span data-stu-id="a7986-142">712</span></span>|<span data-ttu-id="a7986-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="a7986-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="a7986-144">...</span><span class="sxs-lookup"><span data-stu-id="a7986-144">...</span></span>|<span data-ttu-id="a7986-145">...</span><span class="sxs-lookup"><span data-stu-id="a7986-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="a7986-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="a7986-146">MULTISET</span></span>  
 <span data-ttu-id="a7986-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) crea colecciones, como:</span><span class="sxs-lookup"><span data-stu-id="a7986-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 `MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`  
  
 <span data-ttu-id="a7986-148">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-148">Example:</span></span>  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="a7986-149">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-149">Output:</span></span>  
  
|<span data-ttu-id="a7986-150">ProductID</span><span class="sxs-lookup"><span data-stu-id="a7986-150">ProductID</span></span>|<span data-ttu-id="a7986-151">Name</span><span class="sxs-lookup"><span data-stu-id="a7986-151">Name</span></span>|<span data-ttu-id="a7986-152">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="a7986-152">ProductNumber</span></span>|<span data-ttu-id="a7986-153">…</span><span class="sxs-lookup"><span data-stu-id="a7986-153">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="a7986-154">842</span><span class="sxs-lookup"><span data-stu-id="a7986-154">842</span></span>|<span data-ttu-id="a7986-155">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="a7986-155">Touring-Panniers, Large</span></span>|<span data-ttu-id="a7986-156">PA-T100</span><span class="sxs-lookup"><span data-stu-id="a7986-156">PA-T100</span></span>|<span data-ttu-id="a7986-157">…</span><span class="sxs-lookup"><span data-stu-id="a7986-157">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="a7986-158">Object</span><span class="sxs-lookup"><span data-stu-id="a7986-158">Object</span></span>  
 <span data-ttu-id="a7986-159">[Llamada de Constructor de tipo](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) construye los objetos definidos por el usuario (nombre), como `person("abc", 12)`.</span><span class="sxs-lookup"><span data-stu-id="a7986-159">[Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="a7986-160">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-160">Example:</span></span>  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="a7986-161">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-161">Output:</span></span>  
  
|<span data-ttu-id="a7986-162">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="a7986-162">SalesOrderDetailID</span></span>|<span data-ttu-id="a7986-163">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="a7986-163">CarrierTrackingNumber</span></span>|<span data-ttu-id="a7986-164">OrderQty</span><span class="sxs-lookup"><span data-stu-id="a7986-164">OrderQty</span></span>|<span data-ttu-id="a7986-165">ProductID</span><span class="sxs-lookup"><span data-stu-id="a7986-165">ProductID</span></span>|<span data-ttu-id="a7986-166">...</span><span class="sxs-lookup"><span data-stu-id="a7986-166">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="a7986-167">1</span><span class="sxs-lookup"><span data-stu-id="a7986-167">1</span></span>|<span data-ttu-id="a7986-168">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="a7986-168">4911-403C-98</span></span>|<span data-ttu-id="a7986-169">1</span><span class="sxs-lookup"><span data-stu-id="a7986-169">1</span></span>|<span data-ttu-id="a7986-170">776</span><span class="sxs-lookup"><span data-stu-id="a7986-170">776</span></span>|<span data-ttu-id="a7986-171">...</span><span class="sxs-lookup"><span data-stu-id="a7986-171">...</span></span>|  
|<span data-ttu-id="a7986-172">2</span><span class="sxs-lookup"><span data-stu-id="a7986-172">2</span></span>|<span data-ttu-id="a7986-173">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="a7986-173">4911-403C-98</span></span>|<span data-ttu-id="a7986-174">3</span><span class="sxs-lookup"><span data-stu-id="a7986-174">3</span></span>|<span data-ttu-id="a7986-175">777</span><span class="sxs-lookup"><span data-stu-id="a7986-175">777</span></span>|<span data-ttu-id="a7986-176">...</span><span class="sxs-lookup"><span data-stu-id="a7986-176">...</span></span>|  
|<span data-ttu-id="a7986-177">...</span><span class="sxs-lookup"><span data-stu-id="a7986-177">...</span></span>|<span data-ttu-id="a7986-178">...</span><span class="sxs-lookup"><span data-stu-id="a7986-178">...</span></span>|<span data-ttu-id="a7986-179">...</span><span class="sxs-lookup"><span data-stu-id="a7986-179">...</span></span>|<span data-ttu-id="a7986-180">...</span><span class="sxs-lookup"><span data-stu-id="a7986-180">...</span></span>|<span data-ttu-id="a7986-181">...</span><span class="sxs-lookup"><span data-stu-id="a7986-181">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="a7986-182">Referencias</span><span class="sxs-lookup"><span data-stu-id="a7986-182">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="a7986-183">REF</span><span class="sxs-lookup"><span data-stu-id="a7986-183">REF</span></span>  
 <span data-ttu-id="a7986-184">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) crea una referencia a una instancia del tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="a7986-184">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="a7986-185">Por ejemplo, la consulta siguiente devuelve referencias a cada entidad Order en el conjunto de entidades Orders:</span><span class="sxs-lookup"><span data-stu-id="a7986-185">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="a7986-186">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-186">Output:</span></span>  
  
|<span data-ttu-id="a7986-187">Valor</span><span class="sxs-lookup"><span data-stu-id="a7986-187">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a7986-188">1</span><span class="sxs-lookup"><span data-stu-id="a7986-188">1</span></span>|  
|<span data-ttu-id="a7986-189">2</span><span class="sxs-lookup"><span data-stu-id="a7986-189">2</span></span>|  
|<span data-ttu-id="a7986-190">3</span><span class="sxs-lookup"><span data-stu-id="a7986-190">3</span></span>|  
|<span data-ttu-id="a7986-191">...</span><span class="sxs-lookup"><span data-stu-id="a7986-191">...</span></span>|  
  
 <span data-ttu-id="a7986-192">En el ejemplo siguiente se usa el operador de extracción de propiedades (.) para tener acceso a una propiedad de una entidad.</span><span class="sxs-lookup"><span data-stu-id="a7986-192">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="a7986-193">Cuando se utiliza el operador de extracción de propiedades, la referencia se desreferencia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a7986-193">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="a7986-194">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-194">Example:</span></span>  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="a7986-195">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-195">Output:</span></span>  
  
|<span data-ttu-id="a7986-196">Valor</span><span class="sxs-lookup"><span data-stu-id="a7986-196">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a7986-197">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="a7986-197">Adjustable Race</span></span>|  
|<span data-ttu-id="a7986-198">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="a7986-198">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="a7986-199">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="a7986-199">AWC Logo Cap</span></span>|  
|<span data-ttu-id="a7986-200">...</span><span class="sxs-lookup"><span data-stu-id="a7986-200">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="a7986-201">DEREF</span><span class="sxs-lookup"><span data-stu-id="a7986-201">DEREF</span></span>  
 <span data-ttu-id="a7986-202">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) desreferencia un valor de referencia y genera el resultado de dicha desreferenciación.</span><span class="sxs-lookup"><span data-stu-id="a7986-202">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="a7986-203">Por ejemplo, la consulta siguiente genera las entidades Order para cada entidad Order en el conjunto de entidades Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.</span><span class="sxs-lookup"><span data-stu-id="a7986-203">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="a7986-204">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-204">Example:</span></span>  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="a7986-205">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-205">Output:</span></span>  
  
|<span data-ttu-id="a7986-206">Valor</span><span class="sxs-lookup"><span data-stu-id="a7986-206">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a7986-207">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="a7986-207">Adjustable Race</span></span>|  
|<span data-ttu-id="a7986-208">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="a7986-208">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="a7986-209">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="a7986-209">AWC Logo Cap</span></span>|  
|<span data-ttu-id="a7986-210">...</span><span class="sxs-lookup"><span data-stu-id="a7986-210">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="a7986-211">CREATEREF y KEY</span><span class="sxs-lookup"><span data-stu-id="a7986-211">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="a7986-212">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) crea una referencia que pasa una clave.</span><span class="sxs-lookup"><span data-stu-id="a7986-212">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="a7986-213">[CLAVE](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extrae la parte de una expresión con referencia de tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="a7986-213">[KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="a7986-214">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-214">Example:</span></span>  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="a7986-215">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-215">Output:</span></span>  
  
|<span data-ttu-id="a7986-216">ProductID</span><span class="sxs-lookup"><span data-stu-id="a7986-216">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="a7986-217">980</span><span class="sxs-lookup"><span data-stu-id="a7986-217">980</span></span>|  
|<span data-ttu-id="a7986-218">365</span><span class="sxs-lookup"><span data-stu-id="a7986-218">365</span></span>|  
|<span data-ttu-id="a7986-219">771</span><span class="sxs-lookup"><span data-stu-id="a7986-219">771</span></span>|  
|<span data-ttu-id="a7986-220">...</span><span class="sxs-lookup"><span data-stu-id="a7986-220">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="a7986-221">Funciones</span><span class="sxs-lookup"><span data-stu-id="a7986-221">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="a7986-222">Canónicas</span><span class="sxs-lookup"><span data-stu-id="a7986-222">Canonical</span></span>  
 <span data-ttu-id="a7986-223">El espacio de nombres [funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) es Edm, como en `Edm.Length("string")`.</span><span class="sxs-lookup"><span data-stu-id="a7986-223">The namespace for [canonical functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="a7986-224">No es necesario especificar el espacio de nombres a no ser que se importe otro espacio de nombres que contenga una función con el mismo nombre que una función canónica.</span><span class="sxs-lookup"><span data-stu-id="a7986-224">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="a7986-225">Si dos espacios de nombres tienen la misma función, el usuario debe especificar el nombre completo.</span><span class="sxs-lookup"><span data-stu-id="a7986-225">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="a7986-226">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-226">Example:</span></span>  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="a7986-227">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-227">Output:</span></span>  
  
|<span data-ttu-id="a7986-228">NameLen</span><span class="sxs-lookup"><span data-stu-id="a7986-228">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="a7986-229">6</span><span class="sxs-lookup"><span data-stu-id="a7986-229">6</span></span>|  
|<span data-ttu-id="a7986-230">6</span><span class="sxs-lookup"><span data-stu-id="a7986-230">6</span></span>|  
|<span data-ttu-id="a7986-231">5</span><span class="sxs-lookup"><span data-stu-id="a7986-231">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="a7986-232">Específicas de proveedores de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a7986-232">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="a7986-233">[Funciones específicas del proveedor de Microsoft](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) están en el `SqlServer` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a7986-233">[Microsoft provider-specific functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="a7986-234">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-234">Example:</span></span>  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="a7986-235">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-235">Output:</span></span>  
  
|<span data-ttu-id="a7986-236">EmailLen</span><span class="sxs-lookup"><span data-stu-id="a7986-236">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="a7986-237">27</span><span class="sxs-lookup"><span data-stu-id="a7986-237">27</span></span>|  
|<span data-ttu-id="a7986-238">27</span><span class="sxs-lookup"><span data-stu-id="a7986-238">27</span></span>|  
|<span data-ttu-id="a7986-239">26</span><span class="sxs-lookup"><span data-stu-id="a7986-239">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="a7986-240">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="a7986-240">Namespaces</span></span>  
 <span data-ttu-id="a7986-241">[USO de](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) especifica los espacios de nombres utilizados en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="a7986-241">[USING](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="a7986-242">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-242">Example:</span></span>  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="a7986-243">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-243">Output:</span></span>  
  
|<span data-ttu-id="a7986-244">Valor</span><span class="sxs-lookup"><span data-stu-id="a7986-244">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a7986-245">aa</span><span class="sxs-lookup"><span data-stu-id="a7986-245">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="a7986-246">Paginación</span><span class="sxs-lookup"><span data-stu-id="a7986-246">Paging</span></span>  
 <span data-ttu-id="a7986-247">Paginación se puede expresar declarando un [omitir](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) y [límite](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) subcláusulas a la [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) cláusula.</span><span class="sxs-lookup"><span data-stu-id="a7986-247">Paging can be expressed by declaring a [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses to the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="a7986-248">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-248">Example:</span></span>  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="a7986-249">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-249">Output:</span></span>  
  
|<span data-ttu-id="a7986-250">ID</span><span class="sxs-lookup"><span data-stu-id="a7986-250">ID</span></span>|<span data-ttu-id="a7986-251">Name</span><span class="sxs-lookup"><span data-stu-id="a7986-251">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="a7986-252">10</span><span class="sxs-lookup"><span data-stu-id="a7986-252">10</span></span>|<span data-ttu-id="a7986-253">Adina</span><span class="sxs-lookup"><span data-stu-id="a7986-253">Adina</span></span>|  
|<span data-ttu-id="a7986-254">11</span><span class="sxs-lookup"><span data-stu-id="a7986-254">11</span></span>|<span data-ttu-id="a7986-255">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="a7986-255">Agcaoili</span></span>|  
|<span data-ttu-id="a7986-256">12</span><span class="sxs-lookup"><span data-stu-id="a7986-256">12</span></span>|<span data-ttu-id="a7986-257">Aguilar</span><span class="sxs-lookup"><span data-stu-id="a7986-257">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="a7986-258">Agrupar</span><span class="sxs-lookup"><span data-stu-id="a7986-258">Grouping</span></span>  
 <span data-ttu-id="a7986-259">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) especifica los grupos en los objetos devueltos por una consulta ([seleccione](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expresión que se van a colocarse.</span><span class="sxs-lookup"><span data-stu-id="a7986-259">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="a7986-260">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-260">Example:</span></span>  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="a7986-261">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-261">Output:</span></span>  
  
|<span data-ttu-id="a7986-262">name</span><span class="sxs-lookup"><span data-stu-id="a7986-262">name</span></span>|  
|----------|  
|<span data-ttu-id="a7986-263">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="a7986-263">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="a7986-264">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="a7986-264">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="a7986-265">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="a7986-265">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="a7986-266">...</span><span class="sxs-lookup"><span data-stu-id="a7986-266">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="a7986-267">Navegación</span><span class="sxs-lookup"><span data-stu-id="a7986-267">Navigation</span></span>  
 <span data-ttu-id="a7986-268">El operador de navegación por relaciones permite navegar por la relación de un tipo de entidad (extremo inicial) a otro (extremo final).</span><span class="sxs-lookup"><span data-stu-id="a7986-268">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="a7986-269">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) toma el tipo de relación calificado como \<espacio de nombres >.\< nombre de tipo de relación >.</span><span class="sxs-lookup"><span data-stu-id="a7986-269">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="a7986-270">Navegue devuelve Ref\<T > Si la cardinalidad del extremo final es 1.</span><span class="sxs-lookup"><span data-stu-id="a7986-270">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="a7986-271">Si la cardinalidad del extremo final es n, la colección < Ref\<T >> se devolverá.</span><span class="sxs-lookup"><span data-stu-id="a7986-271">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="a7986-272">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-272">Example:</span></span>  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="a7986-273">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-273">Output:</span></span>  
  
|<span data-ttu-id="a7986-274">AddressID</span><span class="sxs-lookup"><span data-stu-id="a7986-274">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="a7986-275">1</span><span class="sxs-lookup"><span data-stu-id="a7986-275">1</span></span>|  
|<span data-ttu-id="a7986-276">2</span><span class="sxs-lookup"><span data-stu-id="a7986-276">2</span></span>|  
|<span data-ttu-id="a7986-277">3</span><span class="sxs-lookup"><span data-stu-id="a7986-277">3</span></span>|  
|<span data-ttu-id="a7986-278">...</span><span class="sxs-lookup"><span data-stu-id="a7986-278">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="a7986-279">SELECT VALUE y SELECT</span><span class="sxs-lookup"><span data-stu-id="a7986-279">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="a7986-280">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="a7986-280">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a7986-281">proporciona la cláusula SELECT VALUE para omitir la creación de filas implícitas.</span><span class="sxs-lookup"><span data-stu-id="a7986-281">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="a7986-282">Solo se puede especificar un elemento en una cláusula SELECT VALUE.</span><span class="sxs-lookup"><span data-stu-id="a7986-282">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="a7986-283">Cuando se usa una cláusula de ese tipo, se crea ningún contenedor de filas en torno a los elementos en la cláusula SELECT y se puede generar una colección de la forma deseada, por ejemplo: `SELECT VALUE a`.</span><span class="sxs-lookup"><span data-stu-id="a7986-283">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="a7986-284">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-284">Example:</span></span>  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="a7986-285">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-285">Output:</span></span>  
  
|<span data-ttu-id="a7986-286">Name</span><span class="sxs-lookup"><span data-stu-id="a7986-286">Name</span></span>|  
|----------|  
|<span data-ttu-id="a7986-287">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="a7986-287">Adjustable Race</span></span>|  
|<span data-ttu-id="a7986-288">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="a7986-288">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="a7986-289">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="a7986-289">AWC Logo Cap</span></span>|  
|<span data-ttu-id="a7986-290">...</span><span class="sxs-lookup"><span data-stu-id="a7986-290">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="a7986-291">SELECT</span><span class="sxs-lookup"><span data-stu-id="a7986-291">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a7986-292">También proporciona el constructor de filas para crear filas arbitrarias.</span><span class="sxs-lookup"><span data-stu-id="a7986-292">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="a7986-293">SELECT toma uno o más elementos en la proyección y devuelve un registro de datos con campos, por ejemplo: `SELECT a, b, c`.</span><span class="sxs-lookup"><span data-stu-id="a7986-293">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="a7986-294">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-294">Example:</span></span>  
  
 <span data-ttu-id="a7986-295">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="a7986-295">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="a7986-296">Name</span><span class="sxs-lookup"><span data-stu-id="a7986-296">Name</span></span>|<span data-ttu-id="a7986-297">ProductID</span><span class="sxs-lookup"><span data-stu-id="a7986-297">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="a7986-298">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="a7986-298">Adjustable Race</span></span>|<span data-ttu-id="a7986-299">1</span><span class="sxs-lookup"><span data-stu-id="a7986-299">1</span></span>|  
|<span data-ttu-id="a7986-300">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="a7986-300">All-Purpose Bike Stand</span></span>|<span data-ttu-id="a7986-301">879</span><span class="sxs-lookup"><span data-stu-id="a7986-301">879</span></span>|  
|<span data-ttu-id="a7986-302">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="a7986-302">AWC Logo Cap</span></span>|<span data-ttu-id="a7986-303">712</span><span class="sxs-lookup"><span data-stu-id="a7986-303">712</span></span>|  
|<span data-ttu-id="a7986-304">...</span><span class="sxs-lookup"><span data-stu-id="a7986-304">...</span></span>|<span data-ttu-id="a7986-305">...</span><span class="sxs-lookup"><span data-stu-id="a7986-305">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="a7986-306">EXPRESIÓN CASE</span><span class="sxs-lookup"><span data-stu-id="a7986-306">CASE EXPRESSION</span></span>  
 <span data-ttu-id="a7986-307">El [caso expresión](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evalúa un conjunto de expresiones booleanas para determinar el resultado.</span><span class="sxs-lookup"><span data-stu-id="a7986-307">The [case expression](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="a7986-308">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7986-308">Example:</span></span>  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="a7986-309">Resultado:</span><span class="sxs-lookup"><span data-stu-id="a7986-309">Output:</span></span>  
  
|<span data-ttu-id="a7986-310">Valor</span><span class="sxs-lookup"><span data-stu-id="a7986-310">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a7986-311">true</span><span class="sxs-lookup"><span data-stu-id="a7986-311">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7986-312">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7986-312">See also</span></span>

- [<span data-ttu-id="a7986-313">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a7986-313">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="a7986-314">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a7986-314">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
