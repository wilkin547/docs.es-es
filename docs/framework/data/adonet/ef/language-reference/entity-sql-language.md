---
title: Lenguaje Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: a2e4b7245dbfccf7864481b52a0e868a85efbca6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251016"
---
# <a name="entity-sql-language"></a>Lenguaje Entity SQL
Entity SQL es un lenguaje de consulta independiente del almacenamiento que se parece a SQL. Entity SQL permite consultar los datos de la entidad, ya sea como objetos o en un formato tabular. Considere el uso de Entity SQL en los siguientes casos:  
  
- Cuando una consulta se debe construir dinámicamente en tiempo de ejecución. En este caso, también debe considerar el uso de los métodos del generador de consultas de <xref:System.Data.Objects.ObjectQuery%601> en lugar de construir una cadena de consulta de Entity SQL en tiempo de ejecución.  
  
- Si desea definir una consulta como parte de la definición del modelo. Entity SQL solo se admite en un modelo de datos. Para obtener más información, vea [QueryView (elemento) (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)  
  
- Si utiliza EntityClient para devolver los datos de la entidad de solo lectura como conjuntos de filas utilizando <xref:System.Data.EntityClient.EntityDataReader>. Para obtener más información, consulte [proveedor de EntityClient para el Entity Framework](../entityclient-provider-for-the-entity-framework.md).  
  
- Si ya es un experto en lenguajes de consulta basados en SQL, Entity SQL puede parecerle el más natural.  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a>Utilizar Entity SQL con el proveedor de EntityClient  
 Si desea utilizar Entity SQL con el proveedor de EntityClient, consulte los siguientes temas para obtener más información:  
  
 [Proveedor de EntityClient para Entity Framework](../entityclient-provider-for-the-entity-framework.md)  
  
 [Procedimientos: Compilación de una cadena de conexión de EntityConnection](../how-to-build-an-entityconnection-connection-string.md)  
  
 [Cómo: Ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Procedimientos: Ejecutar una consulta que devuelve resultados RefType](../how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Cómo: Ejecutar una consulta que devuelve tipos complejos](../how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Procedimientos: Ejecutar una consulta que devuelve colecciones anidadas](../how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Cómo: Ejecutar una consulta de Entity SQL con parámetros mediante EntityCommand](../how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Cómo: Ejecutar un procedimiento almacenado parametrizado usando EntityCommand](../how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Cómo: Ejecutar una consulta polimórfica](../how-to-execute-a-polymorphic-query.md)  
  
 [Cómo: Navegar por las relaciones con el operador Navigate](../how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a>Utilizar Entity SQL con consultas de objeto  
 Si desea utilizar Entity SQL con consultas de objeto, consulte los siguientes temas para obtener más información:  
  
 [Cómo: Ejecutar una consulta que devuelve objetos de tipo de entidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))  
  
 [Procedimientos: Ejecutar una consulta con parámetros](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))  
  
 [Cómo: Navegar por las relaciones mediante propiedades de navegación](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))  
  
 [Cómo: Llamar a una función definida por el usuario](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))  
  
 [Procedimientos: Filtrar datos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))  
  
 [Cómo: Ordenar datos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))  
  
 [Cómo: Agrupar datos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))  
  
 [Cómo: Datos agregados](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))  
  
 [Cómo: Ejecutar una consulta que devuelve objetos de tipo anónimo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))  
  
 [Cómo: Ejecutar una consulta que devuelve una colección de tipos primitivos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))  
  
 [Cómo: Consultar objetos relacionados en una EntityCollection](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))  
  
 [Procedimientos: Ordenar la Unión de dos consultas](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))  
  
 [Cómo: Página a través de los resultados de la consulta](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre Entity SQL](entity-sql-overview.md)  
  
 [Referencia de Entity SQL](entity-sql-reference.md)  
  
## <a name="see-also"></a>Vea también

- [ADO.NET Entity Framework](../index.md)
- [Referencia del lenguaje](index.md)
