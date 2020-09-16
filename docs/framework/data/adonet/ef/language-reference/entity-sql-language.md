---
title: Lenguaje Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 2600b7626ebc5196c702f2d1e3159fd9549227f7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553387"
---
# <a name="entity-sql-language"></a>Lenguaje Entity SQL
Entity SQL es un lenguaje de consulta independiente del almacenamiento que se parece a SQL. Entity SQL permite consultar los datos de la entidad, ya sea como objetos o en un formato tabular. Considere el uso de Entity SQL en los siguientes casos:  
  
- Cuando una consulta se debe construir dinámicamente en tiempo de ejecución. En este caso, también debe considerar el uso de los métodos del generador de consultas de <xref:System.Data.Objects.ObjectQuery%601> en lugar de construir una cadena de consulta de Entity SQL en tiempo de ejecución.  
  
- Si desea definir una consulta como parte de la definición del modelo. Entity SQL solo se admite en un modelo de datos. Para obtener más información, vea [QueryView (elemento) (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)  
  
- Si utiliza EntityClient para devolver los datos de la entidad de solo lectura como conjuntos de filas utilizando <xref:System.Data.EntityClient.EntityDataReader>. Para obtener más información, consulte [Proveedor de EntityClient para Entity Framework](../entityclient-provider-for-the-entity-framework.md).  
  
- Si ya es un experto en lenguajes de consulta basados en SQL, Entity SQL puede parecerle el más natural.  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a>Utilizar Entity SQL con el proveedor de EntityClient  
 Si desea utilizar Entity SQL con el proveedor de EntityClient, consulte los siguientes temas para obtener más información:  
  
 [Proveedor de EntityClient para Entity Framework](../entityclient-provider-for-the-entity-framework.md)  
  
 [Procedimiento para compilar una cadena de conexión EntityConnection](../how-to-build-an-entityconnection-connection-string.md)  
  
 [Procedimiento para ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Procedimiento para ejecutar una consulta que devuelve resultados StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Procedimiento para ejecutar una consulta que devuelve resultados RefType](../how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Procedimiento para ejecutar una consulta que devuelve tipos complejos](../how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Procedimiento para ejecutar una consulta que devuelve colecciones anidadas](../how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Procedimiento para ejecutar una consulta parametrizada de Entity SQL mediante EntityCommand](../how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Procedimiento para ejecutar un procedimiento almacenado parametrizado mediante EntityCommand](../how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Procedimiento para ejecutar una consulta polimórfica](../how-to-execute-a-polymorphic-query.md)  
  
 [Procedimiento para navegar por las relaciones con el operador Navigate](../how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a>Utilizar Entity SQL con consultas de objeto  
 Si desea utilizar Entity SQL con consultas de objeto, consulte los siguientes temas para obtener más información:  
  
 [Cómo: Ejecutar una consulta que devuelve objetos de tipos de entidad](/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))  
  
 [Cómo: Ejecutar una consulta parametrizada](/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))  
  
 [Cómo: Navegar por las relaciones mediante propiedades de navegación](/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))  
  
 [Cómo: Llamar a una función definida por el usuario](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))  
  
 [Cómo: Filtrar datos](/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))  
  
 [Cómo: Ordenar datos](/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))  
  
 [Cómo: Agrupar datos](/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))  
  
 [Cómo: Agregar datos](/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))  
  
 [Cómo: Ejecutar una consulta que devuelve objetos de tipos anónimos](/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))  
  
 [Cómo: Ejecutar una consulta que devuelve una colección de tipos primitivos](/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))  
  
 [Cómo: Consultar objetos relacionados en EntityCollection](/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))  
  
 [Cómo: Ordenar la unión de dos consultas](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))  
  
 [Cómo hojear los resultados de la consulta](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre Entity SQL](entity-sql-overview.md)  
  
 [Referencia de Entity SQL](entity-sql-reference.md)  
  
## <a name="see-also"></a>Vea también

- [ADO.NET Entity Framework](../index.md)
- [Referencia del lenguaje](index.md)
