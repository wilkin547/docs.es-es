---
title: "Semántica de comparación (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: e20d47e0ae97067d2dcafcf929f717598d4e3e80
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="489c7-102">Semántica de comparación (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="489c7-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="489c7-103">El uso de cualquiera de los operadores de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguientes implica la comparación de las instancias de tipo:</span><span class="sxs-lookup"><span data-stu-id="489c7-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="489c7-104">Comparación explícita</span><span class="sxs-lookup"><span data-stu-id="489c7-104">Explicit comparison</span></span>  
 <span data-ttu-id="489c7-105">Operaciones de igualdad:</span><span class="sxs-lookup"><span data-stu-id="489c7-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="489c7-106">!=</span><span class="sxs-lookup"><span data-stu-id="489c7-106">!=</span></span>  
  
 <span data-ttu-id="489c7-107">Operaciones de ordenación:</span><span class="sxs-lookup"><span data-stu-id="489c7-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 <span data-ttu-id="489c7-108">Operaciones de nulabilidad:</span><span class="sxs-lookup"><span data-stu-id="489c7-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="489c7-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="489c7-109">IS NULL</span></span>  
  
-   <span data-ttu-id="489c7-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="489c7-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="489c7-111">Distinción explícita</span><span class="sxs-lookup"><span data-stu-id="489c7-111">Explicit distinction</span></span>  
 <span data-ttu-id="489c7-112">Distinción de igualdad:</span><span class="sxs-lookup"><span data-stu-id="489c7-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="489c7-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="489c7-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="489c7-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="489c7-114">GROUP BY</span></span>  
  
 <span data-ttu-id="489c7-115">Distinción de ordenación:</span><span class="sxs-lookup"><span data-stu-id="489c7-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="489c7-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="489c7-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="489c7-117">Distinción implícita</span><span class="sxs-lookup"><span data-stu-id="489c7-117">Implicit distinction</span></span>  
 <span data-ttu-id="489c7-118">Operaciones y predicados de conjuntos (igualdad):</span><span class="sxs-lookup"><span data-stu-id="489c7-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="489c7-119">UNION</span><span class="sxs-lookup"><span data-stu-id="489c7-119">UNION</span></span>  
  
-   <span data-ttu-id="489c7-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="489c7-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="489c7-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="489c7-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="489c7-122">SET</span><span class="sxs-lookup"><span data-stu-id="489c7-122">SET</span></span>  
  
-   <span data-ttu-id="489c7-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="489c7-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="489c7-124">Predicados de elementos (igualdad):</span><span class="sxs-lookup"><span data-stu-id="489c7-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="489c7-125">IN</span><span class="sxs-lookup"><span data-stu-id="489c7-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="489c7-126">Combinaciones admitidas</span><span class="sxs-lookup"><span data-stu-id="489c7-126">Supported Combinations</span></span>  
 <span data-ttu-id="489c7-127">En la tabla siguiente se muestran todas las combinaciones admitidas de los operadores de comparación para cada clase de tipo:</span><span class="sxs-lookup"><span data-stu-id="489c7-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="489c7-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="489c7-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="489c7-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="489c7-129">**!=**</span></span>|<span data-ttu-id="489c7-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="489c7-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="489c7-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="489c7-131">**DISTINCT**</span></span>|<span data-ttu-id="489c7-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="489c7-132">**UNION**</span></span><br /><br /> <span data-ttu-id="489c7-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="489c7-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="489c7-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="489c7-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="489c7-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="489c7-135">**SET**</span></span><br /><br /> <span data-ttu-id="489c7-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="489c7-136">**OVERLAPS**</span></span>|<span data-ttu-id="489c7-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="489c7-137">**IN**</span></span>|<span data-ttu-id="489c7-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="489c7-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="489c7-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="489c7-139">**>   >=**</span></span>|<span data-ttu-id="489c7-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="489c7-140">**ORDER BY**</span></span>|<span data-ttu-id="489c7-141">**ES NULL**</span><span class="sxs-lookup"><span data-stu-id="489c7-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="489c7-142">**NO ES NULO**</span><span class="sxs-lookup"><span data-stu-id="489c7-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="489c7-143">Tipo de entidad</span><span class="sxs-lookup"><span data-stu-id="489c7-143">Entity type</span></span>|<span data-ttu-id="489c7-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="489c7-145">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="489c7-146">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="489c7-147">Todas las propiedades<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="489c7-148">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-149">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="489c7-151">Tipo complejo</span><span class="sxs-lookup"><span data-stu-id="489c7-151">Complex type</span></span>|<span data-ttu-id="489c7-152">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-153">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-154">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-155">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-156">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-157">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-158">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="489c7-159">Fila</span><span class="sxs-lookup"><span data-stu-id="489c7-159">Row</span></span>|<span data-ttu-id="489c7-160">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="489c7-161">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="489c7-162">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="489c7-163">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-164">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-165">Todas las propiedades<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="489c7-166">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="489c7-167">Tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="489c7-167">Primitive type</span></span>|<span data-ttu-id="489c7-168">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="489c7-168">Provider-specific</span></span>|<span data-ttu-id="489c7-169">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="489c7-169">Provider-specific</span></span>|<span data-ttu-id="489c7-170">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="489c7-170">Provider-specific</span></span>|<span data-ttu-id="489c7-171">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="489c7-171">Provider-specific</span></span>|<span data-ttu-id="489c7-172">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="489c7-172">Provider-specific</span></span>|<span data-ttu-id="489c7-173">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="489c7-173">Provider-specific</span></span>|<span data-ttu-id="489c7-174">Depende del proveedor</span><span class="sxs-lookup"><span data-stu-id="489c7-174">Provider-specific</span></span>|  
|<span data-ttu-id="489c7-175">Conjunto múltiple</span><span class="sxs-lookup"><span data-stu-id="489c7-175">Multiset</span></span>|<span data-ttu-id="489c7-176">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-177">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-178">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-179">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-180">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-181">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-182">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="489c7-183">Ref</span><span class="sxs-lookup"><span data-stu-id="489c7-183">Ref</span></span>|<span data-ttu-id="489c7-184">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="489c7-185">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="489c7-186">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="489c7-187">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="489c7-188">Throw</span><span class="sxs-lookup"><span data-stu-id="489c7-188">Throw</span></span>|<span data-ttu-id="489c7-189">Throw</span><span class="sxs-lookup"><span data-stu-id="489c7-189">Throw</span></span>|<span data-ttu-id="489c7-190">Sí<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="489c7-191">Asociación</span><span class="sxs-lookup"><span data-stu-id="489c7-191">Association</span></span><br /><br /> <span data-ttu-id="489c7-192">type</span><span class="sxs-lookup"><span data-stu-id="489c7-192">type</span></span>|<span data-ttu-id="489c7-193">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-194">Throw</span><span class="sxs-lookup"><span data-stu-id="489c7-194">Throw</span></span>|<span data-ttu-id="489c7-195">Throw</span><span class="sxs-lookup"><span data-stu-id="489c7-195">Throw</span></span>|<span data-ttu-id="489c7-196">Throw</span><span class="sxs-lookup"><span data-stu-id="489c7-196">Throw</span></span>|<span data-ttu-id="489c7-197">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-198">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="489c7-199">Iniciar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="489c7-200"><sup>1</sup>las referencias de las instancias del tipo de entidad dado se comparan implícitamente, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="489c7-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="489c7-201">Una instancia de entidad no se puede comparar con una referencia explícita.</span><span class="sxs-lookup"><span data-stu-id="489c7-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="489c7-202">Si se intenta, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="489c7-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="489c7-203">Por ejemplo, la siguiente consulta iniciaría una excepción:</span><span class="sxs-lookup"><span data-stu-id="489c7-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="489c7-204"><sup>2</sup>propiedades de tipos complejos se simplifican antes de enviarse al almacén, por lo que lleguen a ser comparables (siempre que todas sus propiedades sean comparables).</span><span class="sxs-lookup"><span data-stu-id="489c7-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="489c7-205">Consulte también <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="489c7-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="489c7-206"><sup>3</sup>en tiempo de ejecución de Entity Framework detecta un caso no admitido y se inicia una excepción significativa sin activar el proveedor o almacén.</span><span class="sxs-lookup"><span data-stu-id="489c7-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="489c7-207"><sup>4</sup>se realiza un intento para comparar todas las propiedades.</span><span class="sxs-lookup"><span data-stu-id="489c7-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="489c7-208">Si hay una propiedad que es de un tipo no comparable, como text, ntext o image, se podría iniciar una excepción de servidor.</span><span class="sxs-lookup"><span data-stu-id="489c7-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="489c7-209"><sup>5</sup>se comparan todos los elementos individuales de las referencias (Esto incluye el nombre del conjunto de entidades y todas las propiedades claves del tipo de entidad).</span><span class="sxs-lookup"><span data-stu-id="489c7-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="489c7-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="489c7-210">See Also</span></span>  
 [<span data-ttu-id="489c7-211">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="489c7-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
