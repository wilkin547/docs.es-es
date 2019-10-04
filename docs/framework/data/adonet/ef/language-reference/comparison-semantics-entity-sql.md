---
title: Semántica de comparación (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 8d7868b0166f0a18824ec25e6cdf639deec665ac
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833943"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="d809a-102">Semántica de comparación (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d809a-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="d809a-103">El uso de cualquiera de los operadores de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguientes implica la comparación de las instancias de tipo:</span><span class="sxs-lookup"><span data-stu-id="d809a-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="d809a-104">Comparación explícita</span><span class="sxs-lookup"><span data-stu-id="d809a-104">Explicit comparison</span></span>  
 <span data-ttu-id="d809a-105">Operaciones de igualdad:</span><span class="sxs-lookup"><span data-stu-id="d809a-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="d809a-106">!=</span><span class="sxs-lookup"><span data-stu-id="d809a-106">!=</span></span>  
  
 <span data-ttu-id="d809a-107">Operaciones de ordenación:</span><span class="sxs-lookup"><span data-stu-id="d809a-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="d809a-108">Operaciones de nulabilidad:</span><span class="sxs-lookup"><span data-stu-id="d809a-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="d809a-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="d809a-109">IS NULL</span></span>  
  
- <span data-ttu-id="d809a-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="d809a-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="d809a-111">Distinción explícita</span><span class="sxs-lookup"><span data-stu-id="d809a-111">Explicit distinction</span></span>  
 <span data-ttu-id="d809a-112">Distinción de igualdad:</span><span class="sxs-lookup"><span data-stu-id="d809a-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="d809a-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="d809a-113">DISTINCT</span></span>  
  
- <span data-ttu-id="d809a-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="d809a-114">GROUP BY</span></span>  
  
 <span data-ttu-id="d809a-115">Distinción de ordenación:</span><span class="sxs-lookup"><span data-stu-id="d809a-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="d809a-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="d809a-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="d809a-117">Distinción implícita</span><span class="sxs-lookup"><span data-stu-id="d809a-117">Implicit distinction</span></span>  
 <span data-ttu-id="d809a-118">Operaciones y predicados de conjuntos (igualdad):</span><span class="sxs-lookup"><span data-stu-id="d809a-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="d809a-119">UNION</span><span class="sxs-lookup"><span data-stu-id="d809a-119">UNION</span></span>  
  
- <span data-ttu-id="d809a-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="d809a-120">INTERSECT</span></span>  
  
- <span data-ttu-id="d809a-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="d809a-121">EXCEPT</span></span>  
  
- <span data-ttu-id="d809a-122">SET</span><span class="sxs-lookup"><span data-stu-id="d809a-122">SET</span></span>  
  
- <span data-ttu-id="d809a-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="d809a-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="d809a-124">Predicados de elementos (igualdad):</span><span class="sxs-lookup"><span data-stu-id="d809a-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="d809a-125">IN</span><span class="sxs-lookup"><span data-stu-id="d809a-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="d809a-126">Combinaciones admitidas</span><span class="sxs-lookup"><span data-stu-id="d809a-126">Supported Combinations</span></span>  
 <span data-ttu-id="d809a-127">En la tabla siguiente se muestran todas las combinaciones admitidas de los operadores de comparación para cada clase de tipo:</span><span class="sxs-lookup"><span data-stu-id="d809a-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="d809a-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d809a-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="d809a-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="d809a-129">**!=**</span></span>|<span data-ttu-id="d809a-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="d809a-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="d809a-131">**POCO**</span><span class="sxs-lookup"><span data-stu-id="d809a-131">**DISTINCT**</span></span>|<span data-ttu-id="d809a-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="d809a-132">**UNION**</span></span><br /><br /> <span data-ttu-id="d809a-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="d809a-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="d809a-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="d809a-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="d809a-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="d809a-135">**SET**</span></span><br /><br /> <span data-ttu-id="d809a-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="d809a-136">**OVERLAPS**</span></span>|<span data-ttu-id="d809a-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="d809a-137">**IN**</span></span>|<span data-ttu-id="d809a-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="d809a-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="d809a-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="d809a-139">**>   >=**</span></span>|<span data-ttu-id="d809a-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="d809a-140">**ORDER BY**</span></span>|<span data-ttu-id="d809a-141">**ES NULL**</span><span class="sxs-lookup"><span data-stu-id="d809a-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="d809a-142">**NO ES NULL**</span><span class="sxs-lookup"><span data-stu-id="d809a-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="d809a-143">Tipo de entidad</span><span class="sxs-lookup"><span data-stu-id="d809a-143">Entity type</span></span>|<span data-ttu-id="d809a-144">Referencia<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="d809a-145">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="d809a-146">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="d809a-147">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="d809a-148">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-149">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-150">Referencia<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="d809a-151">Tipo complejo</span><span class="sxs-lookup"><span data-stu-id="d809a-151">Complex type</span></span>|<span data-ttu-id="d809a-152">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-153">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-154">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-155">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-156">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-157">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-158">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d809a-159">Fila</span><span class="sxs-lookup"><span data-stu-id="d809a-159">Row</span></span>|<span data-ttu-id="d809a-160">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="d809a-161">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="d809a-162">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="d809a-163">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-164">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-165">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="d809a-166">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d809a-167">Tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="d809a-167">Primitive type</span></span>|<span data-ttu-id="d809a-168">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d809a-168">Provider-specific</span></span>|<span data-ttu-id="d809a-169">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d809a-169">Provider-specific</span></span>|<span data-ttu-id="d809a-170">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d809a-170">Provider-specific</span></span>|<span data-ttu-id="d809a-171">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d809a-171">Provider-specific</span></span>|<span data-ttu-id="d809a-172">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d809a-172">Provider-specific</span></span>|<span data-ttu-id="d809a-173">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d809a-173">Provider-specific</span></span>|<span data-ttu-id="d809a-174">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d809a-174">Provider-specific</span></span>|  
|<span data-ttu-id="d809a-175">Conjunto múltiple</span><span class="sxs-lookup"><span data-stu-id="d809a-175">Multiset</span></span>|<span data-ttu-id="d809a-176">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-177">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-178">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-179">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-180">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-181">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-182">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d809a-183">Ref</span><span class="sxs-lookup"><span data-stu-id="d809a-183">Ref</span></span>|<span data-ttu-id="d809a-184">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="d809a-185">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="d809a-186">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="d809a-187">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="d809a-188">Throw</span><span class="sxs-lookup"><span data-stu-id="d809a-188">Throw</span></span>|<span data-ttu-id="d809a-189">Throw</span><span class="sxs-lookup"><span data-stu-id="d809a-189">Throw</span></span>|<span data-ttu-id="d809a-190">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="d809a-191">Asociación</span><span class="sxs-lookup"><span data-stu-id="d809a-191">Association</span></span><br /><br /> <span data-ttu-id="d809a-192">type</span><span class="sxs-lookup"><span data-stu-id="d809a-192">type</span></span>|<span data-ttu-id="d809a-193">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-194">Throw</span><span class="sxs-lookup"><span data-stu-id="d809a-194">Throw</span></span>|<span data-ttu-id="d809a-195">Throw</span><span class="sxs-lookup"><span data-stu-id="d809a-195">Throw</span></span>|<span data-ttu-id="d809a-196">Throw</span><span class="sxs-lookup"><span data-stu-id="d809a-196">Throw</span></span>|<span data-ttu-id="d809a-197">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-198">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="d809a-199">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="d809a-200"><sup>1</sup> Las referencias de las instancias de tipo de entidad dadas se comparan implícitamente, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d809a-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="d809a-201">Una instancia de entidad no se puede comparar con una referencia explícita.</span><span class="sxs-lookup"><span data-stu-id="d809a-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="d809a-202">Si se intenta, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="d809a-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="d809a-203">Por ejemplo, la siguiente consulta iniciaría una excepción:</span><span class="sxs-lookup"><span data-stu-id="d809a-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="d809a-204"><sup>2</sup> Las propiedades de los tipos complejos se alisan antes de enviarse al almacén, por lo que son comparables (siempre y cuando todas sus propiedades sean comparables).</span><span class="sxs-lookup"><span data-stu-id="d809a-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="d809a-205">Vea también <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="d809a-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="d809a-206"><sup>3</sup> El entorno de tiempo de ejecución de Entity Framework detecta el caso no compatible y produce una excepción significativa sin tener que atraer al proveedor o almacén.</span><span class="sxs-lookup"><span data-stu-id="d809a-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="d809a-207"><sup>4</sup> Se ha intentado comparar todas las propiedades.</span><span class="sxs-lookup"><span data-stu-id="d809a-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="d809a-208">Si hay una propiedad que es de un tipo no comparable, como text, ntext o image, se podría iniciar una excepción de servidor.</span><span class="sxs-lookup"><span data-stu-id="d809a-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="d809a-209"><sup>5</sup> Se comparan todos los elementos individuales de las referencias (esto incluye el nombre del conjunto de entidades y todas las propiedades clave del tipo de entidad).</span><span class="sxs-lookup"><span data-stu-id="d809a-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d809a-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="d809a-210">See also</span></span>

- [<span data-ttu-id="d809a-211">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d809a-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
