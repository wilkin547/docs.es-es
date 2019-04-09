---
title: Lenguaje Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 09ec1a5518ec0847b54394449f32b3068c811577
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140938"
---
# <a name="entity-sql-language"></a><span data-ttu-id="a9b8f-102">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a9b8f-102">Entity SQL Language</span></span>
<span data-ttu-id="a9b8f-103">Entity SQL es un lenguaje de consulta independiente del almacenamiento que se parece a SQL.</span><span class="sxs-lookup"><span data-stu-id="a9b8f-103">Entity SQL is a storage-independent query language that is similar to SQL.</span></span> <span data-ttu-id="a9b8f-104">Entity SQL permite consultar los datos de la entidad, ya sea como objetos o en un formato tabular.</span><span class="sxs-lookup"><span data-stu-id="a9b8f-104">Entity SQL allows you to query entity data, either as objects or in a tabular form.</span></span> <span data-ttu-id="a9b8f-105">Considere el uso de Entity SQL en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="a9b8f-105">You should consider using Entity SQL in the following cases:</span></span>  
  
-   <span data-ttu-id="a9b8f-106">Cuando una consulta se debe construir dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a9b8f-106">When a query must be dynamically constructed at runtime.</span></span> <span data-ttu-id="a9b8f-107">En este caso, también debe considerar el uso de los métodos del generador de consultas de <xref:System.Data.Objects.ObjectQuery%601> en lugar de construir una cadena de consulta de Entity SQL en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a9b8f-107">In this case, you should also consider using the query builder methods of <xref:System.Data.Objects.ObjectQuery%601> instead of constructing an Entity SQL query string at runtime.</span></span>  
  
