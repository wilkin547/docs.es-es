---
title: Lenguaje Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 721a4cd9d4e5618c083392bbe1ae203f285f8feb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148119"
---
# <a name="entity-sql-language"></a><span data-ttu-id="bcef4-102">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bcef4-102">Entity SQL Language</span></span>

<span data-ttu-id="bcef4-103">Entity SQL es un lenguaje de consulta independiente del almacenamiento que se parece a SQL.</span><span class="sxs-lookup"><span data-stu-id="bcef4-103">Entity SQL is a storage-independent query language that is similar to SQL.</span></span> <span data-ttu-id="bcef4-104">Entity SQL permite consultar los datos de la entidad, ya sea como objetos o en un formato tabular.</span><span class="sxs-lookup"><span data-stu-id="bcef4-104">Entity SQL allows you to query entity data, either as objects or in a tabular form.</span></span> <span data-ttu-id="bcef4-105">Considere el uso de Entity SQL en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="bcef4-105">You should consider using Entity SQL in the following cases:</span></span>  
  
- <span data-ttu-id="bcef4-106">Cuando una consulta se debe construir dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bcef4-106">When a query must be dynamically constructed at runtime.</span></span> <span data-ttu-id="bcef4-107">En este caso, también debe considerar el uso de los métodos del generador de consultas de <xref:System.Data.Objects.ObjectQuery%601> en lugar de construir una cadena de consulta de Entity SQL en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bcef4-107">In this case, you should also consider using the query builder methods of <xref:System.Data.Objects.ObjectQuery%601> instead of constructing an Entity SQL query string at runtime.</span></span>  
  
