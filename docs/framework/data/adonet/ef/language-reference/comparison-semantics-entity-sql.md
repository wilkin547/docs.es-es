---
description: 'Más información sobre: semántica de comparación (Entity SQL)'
title: Semántica de comparación (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: b1c832cb6f2903073b1c6be806c73823b1f4a220
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786438"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="5c643-103">Semántica de comparación (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5c643-103">Comparison Semantics (Entity SQL)</span></span>

<span data-ttu-id="5c643-104">El uso de cualquiera de los operadores de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguientes implica la comparación de las instancias de tipo:</span><span class="sxs-lookup"><span data-stu-id="5c643-104">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="5c643-105">Comparación explícita</span><span class="sxs-lookup"><span data-stu-id="5c643-105">Explicit comparison</span></span>  

 <span data-ttu-id="5c643-106">Operaciones de igualdad:</span><span class="sxs-lookup"><span data-stu-id="5c643-106">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="5c643-107">!=</span><span class="sxs-lookup"><span data-stu-id="5c643-107">!=</span></span>  
  
 <span data-ttu-id="5c643-108">Operaciones de ordenación:</span><span class="sxs-lookup"><span data-stu-id="5c643-108">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="5c643-109">Operaciones de nulabilidad:</span><span class="sxs-lookup"><span data-stu-id="5c643-109">Nullability operations:</span></span>  
  
- <span data-ttu-id="5c643-110">IS NULL</span><span class="sxs-lookup"><span data-stu-id="5c643-110">IS NULL</span></span>  
  
- <span data-ttu-id="5c643-111">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5c643-111">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="5c643-112">Distinción explícita</span><span class="sxs-lookup"><span data-stu-id="5c643-112">Explicit distinction</span></span>  

 <span data-ttu-id="5c643-113">Distinción de igualdad:</span><span class="sxs-lookup"><span data-stu-id="5c643-113">Equality distinction:</span></span>  
  
- <span data-ttu-id="5c643-114">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="5c643-114">DISTINCT</span></span>  
  
- <span data-ttu-id="5c643-115">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="5c643-115">GROUP BY</span></span>  
  
 <span data-ttu-id="5c643-116">Distinción de ordenación:</span><span class="sxs-lookup"><span data-stu-id="5c643-116">Ordering distinction:</span></span>  
  
- <span data-ttu-id="5c643-117">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="5c643-117">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="5c643-118">Distinción implícita</span><span class="sxs-lookup"><span data-stu-id="5c643-118">Implicit distinction</span></span>  

 <span data-ttu-id="5c643-119">Operaciones y predicados de conjuntos (igualdad):</span><span class="sxs-lookup"><span data-stu-id="5c643-119">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="5c643-120">UNION</span><span class="sxs-lookup"><span data-stu-id="5c643-120">UNION</span></span>  
  
- <span data-ttu-id="5c643-121">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="5c643-121">INTERSECT</span></span>  
  
- <span data-ttu-id="5c643-122">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="5c643-122">EXCEPT</span></span>  
  
- <span data-ttu-id="5c643-123">SET</span><span class="sxs-lookup"><span data-stu-id="5c643-123">SET</span></span>  
  
- <span data-ttu-id="5c643-124">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="5c643-124">OVERLAPS</span></span>  
  
 <span data-ttu-id="5c643-125">Predicados de elementos (igualdad):</span><span class="sxs-lookup"><span data-stu-id="5c643-125">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="5c643-126">IN</span><span class="sxs-lookup"><span data-stu-id="5c643-126">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="5c643-127">Combinaciones admitidas</span><span class="sxs-lookup"><span data-stu-id="5c643-127">Supported Combinations</span></span>  

 <span data-ttu-id="5c643-128">En la tabla siguiente se muestran todas las combinaciones admitidas de los operadores de comparación para cada clase de tipo:</span><span class="sxs-lookup"><span data-stu-id="5c643-128">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="5c643-129">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5c643-129">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="5c643-130">**!=**</span><span class="sxs-lookup"><span data-stu-id="5c643-130">**!=**</span></span>|<span data-ttu-id="5c643-131">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="5c643-131">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="5c643-132">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="5c643-132">**DISTINCT**</span></span>|<span data-ttu-id="5c643-133">**UNION**</span><span class="sxs-lookup"><span data-stu-id="5c643-133">**UNION**</span></span><br /><br /> <span data-ttu-id="5c643-134">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="5c643-134">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="5c643-135">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="5c643-135">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="5c643-136">**SET**</span><span class="sxs-lookup"><span data-stu-id="5c643-136">**SET**</span></span><br /><br /> <span data-ttu-id="5c643-137">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="5c643-137">**OVERLAPS**</span></span>|<span data-ttu-id="5c643-138">**IN**</span><span class="sxs-lookup"><span data-stu-id="5c643-138">**IN**</span></span>|<span data-ttu-id="5c643-139">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="5c643-139">**<   <=**</span></span><br /><br /> <span data-ttu-id="5c643-140">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="5c643-140">**>   >=**</span></span>|<span data-ttu-id="5c643-141">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="5c643-141">**ORDER BY**</span></span>|<span data-ttu-id="5c643-142">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="5c643-142">**IS NULL**</span></span><br /><br /> <span data-ttu-id="5c643-143">**NO ES NULL**</span><span class="sxs-lookup"><span data-stu-id="5c643-143">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="5c643-144">Tipo de entidad</span><span class="sxs-lookup"><span data-stu-id="5c643-144">Entity type</span></span>|<span data-ttu-id="5c643-145">Referencia<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-145">Ref<sup>1</sup></span></span>|<span data-ttu-id="5c643-146">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="5c643-147">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="5c643-148">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-148">All properties<sup>2</sup></span></span>|<span data-ttu-id="5c643-149">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-150">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-150">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-151">Referencia<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-151">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="5c643-152">Tipo complejo</span><span class="sxs-lookup"><span data-stu-id="5c643-152">Complex type</span></span>|<span data-ttu-id="5c643-153">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-154">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-155">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-156">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-157">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-158">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-158">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-159">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-159">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="5c643-160">Row</span><span class="sxs-lookup"><span data-stu-id="5c643-160">Row</span></span>|<span data-ttu-id="5c643-161">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="5c643-162">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="5c643-163">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-163">All properties<sup>4</sup></span></span>|<span data-ttu-id="5c643-164">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-165">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-165">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-166">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-166">All properties<sup>4</sup></span></span>|<span data-ttu-id="5c643-167">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-167">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="5c643-168">Tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="5c643-168">Primitive type</span></span>|<span data-ttu-id="5c643-169">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="5c643-169">Provider-specific</span></span>|<span data-ttu-id="5c643-170">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="5c643-170">Provider-specific</span></span>|<span data-ttu-id="5c643-171">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="5c643-171">Provider-specific</span></span>|<span data-ttu-id="5c643-172">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="5c643-172">Provider-specific</span></span>|<span data-ttu-id="5c643-173">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="5c643-173">Provider-specific</span></span>|<span data-ttu-id="5c643-174">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="5c643-174">Provider-specific</span></span>|<span data-ttu-id="5c643-175">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="5c643-175">Provider-specific</span></span>|  
|<span data-ttu-id="5c643-176">Conjunto múltiple</span><span class="sxs-lookup"><span data-stu-id="5c643-176">Multiset</span></span>|<span data-ttu-id="5c643-177">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-178">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-179">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-180">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-181">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-182">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-182">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-183">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-183">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="5c643-184">Ref</span><span class="sxs-lookup"><span data-stu-id="5c643-184">Ref</span></span>|<span data-ttu-id="5c643-185">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="5c643-186">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="5c643-187">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="5c643-188">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-188">Yes<sup>5</sup></span></span>|<span data-ttu-id="5c643-189">Throw</span><span class="sxs-lookup"><span data-stu-id="5c643-189">Throw</span></span>|<span data-ttu-id="5c643-190">Throw</span><span class="sxs-lookup"><span data-stu-id="5c643-190">Throw</span></span>|<span data-ttu-id="5c643-191">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-191">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="5c643-192">Asociación</span><span class="sxs-lookup"><span data-stu-id="5c643-192">Association</span></span><br /><br /> <span data-ttu-id="5c643-193">type</span><span class="sxs-lookup"><span data-stu-id="5c643-193">type</span></span>|<span data-ttu-id="5c643-194">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-194">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-195">Throw</span><span class="sxs-lookup"><span data-stu-id="5c643-195">Throw</span></span>|<span data-ttu-id="5c643-196">Throw</span><span class="sxs-lookup"><span data-stu-id="5c643-196">Throw</span></span>|<span data-ttu-id="5c643-197">Throw</span><span class="sxs-lookup"><span data-stu-id="5c643-197">Throw</span></span>|<span data-ttu-id="5c643-198">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-199">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-199">Throw<sup>3</sup></span></span>|<span data-ttu-id="5c643-200">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-200">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="5c643-201"><sup>1</sup> Las referencias de las instancias de tipo de entidad dadas se comparan implícitamente, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c643-201"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="5c643-202">Una instancia de entidad no se puede comparar con una referencia explícita.</span><span class="sxs-lookup"><span data-stu-id="5c643-202">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="5c643-203">Si se intenta, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="5c643-203">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="5c643-204">Por ejemplo, la siguiente consulta iniciaría una excepción:</span><span class="sxs-lookup"><span data-stu-id="5c643-204">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="5c643-205"><sup>2</sup> Las propiedades de los tipos complejos se alisan antes de enviarse al almacén, por lo que son comparables (siempre y cuando todas sus propiedades sean comparables).</span><span class="sxs-lookup"><span data-stu-id="5c643-205"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="5c643-206">Vea también <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="5c643-206">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="5c643-207"><sup>3</sup> El entorno de tiempo de ejecución de Entity Framework detecta el caso no compatible y produce una excepción significativa sin tener que atraer al proveedor o almacén.</span><span class="sxs-lookup"><span data-stu-id="5c643-207"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="5c643-208"><sup>4</sup> Se ha intentado comparar todas las propiedades.</span><span class="sxs-lookup"><span data-stu-id="5c643-208"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="5c643-209">Si hay una propiedad que es de un tipo no comparable, como text, ntext o image, se podría iniciar una excepción de servidor.</span><span class="sxs-lookup"><span data-stu-id="5c643-209">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="5c643-210"><sup>5</sup> Se comparan todos los elementos individuales de las referencias (esto incluye el nombre del conjunto de entidades y todas las propiedades clave del tipo de entidad).</span><span class="sxs-lookup"><span data-stu-id="5c643-210"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c643-211">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c643-211">See also</span></span>

- [<span data-ttu-id="5c643-212">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5c643-212">Entity SQL Overview</span></span>](entity-sql-overview.md)
