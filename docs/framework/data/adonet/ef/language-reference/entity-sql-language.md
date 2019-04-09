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
# <a name="entity-sql-language"></a>Lenguaje Entity SQL
Entity SQL es un lenguaje de consulta independiente del almacenamiento que se parece a SQL. Entity SQL permite consultar los datos de la entidad, ya sea como objetos o en un formato tabular. Considere el uso de Entity SQL en los siguientes casos:  
  
-   Cuando una consulta se debe construir dinámicamente en tiempo de ejecución. En este caso, también debe considerar el uso de los métodos del generador de consultas de <xref:System.Data.Objects.ObjectQuery%601> en lugar de construir una cadena de consulta de Entity SQL en tiempo de ejecución.  
  
-   Si desea definir una consulta como parte de la definición del modelo. Entity SQL solo se admite en un modelo de datos. Para obtener más información, consulte [elemento QueryView (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)  
  
-   Si utiliza EntityClient para devolver los datos de la entidad de solo lectura como conjuntos de filas utilizando <xref:System.Data.EntityClient.EntityDataReader>. Para obtener más información, consulte [proveedor de EntityClient para Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
-   Si ya es un experto en lenguajes de consulta basados en SQL, Entity SQL puede parecerle el más natural.  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a>Utilizar Entity SQL con el proveedor de EntityClient  
 Si desea utilizar Entity SQL con el proveedor de EntityClient, consulte los siguientes temas para obtener más información:  
  
 [Proveedor de EntityClient para Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [Filtrar para compilar una cadena de conexión EntityConnection](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [Filtrar para ejecutar una consulta que devuelve resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Filtrar para ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Filtrar para ejecutar una consulta que devuelve resultados RefType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Filtrar para ejecutar una consulta que devuelve tipos complejos](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Filtrar para ejecutar una consulta que devuelve colecciones anidadas](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Filtrar para ejecutar una consulta parametrizada de Entity SQL mediante EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Filtrar para ejecutar un procedimiento almacenado parametrizado mediante EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Filtrar para ejecutar una consulta polimórfica](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Filtrar para navegar por las relaciones con el operador Navigate](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a>Utilizar Entity SQL con consultas de objeto  
 Si desea utilizar Entity SQL con consultas de objeto, consulte los siguientes temas para obtener más información:  
  
 [Filtrar Ejecutar una consulta que devuelve objetos de tipo de entidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))  
  
 [Filtrar Ejecutar una consulta parametrizada](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))  
  
 [Filtrar Navegar por las relaciones mediante propiedades de navegación](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))  
  
 [Filtrar Llamar a una función definida por el usuario](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))  
  
 [Filtrar Filtrar datos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))  
  
 [Filtrar Ordenar datos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))  
  
 [Filtrar Agrupar datos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))  
  
 [Filtrar Agregar datos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))  
  
 [Filtrar Ejecutar una consulta que devuelve objetos de tipo anónimo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))  
  
 [Filtrar Ejecutar una consulta que devuelve una colección de tipos primitivos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))  
  
 [Filtrar Consultar objetos relacionados en EntityCollection](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))  
  
 [Filtrar Ordenar la unión de dos consultas](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))  
  
 [Filtrar Página de resultados de la consulta](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a>Vea también

- [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)
- [Referencia del lenguaje](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