-   <span data-ttu-id="a9b8f-108">Si desea definir una consulta como parte de la definición del modelo.</span><span class="sxs-lookup"><span data-stu-id="a9b8f-108">When you want to define a query as part of the model definition.</span></span> <span data-ttu-id="a9b8f-109">Entity SQL solo se admite en un modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="a9b8f-109">Only Entity SQL is supported in a data model.</span></span> <span data-ttu-id="a9b8f-110">Para obtener más información, consulte [elemento QueryView (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span><span class="sxs-lookup"><span data-stu-id="a9b8f-110">For more information, see [QueryView Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span></span>  
  
-   <span data-ttu-id="a9b8f-111">Si utiliza EntityClient para devolver los datos de la entidad de solo lectura como conjuntos de filas utilizando <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="a9b8f-111">When using EntityClient to return read-only entity data as rowsets using a <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="a9b8f-112">Para obtener más información, consulte [proveedor de EntityClient para Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span><span class="sxs-lookup"><span data-stu-id="a9b8f-112">For more information, see [EntityClient Provider for the Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span></span>  
  
-   <span data-ttu-id="a9b8f-113">Si ya es un experto en lenguajes de consulta basados en SQL, Entity SQL puede parecerle el más natural.</span><span class="sxs-lookup"><span data-stu-id="a9b8f-113">If you are already an expert in SQL-based query languages, Entity SQL may seem the most natural to you.</span></span>  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a><span data-ttu-id="a9b8f-114">Utilizar Entity SQL con el proveedor de EntityClient</span><span class="sxs-lookup"><span data-stu-id="a9b8f-114">Using Entity SQL with the EntityClient provider</span></span>  
 <span data-ttu-id="a9b8f-115">Si desea utilizar Entity SQL con el proveedor de EntityClient, consulte los siguientes temas para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="a9b8f-115">If you want to use Entity SQL with the EntityClient provider, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="a9b8f-116">Proveedor de EntityClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="a9b8f-116">EntityClient Provider for the Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [<span data-ttu-id="a9b8f-117">Filtrar para compilar una cadena de conexión EntityConnection</span><span class="sxs-lookup"><span data-stu-id="a9b8f-117">How to: Build an EntityConnection Connection String</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [<span data-ttu-id="a9b8f-118">Filtrar para ejecutar una consulta que devuelve resultados PrimitiveType</span><span class="sxs-lookup"><span data-stu-id="a9b8f-118">How to: Execute a Query that Returns PrimitiveType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [<span data-ttu-id="a9b8f-119">Filtrar para ejecutar una consulta que devuelve resultados StructuralType</span><span class="sxs-lookup"><span data-stu-id="a9b8f-119">How to: Execute a Query that Returns StructuralType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [<span data-ttu-id="a9b8f-120">Filtrar para ejecutar una consulta que devuelve resultados RefType</span><span class="sxs-lookup"><span data-stu-id="a9b8f-120">How to: Execute a Query that Returns RefType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [<span data-ttu-id="a9b8f-121">Filtrar para ejecutar una consulta que devuelve tipos complejos</span><span class="sxs-lookup"><span data-stu-id="a9b8f-121">How to: Execute a Query that Returns Complex Types</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [<span data-ttu-id="a9b8f-122">Filtrar para ejecutar una consulta que devuelve colecciones anidadas</span><span class="sxs-lookup"><span data-stu-id="a9b8f-122">How to: Execute a Query that Returns Nested Collections</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [<span data-ttu-id="a9b8f-123">Filtrar para ejecutar una consulta parametrizada de Entity SQL mediante EntityCommand</span><span class="sxs-lookup"><span data-stu-id="a9b8f-123">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [<span data-ttu-id="a9b8f-124">Filtrar para ejecutar un procedimiento almacenado parametrizado mediante EntityCommand</span><span class="sxs-lookup"><span data-stu-id="a9b8f-124">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [<span data-ttu-id="a9b8f-125">Filtrar para ejecutar una consulta polimórfica</span><span class="sxs-lookup"><span data-stu-id="a9b8f-125">How to: Execute a Polymorphic Query</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [<span data-ttu-id="a9b8f-126">Filtrar para navegar por las relaciones con el operador Navigate</span><span class="sxs-lookup"><span data-stu-id="a9b8f-126">How to: Navigate Relationships with the Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a><span data-ttu-id="a9b8f-127">Utilizar Entity SQL con consultas de objeto</span><span class="sxs-lookup"><span data-stu-id="a9b8f-127">Using Entity SQL with object queries</span></span>  
 <span data-ttu-id="a9b8f-128">Si desea utilizar Entity SQL con consultas de objeto, consulte los siguientes temas para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="a9b8f-128">If you want to use Entity SQL with object queries, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="a9b8f-129">Filtrar Ejecutar una consulta que devuelve objetos de tipo de entidad</span><span class="sxs-lookup"><span data-stu-id="a9b8f-129">How to: Execute a Query that Returns Entity Type Objects</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))  
  
 [<span data-ttu-id="a9b8f-130">Filtrar Ejecutar una consulta parametrizada</span><span class="sxs-lookup"><span data-stu-id="a9b8f-130">How to: Execute a Parameterized Query</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))  
  
 [<span data-ttu-id="a9b8f-131">Filtrar Navegar por las relaciones mediante propiedades de navegación</span><span class="sxs-lookup"><span data-stu-id="a9b8f-131">How to: Navigate Relationships Using Navigation Properties</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))  
  
 [<span data-ttu-id="a9b8f-132">Filtrar Llamar a una función definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="a9b8f-132">How to: Call a User-Defined Function</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))  
  
 [<span data-ttu-id="a9b8f-133">Filtrar Filtrar datos</span><span class="sxs-lookup"><span data-stu-id="a9b8f-133">How to: Filter Data</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))  
  
 [<span data-ttu-id="a9b8f-134">Filtrar Ordenar datos</span><span class="sxs-lookup"><span data-stu-id="a9b8f-134">How to: Sort Data</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))  
  
 [<span data-ttu-id="a9b8f-135">Filtrar Agrupar datos</span><span class="sxs-lookup"><span data-stu-id="a9b8f-135">How to: Group Data</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))  
  
 [<span data-ttu-id="a9b8f-136">Filtrar Agregar datos</span><span class="sxs-lookup"><span data-stu-id="a9b8f-136">How to: Aggregate Data</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))  
  
 [<span data-ttu-id="a9b8f-137">Filtrar Ejecutar una consulta que devuelve objetos de tipo anónimo</span><span class="sxs-lookup"><span data-stu-id="a9b8f-137">How to: Execute a Query that Returns Anonymous Type Objects</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))  
  
 [<span data-ttu-id="a9b8f-138">Filtrar Ejecutar una consulta que devuelve una colección de tipos primitivos</span><span class="sxs-lookup"><span data-stu-id="a9b8f-138">How to: Execute a Query that Returns a Collection of Primitive Types</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))  
  
 [<span data-ttu-id="a9b8f-139">Filtrar Consultar objetos relacionados en EntityCollection</span><span class="sxs-lookup"><span data-stu-id="a9b8f-139">How to: Query Related Objects in an EntityCollection</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))  
  
 [<span data-ttu-id="a9b8f-140">Filtrar Ordenar la unión de dos consultas</span><span class="sxs-lookup"><span data-stu-id="a9b8f-140">How to: Order the Union of Two Queries</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))  
  
 [<span data-ttu-id="a9b8f-141">Filtrar Página de resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="a9b8f-141">How to: Page Through Query Results</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))  
  
## <a name="in-this-section"></a><span data-ttu-id="a9b8f-142">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a9b8f-142">In This Section</span></span>  
 [<span data-ttu-id="a9b8f-143">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a9b8f-143">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [<span data-ttu-id="a9b8f-144">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a9b8f-144">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="a9b8f-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9b8f-145">See also</span></span>

- [<span data-ttu-id="a9b8f-146">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="a9b8f-146">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
- [<span data-ttu-id="a9b8f-147">Referencia del lenguaje</span><span class="sxs-lookup"><span data-stu-id="a9b8f-147">Language Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