- <span data-ttu-id="bcef4-108">Si desea definir una consulta como parte de la definición del modelo.</span><span class="sxs-lookup"><span data-stu-id="bcef4-108">When you want to define a query as part of the model definition.</span></span> <span data-ttu-id="bcef4-109">Entity SQL solo se admite en un modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="bcef4-109">Only Entity SQL is supported in a data model.</span></span> <span data-ttu-id="bcef4-110">Para obtener más información, vea [QueryView (elemento) (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span><span class="sxs-lookup"><span data-stu-id="bcef4-110">For more information, see [QueryView Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span></span>  
  
- <span data-ttu-id="bcef4-111">Si utiliza EntityClient para devolver los datos de la entidad de solo lectura como conjuntos de filas utilizando <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="bcef4-111">When using EntityClient to return read-only entity data as rowsets using a <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="bcef4-112">Para obtener más información, consulte [Proveedor de EntityClient para Entity Framework](../entityclient-provider-for-the-entity-framework.md).</span><span class="sxs-lookup"><span data-stu-id="bcef4-112">For more information, see [EntityClient Provider for the Entity Framework](../entityclient-provider-for-the-entity-framework.md).</span></span>  
  
- <span data-ttu-id="bcef4-113">Si ya es un experto en lenguajes de consulta basados en SQL, Entity SQL puede parecerle el más natural.</span><span class="sxs-lookup"><span data-stu-id="bcef4-113">If you are already an expert in SQL-based query languages, Entity SQL may seem the most natural to you.</span></span>  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a><span data-ttu-id="bcef4-114">Utilizar Entity SQL con el proveedor de EntityClient</span><span class="sxs-lookup"><span data-stu-id="bcef4-114">Using Entity SQL with the EntityClient provider</span></span>  

 <span data-ttu-id="bcef4-115">Si desea utilizar Entity SQL con el proveedor de EntityClient, consulte los siguientes temas para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="bcef4-115">If you want to use Entity SQL with the EntityClient provider, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="bcef4-116">Proveedor de EntityClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="bcef4-116">EntityClient Provider for the Entity Framework</span></span>](../entityclient-provider-for-the-entity-framework.md)  
  
 [<span data-ttu-id="bcef4-117">Procedimiento para compilar una cadena de conexión EntityConnection</span><span class="sxs-lookup"><span data-stu-id="bcef4-117">How to: Build an EntityConnection Connection String</span></span>](../how-to-build-an-entityconnection-connection-string.md)  
  
 [<span data-ttu-id="bcef4-118">Procedimiento para ejecutar una consulta que devuelve resultados PrimitiveType</span><span class="sxs-lookup"><span data-stu-id="bcef4-118">How to: Execute a Query that Returns PrimitiveType Results</span></span>](../how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [<span data-ttu-id="bcef4-119">Procedimiento para ejecutar una consulta que devuelve resultados StructuralType</span><span class="sxs-lookup"><span data-stu-id="bcef4-119">How to: Execute a Query that Returns StructuralType Results</span></span>](../how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [<span data-ttu-id="bcef4-120">Procedimiento para ejecutar una consulta que devuelve resultados RefType</span><span class="sxs-lookup"><span data-stu-id="bcef4-120">How to: Execute a Query that Returns RefType Results</span></span>](../how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [<span data-ttu-id="bcef4-121">Procedimiento para ejecutar una consulta que devuelve tipos complejos</span><span class="sxs-lookup"><span data-stu-id="bcef4-121">How to: Execute a Query that Returns Complex Types</span></span>](../how-to-execute-a-query-that-returns-complex-types.md)  
  
 [<span data-ttu-id="bcef4-122">Procedimiento para ejecutar una consulta que devuelve colecciones anidadas</span><span class="sxs-lookup"><span data-stu-id="bcef4-122">How to: Execute a Query that Returns Nested Collections</span></span>](../how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [<span data-ttu-id="bcef4-123">Procedimiento para ejecutar una consulta parametrizada de Entity SQL mediante EntityCommand</span><span class="sxs-lookup"><span data-stu-id="bcef4-123">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>](../how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [<span data-ttu-id="bcef4-124">Procedimiento para ejecutar un procedimiento almacenado parametrizado mediante EntityCommand</span><span class="sxs-lookup"><span data-stu-id="bcef4-124">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>](../how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [<span data-ttu-id="bcef4-125">Procedimiento para ejecutar una consulta polimórfica</span><span class="sxs-lookup"><span data-stu-id="bcef4-125">How to: Execute a Polymorphic Query</span></span>](../how-to-execute-a-polymorphic-query.md)  
  
 [<span data-ttu-id="bcef4-126">Procedimiento para navegar por las relaciones con el operador Navigate</span><span class="sxs-lookup"><span data-stu-id="bcef4-126">How to: Navigate Relationships with the Navigate Operator</span></span>](../how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a><span data-ttu-id="bcef4-127">Utilizar Entity SQL con consultas de objeto</span><span class="sxs-lookup"><span data-stu-id="bcef4-127">Using Entity SQL with object queries</span></span>  

 <span data-ttu-id="bcef4-128">Si desea utilizar Entity SQL con consultas de objeto, consulte los siguientes temas para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="bcef4-128">If you want to use Entity SQL with object queries, see the following topics for more information:</span></span>  
  
 <span data-ttu-id="bcef4-129">[Cómo: Ejecutar una consulta que devuelve objetos de tipos de entidad](/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bcef4-129">[How to: Execute a Query that Returns Entity Type Objects](/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))</span></span>  
  
 <span data-ttu-id="bcef4-130">[Cómo: Ejecutar una consulta parametrizada](/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bcef4-130">[How to: Execute a Parameterized Query](/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span></span>  
  
 <span data-ttu-id="bcef4-131">[Cómo: Navegar por las relaciones mediante propiedades de navegación](/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bcef4-131">[How to: Navigate Relationships Using Navigation Properties](/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))</span></span>  
  
 <span data-ttu-id="bcef4-132">[Cómo: Llamar a una función definida por el usuario](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bcef4-132">[How to: Call a User-Defined Function](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))</span></span>  
  
 <span data-ttu-id="bcef4-133">[Cómo: Filtrar datos](/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bcef4-133">[How to: Filter Data](/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))</span></span>  
  
 <span data-ttu-id="bcef4-134">[Cómo: Ordenar datos](/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bcef4-134">[How to: Sort Data](/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))</span></span>  
  
 <span data-ttu-id="bcef4-135">[Cómo: Agrupar datos](/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bcef4-135">[How to: Group Data](/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))</span></span>  
  
 <span data-ttu-id="bcef4-136">[Cómo: Agregar datos](/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bcef4-136">[How to: Aggregate Data](/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))</span></span>  
  
 <span data-ttu-id="bcef4-137">[Cómo: Ejecutar una consulta que devuelve objetos de tipos anónimos](/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bcef4-137">[How to: Execute a Query that Returns Anonymous Type Objects](/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span></span>  
  
 <span data-ttu-id="bcef4-138">[Cómo: Ejecutar una consulta que devuelve una colección de tipos primitivos](/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bcef4-138">[How to: Execute a Query that Returns a Collection of Primitive Types](/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))</span></span>  
  
 <span data-ttu-id="bcef4-139">[Cómo: Consultar objetos relacionados en EntityCollection](/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bcef4-139">[How to: Query Related Objects in an EntityCollection](/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))</span></span>  
  
 <span data-ttu-id="bcef4-140">[Cómo: Ordenar la unión de dos consultas](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bcef4-140">[How to: Order the Union of Two Queries](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))</span></span>  
  
 <span data-ttu-id="bcef4-141">[Cómo hojear los resultados de la consulta](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bcef4-141">[How to: Page Through Query Results](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bcef4-142">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bcef4-142">In This Section</span></span>  

 [<span data-ttu-id="bcef4-143">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bcef4-143">Entity SQL Overview</span></span>](entity-sql-overview.md)  
  
 [<span data-ttu-id="bcef4-144">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bcef4-144">Entity SQL Reference</span></span>](entity-sql-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="bcef4-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcef4-145">See also</span></span>

- [<span data-ttu-id="bcef4-146">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="bcef4-146">ADO.NET Entity Framework</span></span>](../index.md)
- [<span data-ttu-id="bcef4-147">Referencia del lenguaje</span><span class="sxs-lookup"><span data-stu-id="bcef4-147">Language Reference</span></span>](index.md)
