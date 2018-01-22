---
title: Lenguaje Entity SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a0caf2670a90db0e44ad1f51689b6086313de274
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="entity-sql-language"></a><span data-ttu-id="206bb-102">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="206bb-102">Entity SQL Language</span></span>
<span data-ttu-id="206bb-103">Entity SQL es un lenguaje de consulta independiente del almacenamiento que se parece a SQL.</span><span class="sxs-lookup"><span data-stu-id="206bb-103">Entity SQL is a storage-independent query language that is similar to SQL.</span></span> <span data-ttu-id="206bb-104">Entity SQL permite consultar los datos de la entidad, ya sea como objetos o en un formato tabular.</span><span class="sxs-lookup"><span data-stu-id="206bb-104">Entity SQL allows you to query entity data, either as objects or in a tabular form.</span></span> <span data-ttu-id="206bb-105">Considere el uso de Entity SQL en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="206bb-105">You should consider using Entity SQL in the following cases:</span></span>  
  
-   <span data-ttu-id="206bb-106">Cuando una consulta se debe construir dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="206bb-106">When a query must be dynamically constructed at runtime.</span></span> <span data-ttu-id="206bb-107">En este caso, también debe considerar el uso de los métodos del generador de consultas de <xref:System.Data.Objects.ObjectQuery%601> en lugar de construir una cadena de consulta de Entity SQL en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="206bb-107">In this case, you should also consider using the query builder methods of <xref:System.Data.Objects.ObjectQuery%601> instead of constructing an Entity SQL query string at runtime.</span></span>  
  
