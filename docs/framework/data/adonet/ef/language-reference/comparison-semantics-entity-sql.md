---
title: Semántica de comparación (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 2184f86ee43f88b0c4cfc1b96e42e2486c17fe5f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="d6954-102">Semántica de comparación (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d6954-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="d6954-103">El uso de cualquiera de los operadores de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguientes implica la comparación de las instancias de tipo:</span><span class="sxs-lookup"><span data-stu-id="d6954-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="d6954-104">Comparación explícita</span><span class="sxs-lookup"><span data-stu-id="d6954-104">Explicit comparison</span></span>  
 <span data-ttu-id="d6954-105">Operaciones de igualdad:</span><span class="sxs-lookup"><span data-stu-id="d6954-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="d6954-106">!=</span><span class="sxs-lookup"><span data-stu-id="d6954-106">!=</span></span>  
  
 <span data-ttu-id="d6954-107">Operaciones de ordenación:</span><span class="sxs-lookup"><span data-stu-id="d6954-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 <span data-ttu-id="d6954-108">Operaciones de nulabilidad:</span><span class="sxs-lookup"><span data-stu-id="d6954-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="d6954-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="d6954-109">IS NULL</span></span>  
  
-   <span data-ttu-id="d6954-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="d6954-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="d6954-111">Distinción explícita</span><span class="sxs-lookup"><span data-stu-id="d6954-111">Explicit distinction</span></span>  
 <span data-ttu-id="d6954-112">Distinción de igualdad:</span><span class="sxs-lookup"><span data-stu-id="d6954-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="d6954-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="d6954-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="d6954-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="d6954-114">GROUP BY</span></span>  
  
 <span data-ttu-id="d6954-115">Distinción de ordenación:</span><span class="sxs-lookup"><span data-stu-id="d6954-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="d6954-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="d6954-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="d6954-117">Distinción implícita</span><span class="sxs-lookup"><span data-stu-id="d6954-117">Implicit distinction</span></span>  
 <span data-ttu-id="d6954-118">Operaciones y predicados de conjuntos (igualdad):</span><span class="sxs-lookup"><span data-stu-id="d6954-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="d6954-119">UNION</span><span class="sxs-lookup"><span data-stu-id="d6954-119">UNION</span></span>  
  
-   <span data-ttu-id="d6954-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="d6954-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="d6954-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="d6954-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="d6954-122">SET</span><span class="sxs-lookup"><span data-stu-id="d6954-122">SET</span></span>  
  
-   <span data-ttu-id="d6954-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="d6954-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="d6954-124">Predicados de elementos (igualdad):</span><span class="sxs-lookup"><span data-stu-id="d6954-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="d6954-125">IN</span><span class="sxs-lookup"><span data-stu-id="d6954-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="d6954-126">Combinaciones admitidas</span><span class="sxs-lookup"><span data-stu-id="d6954-126">Supported Combinations</span></span>  
 <span data-ttu-id="d6954-127">En la tabla siguiente se muestran todas las combinaciones admitidas de los operadores de comparación para cada clase de tipo:</span><span class="sxs-lookup"><span data-stu-id="d6954-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="d6954-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="d6954-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="d6954-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="d6954-129">**!=**</span></span>|<span data-ttu-id="d6954-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="d6954-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="d6954-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="d6954-131">**DISTINCT**</span></span>|<span data-ttu-id="d6954-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="d6954-132">**UNION**</span></span><br /><br /> <span data-ttu-id="d6954-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="d6954-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="d6954-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="d6954-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="d6954-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="d6954-135">**SET**</span></span><br /><br /> <span data-ttu-id="d6954-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="d6954-136">**OVERLAPS**</span></span>|<span data-ttu-id="d6954-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="d6954-137">**IN**</span></span>|<span data-ttu-id="d6954-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="d6954-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="d6954-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="d6954-139">**>   >=**</span></span>|<span data-ttu-id="d6954-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="d6954-140">**ORDER BY**</span></span>|<span data-ttu-id="d6954-141">**ES NULL**</span><span class="sxs-lookup"><span data-stu-id="d6954-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="d6954-142">**NO ES NULO**</span><span class="sxs-lookup"><span data-stu-id="d6954-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="d6954-143">Tipo de entidad</span><span class="sxs-lookup"><span data-stu-id="d6954-143">Entity type</span></span>|<span data-ttu-id="d6954-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="d6954-145">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="d6954-146">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="d6954-147">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="d6954-148">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-149">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="d6954-151">Tipo complejo</span><span class="sxs-lookup"><span data-stu-id="d6954-151">Complex type</span></span>|<span data-ttu-id="d6954-152">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-153">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-154">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-155">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-156">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-157">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-158">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d6954-159">Fila</span><span class="sxs-lookup"><span data-stu-id="d6954-159">Row</span></span>|<span data-ttu-id="d6954-160">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="d6954-161">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="d6954-162">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="d6954-163">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-164">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-165">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="d6954-166">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d6954-167">Tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="d6954-167">Primitive type</span></span>|<span data-ttu-id="d6954-168">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d6954-168">Provider-specific</span></span>|<span data-ttu-id="d6954-169">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d6954-169">Provider-specific</span></span>|<span data-ttu-id="d6954-170">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d6954-170">Provider-specific</span></span>|<span data-ttu-id="d6954-171">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d6954-171">Provider-specific</span></span>|<span data-ttu-id="d6954-172">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d6954-172">Provider-specific</span></span>|<span data-ttu-id="d6954-173">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d6954-173">Provider-specific</span></span>|<span data-ttu-id="d6954-174">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="d6954-174">Provider-specific</span></span>|  
|<span data-ttu-id="d6954-175">Conjunto múltiple</span><span class="sxs-lookup"><span data-stu-id="d6954-175">Multiset</span></span>|<span data-ttu-id="d6954-176">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-177">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-178">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-179">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-180">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-181">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-182">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d6954-183">Ref</span><span class="sxs-lookup"><span data-stu-id="d6954-183">Ref</span></span>|<span data-ttu-id="d6954-184">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="d6954-185">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="d6954-186">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="d6954-187">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="d6954-188">Throw</span><span class="sxs-lookup"><span data-stu-id="d6954-188">Throw</span></span>|<span data-ttu-id="d6954-189">Throw</span><span class="sxs-lookup"><span data-stu-id="d6954-189">Throw</span></span>|<span data-ttu-id="d6954-190">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="d6954-191">Asociación</span><span class="sxs-lookup"><span data-stu-id="d6954-191">Association</span></span><br /><br /> <span data-ttu-id="d6954-192">type</span><span class="sxs-lookup"><span data-stu-id="d6954-192">type</span></span>|<span data-ttu-id="d6954-193">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-194">Throw</span><span class="sxs-lookup"><span data-stu-id="d6954-194">Throw</span></span>|<span data-ttu-id="d6954-195">Throw</span><span class="sxs-lookup"><span data-stu-id="d6954-195">Throw</span></span>|<span data-ttu-id="d6954-196">Throw</span><span class="sxs-lookup"><span data-stu-id="d6954-196">Throw</span></span>|<span data-ttu-id="d6954-197">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-198">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="d6954-199">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="d6954-200"><sup>1</sup>las referencias de las instancias del tipo de entidad dado se comparan implícitamente, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d6954-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="d6954-201">Una instancia de entidad no se puede comparar con una referencia explícita.</span><span class="sxs-lookup"><span data-stu-id="d6954-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="d6954-202">Si se intenta, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="d6954-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="d6954-203">Por ejemplo, la siguiente consulta iniciaría una excepción:</span><span class="sxs-lookup"><span data-stu-id="d6954-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="d6954-204"><sup>2</sup>propiedades de tipos complejos se simplifican antes de enviarse al almacén, por lo que lleguen a ser comparables (siempre que todas sus propiedades sean comparables).</span><span class="sxs-lookup"><span data-stu-id="d6954-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="d6954-205">Consulte también <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="d6954-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="d6954-206"><sup>3</sup>en tiempo de ejecución de Entity Framework detecta un caso no admitido y se inicia una excepción significativa sin activar el proveedor o almacén.</span><span class="sxs-lookup"><span data-stu-id="d6954-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="d6954-207"><sup>4</sup>se realiza un intento para comparar todas las propiedades.</span><span class="sxs-lookup"><span data-stu-id="d6954-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="d6954-208">Si hay una propiedad que es de un tipo no comparable, como text, ntext o image, se podría iniciar una excepción de servidor.</span><span class="sxs-lookup"><span data-stu-id="d6954-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="d6954-209"><sup>5</sup>se comparan todos los elementos individuales de las referencias (Esto incluye el nombre del conjunto de entidades y todas las propiedades claves del tipo de entidad).</span><span class="sxs-lookup"><span data-stu-id="d6954-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6954-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6954-210">See Also</span></span>  
 [<span data-ttu-id="d6954-211">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d6954-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
