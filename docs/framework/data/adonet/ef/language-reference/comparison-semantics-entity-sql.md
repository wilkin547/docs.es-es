---
title: Semántica de comparación (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 6b4c4177ebd6c45e00a1ac7774e40a43e0c14a74
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083340"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="6e89c-102">Semántica de comparación (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6e89c-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="6e89c-103">El uso de cualquiera de los operadores de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguientes implica la comparación de las instancias de tipo:</span><span class="sxs-lookup"><span data-stu-id="6e89c-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="6e89c-104">Comparación explícita</span><span class="sxs-lookup"><span data-stu-id="6e89c-104">Explicit comparison</span></span>  
 <span data-ttu-id="6e89c-105">Operaciones de igualdad:</span><span class="sxs-lookup"><span data-stu-id="6e89c-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="6e89c-106">!=</span><span class="sxs-lookup"><span data-stu-id="6e89c-106">!=</span></span>  
  
 <span data-ttu-id="6e89c-107">Operaciones de ordenación:</span><span class="sxs-lookup"><span data-stu-id="6e89c-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 <span data-ttu-id="6e89c-108">Operaciones de nulabilidad:</span><span class="sxs-lookup"><span data-stu-id="6e89c-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="6e89c-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="6e89c-109">IS NULL</span></span>  
  
-   <span data-ttu-id="6e89c-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6e89c-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="6e89c-111">Distinción explícita</span><span class="sxs-lookup"><span data-stu-id="6e89c-111">Explicit distinction</span></span>  
 <span data-ttu-id="6e89c-112">Distinción de igualdad:</span><span class="sxs-lookup"><span data-stu-id="6e89c-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="6e89c-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="6e89c-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="6e89c-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="6e89c-114">GROUP BY</span></span>  
  
 <span data-ttu-id="6e89c-115">Distinción de ordenación:</span><span class="sxs-lookup"><span data-stu-id="6e89c-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="6e89c-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="6e89c-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="6e89c-117">Distinción implícita</span><span class="sxs-lookup"><span data-stu-id="6e89c-117">Implicit distinction</span></span>  
 <span data-ttu-id="6e89c-118">Operaciones y predicados de conjuntos (igualdad):</span><span class="sxs-lookup"><span data-stu-id="6e89c-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="6e89c-119">UNION</span><span class="sxs-lookup"><span data-stu-id="6e89c-119">UNION</span></span>  
  
-   <span data-ttu-id="6e89c-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="6e89c-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="6e89c-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="6e89c-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="6e89c-122">SET</span><span class="sxs-lookup"><span data-stu-id="6e89c-122">SET</span></span>  
  
-   <span data-ttu-id="6e89c-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="6e89c-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="6e89c-124">Predicados de elementos (igualdad):</span><span class="sxs-lookup"><span data-stu-id="6e89c-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="6e89c-125">IN</span><span class="sxs-lookup"><span data-stu-id="6e89c-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="6e89c-126">Combinaciones admitidas</span><span class="sxs-lookup"><span data-stu-id="6e89c-126">Supported Combinations</span></span>  
 <span data-ttu-id="6e89c-127">En la tabla siguiente se muestran todas las combinaciones admitidas de los operadores de comparación para cada clase de tipo:</span><span class="sxs-lookup"><span data-stu-id="6e89c-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="6e89c-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="6e89c-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="6e89c-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="6e89c-129">**!=**</span></span>|<span data-ttu-id="6e89c-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="6e89c-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="6e89c-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="6e89c-131">**DISTINCT**</span></span>|<span data-ttu-id="6e89c-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="6e89c-132">**UNION**</span></span><br /><br /> <span data-ttu-id="6e89c-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="6e89c-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="6e89c-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="6e89c-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="6e89c-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="6e89c-135">**SET**</span></span><br /><br /> <span data-ttu-id="6e89c-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="6e89c-136">**OVERLAPS**</span></span>|<span data-ttu-id="6e89c-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="6e89c-137">**IN**</span></span>|<span data-ttu-id="6e89c-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="6e89c-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="6e89c-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="6e89c-139">**>   >=**</span></span>|<span data-ttu-id="6e89c-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="6e89c-140">**ORDER BY**</span></span>|<span data-ttu-id="6e89c-141">**ES NULL**</span><span class="sxs-lookup"><span data-stu-id="6e89c-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="6e89c-142">**NO ES NULL**</span><span class="sxs-lookup"><span data-stu-id="6e89c-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="6e89c-143">Tipo de entidad</span><span class="sxs-lookup"><span data-stu-id="6e89c-143">Entity type</span></span>|<span data-ttu-id="6e89c-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="6e89c-145">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="6e89c-146">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="6e89c-147">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="6e89c-148">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-149">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="6e89c-151">Tipo complejo</span><span class="sxs-lookup"><span data-stu-id="6e89c-151">Complex type</span></span>|<span data-ttu-id="6e89c-152">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-153">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-154">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-155">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-156">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-157">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-158">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="6e89c-159">Fila</span><span class="sxs-lookup"><span data-stu-id="6e89c-159">Row</span></span>|<span data-ttu-id="6e89c-160">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="6e89c-161">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="6e89c-162">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="6e89c-163">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-164">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-165">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="6e89c-166">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="6e89c-167">Tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="6e89c-167">Primitive type</span></span>|<span data-ttu-id="6e89c-168">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="6e89c-168">Provider-specific</span></span>|<span data-ttu-id="6e89c-169">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="6e89c-169">Provider-specific</span></span>|<span data-ttu-id="6e89c-170">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="6e89c-170">Provider-specific</span></span>|<span data-ttu-id="6e89c-171">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="6e89c-171">Provider-specific</span></span>|<span data-ttu-id="6e89c-172">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="6e89c-172">Provider-specific</span></span>|<span data-ttu-id="6e89c-173">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="6e89c-173">Provider-specific</span></span>|<span data-ttu-id="6e89c-174">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="6e89c-174">Provider-specific</span></span>|  
|<span data-ttu-id="6e89c-175">Conjunto múltiple</span><span class="sxs-lookup"><span data-stu-id="6e89c-175">Multiset</span></span>|<span data-ttu-id="6e89c-176">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-177">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-178">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-179">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-180">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-181">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-182">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="6e89c-183">Ref</span><span class="sxs-lookup"><span data-stu-id="6e89c-183">Ref</span></span>|<span data-ttu-id="6e89c-184">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="6e89c-185">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="6e89c-186">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="6e89c-187">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="6e89c-188">Throw</span><span class="sxs-lookup"><span data-stu-id="6e89c-188">Throw</span></span>|<span data-ttu-id="6e89c-189">Throw</span><span class="sxs-lookup"><span data-stu-id="6e89c-189">Throw</span></span>|<span data-ttu-id="6e89c-190">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="6e89c-191">Asociación</span><span class="sxs-lookup"><span data-stu-id="6e89c-191">Association</span></span><br /><br /> <span data-ttu-id="6e89c-192">type</span><span class="sxs-lookup"><span data-stu-id="6e89c-192">type</span></span>|<span data-ttu-id="6e89c-193">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-194">Throw</span><span class="sxs-lookup"><span data-stu-id="6e89c-194">Throw</span></span>|<span data-ttu-id="6e89c-195">Throw</span><span class="sxs-lookup"><span data-stu-id="6e89c-195">Throw</span></span>|<span data-ttu-id="6e89c-196">Throw</span><span class="sxs-lookup"><span data-stu-id="6e89c-196">Throw</span></span>|<span data-ttu-id="6e89c-197">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-198">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="6e89c-199">Producir<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="6e89c-200"><sup>1</sup>las referencias de las instancias del tipo de entidad dado se comparan implícitamente, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6e89c-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="6e89c-201">Una instancia de entidad no se puede comparar con una referencia explícita.</span><span class="sxs-lookup"><span data-stu-id="6e89c-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="6e89c-202">Si se intenta, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="6e89c-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="6e89c-203">Por ejemplo, la siguiente consulta iniciaría una excepción:</span><span class="sxs-lookup"><span data-stu-id="6e89c-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="6e89c-204"><sup>2</sup>propiedades de tipos complejos se simplifican antes de que se envían a la tienda, por lo que lleguen a ser comparables (siempre que todas sus propiedades sean comparables).</span><span class="sxs-lookup"><span data-stu-id="6e89c-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="6e89c-205">Consulte también <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="6e89c-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="6e89c-206"><sup>3</sup>en tiempo de ejecución de Entity Framework detecta un caso no admitido y se inicia una excepción significativa sin activar el proveedor o almacén.</span><span class="sxs-lookup"><span data-stu-id="6e89c-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="6e89c-207"><sup>4</sup>se realiza un intento para comparar todas las propiedades.</span><span class="sxs-lookup"><span data-stu-id="6e89c-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="6e89c-208">Si hay una propiedad que es de un tipo no comparable, como text, ntext o image, se podría iniciar una excepción de servidor.</span><span class="sxs-lookup"><span data-stu-id="6e89c-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="6e89c-209"><sup>5</sup>se comparan todos los elementos individuales de las referencias (Esto incluye el nombre del conjunto de entidades y todas las propiedades claves del tipo de entidad).</span><span class="sxs-lookup"><span data-stu-id="6e89c-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e89c-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e89c-210">See also</span></span>

- [<span data-ttu-id="6e89c-211">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6e89c-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
