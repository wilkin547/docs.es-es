---
title: Semántica de comparación (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 57d81d4b581df76a4382ad5e1d72fe8250b10d43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150459"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="d8f11-102">Semántica de comparación (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d8f11-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="d8f11-103">El uso de cualquiera de los operadores de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguientes implica la comparación de las instancias de tipo:</span><span class="sxs-lookup"><span data-stu-id="d8f11-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="d8f11-104">Comparación explícita</span><span class="sxs-lookup"><span data-stu-id="d8f11-104">Explicit comparison</span></span>  
 <span data-ttu-id="d8f11-105">Operaciones de igualdad:</span><span class="sxs-lookup"><span data-stu-id="d8f11-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="d8f11-106">!=</span><span class="sxs-lookup"><span data-stu-id="d8f11-106">!=</span></span>  
  
 <span data-ttu-id="d8f11-107">Operaciones de ordenación:</span><span class="sxs-lookup"><span data-stu-id="d8f11-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="d8f11-108">Operaciones de nulabilidad:</span><span class="sxs-lookup"><span data-stu-id="d8f11-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="d8f11-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="d8f11-109">IS NULL</span></span>  
  
- <span data-ttu-id="d8f11-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="d8f11-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="d8f11-111">Distinción explícita</span><span class="sxs-lookup"><span data-stu-id="d8f11-111">Explicit distinction</span></span>  
 <span data-ttu-id="d8f11-112">Distinción de igualdad:</span><span class="sxs-lookup"><span data-stu-id="d8f11-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="d8f11-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="d8f11-113">DISTINCT</span></span>  
  
- <span data-ttu-id="d8f11-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="d8f11-114">GROUP BY</span></span>  
  
 <span data-ttu-id="d8f11-115">Distinción de ordenación:</span><span class="sxs-lookup"><span data-stu-id="d8f11-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="d8f11-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="d8f11-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="d8f11-117">Distinción implícita</span><span class="sxs-lookup"><span data-stu-id="d8f11-117">Implicit distinction</span></span>  
 <span data-ttu-id="d8f11-118">Operaciones y predicados de conjuntos (igualdad):</span><span class="sxs-lookup"><span data-stu-id="d8f11-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="d8f11-119">UNION</span><span class="sxs-lookup"><span data-stu-id="d8f11-119">UNION</span></span>  
  
- <span data-ttu-id="d8f11-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="d8f11-120">INTERSECT</span></span>  
  
- <span data-ttu-id="d8f11-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="d8f11-121">EXCEPT</span></span>  
  
- <span data-ttu-id="d8f11-122">SET</span><span class="sxs-lookup"><span data-stu-id="d8f11-122">SET</span></span>  
  
- <span data-ttu-id="d8f11-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="d8f11-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="d8f11-124">Predicados de elementos (igualdad):</span><span class="sxs-lookup"><span data-stu-id="d8f11-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="d8f11-125">IN</span><span class="sxs-lookup"><span data-stu-id="d8f11-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="d8f11-126">Combinaciones admitidas</span><span class="sxs-lookup"><span data-stu-id="d8f11-126">Supported Combinations</span></span>  
 <span data-ttu-id="d8f11-127">En la tabla siguiente se muestran todas las combinaciones admitidas de los operadores de comparación para cada clase de tipo:</span><span class="sxs-lookup"><span data-stu-id="d8f11-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="d8f11-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d8f11-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="d8f11-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="d8f11-129">**!=**</span></span>|<span data-ttu-id="d8f11-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="d8f11-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="d8f11-131">**Distintas**</span><span class="sxs-lookup"><span data-stu-id="d8f11-131">**DISTINCT**</span></span>|<span data-ttu-id="d8f11-132">**Unión**</span><span class="sxs-lookup"><span data-stu-id="d8f11-132">**UNION**</span></span><br /><br /> <span data-ttu-id="d8f11-133">**Intersect**</span><span class="sxs-lookup"><span data-stu-id="d8f11-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="d8f11-134">**Excepto**</span><span class="sxs-lookup"><span data-stu-id="d8f11-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="d8f11-135">**Establecer**</span><span class="sxs-lookup"><span data-stu-id="d8f11-135">**SET**</span></span><br /><br /> <span data-ttu-id="d8f11-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="d8f11-136">**OVERLAPS**</span></span>|<span data-ttu-id="d8f11-137">**En**</span><span class="sxs-lookup"><span data-stu-id="d8f11-137">**IN**</span></span>|<span data-ttu-id="d8f11-138">**< <**</span><span class="sxs-lookup"><span data-stu-id="d8f11-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="d8f11-139">**> >**</span><span class="sxs-lookup"><span data-stu-id="d8f11-139">**>   >=**</span></span>|<span data-ttu-id="d8f11-140">**PEDIDO POR**</span><span class="sxs-lookup"><span data-stu-id="d8f11-140">**ORDER BY**</span></span>|<span data-ttu-id="d8f11-141">**ES NULO**</span><span class="sxs-lookup"><span data-stu-id="d8f11-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="d8f11-142">**NO ES NULO**</span><span class="sxs-lookup"><span data-stu-id="d8f11-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="d8f11-143">Tipo de entidad</span><span class="sxs-lookup"><span data-stu-id="d8f11-143">Entity type</span></span>|<span data-ttu-id="d8f11-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="d8f11-145">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="d8f11-146">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="d8f11-147">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="d8f11-148">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-149">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="d8f11-151">Tipo complejo</span><span class="sxs-lookup"><span data-stu-id="d8f11-151">Complex type</span></span>|<span data-ttu-id="d8f11-152">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-153">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-154">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-155">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-156">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-157">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-158">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d8f11-159">Row</span><span class="sxs-lookup"><span data-stu-id="d8f11-159">Row</span></span>|<span data-ttu-id="d8f11-160">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="d8f11-161">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="d8f11-162">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="d8f11-163">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-164">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-165">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="d8f11-166">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d8f11-167">Tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="d8f11-167">Primitive type</span></span>|<span data-ttu-id="d8f11-168">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d8f11-168">Provider-specific</span></span>|<span data-ttu-id="d8f11-169">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d8f11-169">Provider-specific</span></span>|<span data-ttu-id="d8f11-170">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d8f11-170">Provider-specific</span></span>|<span data-ttu-id="d8f11-171">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d8f11-171">Provider-specific</span></span>|<span data-ttu-id="d8f11-172">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d8f11-172">Provider-specific</span></span>|<span data-ttu-id="d8f11-173">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d8f11-173">Provider-specific</span></span>|<span data-ttu-id="d8f11-174">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d8f11-174">Provider-specific</span></span>|  
|<span data-ttu-id="d8f11-175">Conjunto múltiple</span><span class="sxs-lookup"><span data-stu-id="d8f11-175">Multiset</span></span>|<span data-ttu-id="d8f11-176">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-177">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-178">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-179">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-180">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-181">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-182">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d8f11-183">Ref</span><span class="sxs-lookup"><span data-stu-id="d8f11-183">Ref</span></span>|<span data-ttu-id="d8f11-184">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="d8f11-185">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="d8f11-186">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="d8f11-187">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="d8f11-188">Throw</span><span class="sxs-lookup"><span data-stu-id="d8f11-188">Throw</span></span>|<span data-ttu-id="d8f11-189">Throw</span><span class="sxs-lookup"><span data-stu-id="d8f11-189">Throw</span></span>|<span data-ttu-id="d8f11-190">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="d8f11-191">Asociación</span><span class="sxs-lookup"><span data-stu-id="d8f11-191">Association</span></span><br /><br /> <span data-ttu-id="d8f11-192">type</span><span class="sxs-lookup"><span data-stu-id="d8f11-192">type</span></span>|<span data-ttu-id="d8f11-193">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-194">Throw</span><span class="sxs-lookup"><span data-stu-id="d8f11-194">Throw</span></span>|<span data-ttu-id="d8f11-195">Throw</span><span class="sxs-lookup"><span data-stu-id="d8f11-195">Throw</span></span>|<span data-ttu-id="d8f11-196">Throw</span><span class="sxs-lookup"><span data-stu-id="d8f11-196">Throw</span></span>|<span data-ttu-id="d8f11-197">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-198">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="d8f11-199">Lanzar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="d8f11-200"><sup>1</sup> Las referencias de las instancias de tipo de entidad especificadas se comparan implícitamente, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8f11-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="d8f11-201">Una instancia de entidad no se puede comparar con una referencia explícita.</span><span class="sxs-lookup"><span data-stu-id="d8f11-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="d8f11-202">Si se intenta, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="d8f11-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="d8f11-203">Por ejemplo, la siguiente consulta iniciaría una excepción:</span><span class="sxs-lookup"><span data-stu-id="d8f11-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="d8f11-204"><sup>2</sup> Las propiedades de tipos complejos se aplanan antes de enviarse a la tienda, por lo que se vuelven comparables (siempre y cuando todas sus propiedades sean comparables).</span><span class="sxs-lookup"><span data-stu-id="d8f11-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="d8f11-205">Consulte también <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="d8f11-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="d8f11-206"><sup>3</sup> El tiempo de ejecución de Entity Framework detecta el caso no admitido y produce una excepción significativa sin involucrar al proveedor o almacén.</span><span class="sxs-lookup"><span data-stu-id="d8f11-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="d8f11-207"><sup>4</sup> Se intenta comparar todas las propiedades.</span><span class="sxs-lookup"><span data-stu-id="d8f11-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="d8f11-208">Si hay una propiedad que es de un tipo no comparable, como text, ntext o image, se podría iniciar una excepción de servidor.</span><span class="sxs-lookup"><span data-stu-id="d8f11-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="d8f11-209"><sup>5</sup> Se comparan todos los elementos individuales de las referencias (esto incluye el nombre del conjunto de entidades y todas las propiedades de clave del tipo de entidad).</span><span class="sxs-lookup"><span data-stu-id="d8f11-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f11-210">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8f11-210">See also</span></span>

- [<span data-ttu-id="d8f11-211">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d8f11-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