-   <span data-ttu-id="206bb-108">Si desea definir una consulta como parte de la definición del modelo.</span><span class="sxs-lookup"><span data-stu-id="206bb-108">When you want to define a query as part of the model definition.</span></span> <span data-ttu-id="206bb-109">Entity SQL solo se admite en un modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="206bb-109">Only Entity SQL is supported in a data model.</span></span> <span data-ttu-id="206bb-110">Para obtener más información, vea [elemento QueryView (MSL)](http://msdn.microsoft.com/library/f0426b34-45cb-4fd7-9777-e0570c5e0e80)</span><span class="sxs-lookup"><span data-stu-id="206bb-110">For more information, see [QueryView Element (MSL)](http://msdn.microsoft.com/library/f0426b34-45cb-4fd7-9777-e0570c5e0e80)</span></span>  
  
-   <span data-ttu-id="206bb-111">Si utiliza EntityClient para devolver los datos de la entidad de solo lectura como conjuntos de filas utilizando <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="206bb-111">When using EntityClient to return read-only entity data as rowsets using a <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="206bb-112">Para obtener más información, consulte [proveedor de EntityClient para Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span><span class="sxs-lookup"><span data-stu-id="206bb-112">For more information, see [EntityClient Provider for the Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span></span>  
  
-   <span data-ttu-id="206bb-113">Si ya es un experto en lenguajes de consulta basados en SQL, Entity SQL puede parecerle el más natural.</span><span class="sxs-lookup"><span data-stu-id="206bb-113">If you are already an expert in SQL-based query languages, Entity SQL may seem the most natural to you.</span></span>  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a><span data-ttu-id="206bb-114">Utilizar Entity SQL con el proveedor de EntityClient</span><span class="sxs-lookup"><span data-stu-id="206bb-114">Using Entity SQL with the EntityClient provider</span></span>  
 <span data-ttu-id="206bb-115">Si desea utilizar Entity SQL con el proveedor de EntityClient, consulte los siguientes temas para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="206bb-115">If you want to use Entity SQL with the EntityClient provider, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="206bb-116">Proveedor de EntityClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="206bb-116">EntityClient Provider for the Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [<span data-ttu-id="206bb-117">Compilación de una cadena de conexión EntityConnection</span><span class="sxs-lookup"><span data-stu-id="206bb-117">How to: Build an EntityConnection Connection String</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [<span data-ttu-id="206bb-118">Ejecución de una consulta que devuelve resultados PrimitiveType</span><span class="sxs-lookup"><span data-stu-id="206bb-118">How to: Execute a Query that Returns PrimitiveType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [<span data-ttu-id="206bb-119">Ejecución de una consulta que devuelve resultados StructuralType</span><span class="sxs-lookup"><span data-stu-id="206bb-119">How to: Execute a Query that Returns StructuralType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [<span data-ttu-id="206bb-120">Ejecución de una consulta que devuelve resultados RefType</span><span class="sxs-lookup"><span data-stu-id="206bb-120">How to: Execute a Query that Returns RefType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [<span data-ttu-id="206bb-121">Ejecución de una consulta que devuelve tipos complejos</span><span class="sxs-lookup"><span data-stu-id="206bb-121">How to: Execute a Query that Returns Complex Types</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [<span data-ttu-id="206bb-122">Ejecución de una consulta que devuelve colecciones anidadas</span><span class="sxs-lookup"><span data-stu-id="206bb-122">How to: Execute a Query that Returns Nested Collections</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [<span data-ttu-id="206bb-123">Ejecución de una consulta parametrizada de Entity SQL usando EntityCommand</span><span class="sxs-lookup"><span data-stu-id="206bb-123">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [<span data-ttu-id="206bb-124">Ejecución de un procedimiento almacenado parametrizado usando EntityCommand</span><span class="sxs-lookup"><span data-stu-id="206bb-124">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [<span data-ttu-id="206bb-125">Ejecución de una consulta polimórfica</span><span class="sxs-lookup"><span data-stu-id="206bb-125">How to: Execute a Polymorphic Query</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [<span data-ttu-id="206bb-126">Navegación por las relaciones con el operador Navigate</span><span class="sxs-lookup"><span data-stu-id="206bb-126">How to: Navigate Relationships with the Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a><span data-ttu-id="206bb-127">Utilizar Entity SQL con consultas de objeto</span><span class="sxs-lookup"><span data-stu-id="206bb-127">Using Entity SQL with object queries</span></span>  
 <span data-ttu-id="206bb-128">Si desea utilizar Entity SQL con consultas de objeto, consulte los siguientes temas para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="206bb-128">If you want to use Entity SQL with object queries, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="206bb-129">Cómo: ejecutar una consulta que devuelve objetos de tipo de entidad</span><span class="sxs-lookup"><span data-stu-id="206bb-129">How to: Execute a Query that Returns Entity Type Objects</span></span>](http://msdn.microsoft.com/library/f73e137d-1534-42bb-9e31-99ca42c19b48)  
  
 [<span data-ttu-id="206bb-130">Cómo: ejecutar una consulta con parámetros</span><span class="sxs-lookup"><span data-stu-id="206bb-130">How to: Execute a Parameterized Query</span></span>](http://msdn.microsoft.com/library/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
  
 [<span data-ttu-id="206bb-131">Cómo: navegar por las relaciones mediante propiedades de navegación</span><span class="sxs-lookup"><span data-stu-id="206bb-131">How to: Navigate Relationships Using Navigation Properties</span></span>](http://msdn.microsoft.com/library/b1d71c7d-16a7-4b46-96ac-690176bd5057)  
  
 [<span data-ttu-id="206bb-132">Cómo: llamar a una función definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="206bb-132">How to: Call a User-Defined Function</span></span>](http://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)  
  
 [<span data-ttu-id="206bb-133">Cómo: filtrar datos</span><span class="sxs-lookup"><span data-stu-id="206bb-133">How to: Filter Data</span></span>](http://msdn.microsoft.com/library/776f8556-3350-4572-804a-b1513515c1b2)  
  
 [<span data-ttu-id="206bb-134">Cómo: ordenar datos</span><span class="sxs-lookup"><span data-stu-id="206bb-134">How to: Sort Data</span></span>](http://msdn.microsoft.com/library/c05f2506-cb9d-4ebc-822b-300042ad53e7)  
  
 [<span data-ttu-id="206bb-135">Cómo: agrupar datos</span><span class="sxs-lookup"><span data-stu-id="206bb-135">How to: Group Data</span></span>](http://msdn.microsoft.com/library/df801d9d-9a8a-4157-97a6-5016b18998e1)  
  
 [<span data-ttu-id="206bb-136">Cómo: agregar datos</span><span class="sxs-lookup"><span data-stu-id="206bb-136">How to: Aggregate Data</span></span>](http://msdn.microsoft.com/library/4cf04ce8-3c0f-4f88-9d97-8fac8622598d)  
  
 [<span data-ttu-id="206bb-137">Cómo: ejecutar una consulta que devuelve objetos de tipo anónimo</span><span class="sxs-lookup"><span data-stu-id="206bb-137">How to: Execute a Query that Returns Anonymous Type Objects</span></span>](http://msdn.microsoft.com/library/3b264025-e911-4d73-90ce-992d2b9d189d)  
  
 [<span data-ttu-id="206bb-138">Cómo: ejecutar una consulta que devuelve una colección de tipos primitivos</span><span class="sxs-lookup"><span data-stu-id="206bb-138">How to: Execute a Query that Returns a Collection of Primitive Types</span></span>](http://msdn.microsoft.com/library/115b52c0-4f27-4253-8991-284b450000b5)  
  
 [<span data-ttu-id="206bb-139">Cómo: consultar objetos relacionados en una EntityCollection</span><span class="sxs-lookup"><span data-stu-id="206bb-139">How to: Query Related Objects in an EntityCollection</span></span>](http://msdn.microsoft.com/library/11ce946f-16f8-4c1d-9d80-f740853807ba)  
  
 [<span data-ttu-id="206bb-140">Cómo: ordenar la unión de dos consultas</span><span class="sxs-lookup"><span data-stu-id="206bb-140">How to: Order the Union of Two Queries</span></span>](http://msdn.microsoft.com/library/853c583a-eaba-4400-830d-be974e735313)  
  
 [<span data-ttu-id="206bb-141">Cómo: resultados de la página a través de consulta</span><span class="sxs-lookup"><span data-stu-id="206bb-141">How to: Page Through Query Results</span></span>](http://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
  
## <a name="in-this-section"></a><span data-ttu-id="206bb-142">En esta sección</span><span class="sxs-lookup"><span data-stu-id="206bb-142">In This Section</span></span>  
 [<span data-ttu-id="206bb-143">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="206bb-143">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [<span data-ttu-id="206bb-144">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="206bb-144">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="206bb-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="206bb-145">See Also</span></span>  
 [<span data-ttu-id="206bb-146">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="206bb-146">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)  
 [<span data-ttu-id="206bb-147">Referencia del lenguaje</span><span class="sxs-lookup"><span data-stu-id="206bb-147">Language Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
