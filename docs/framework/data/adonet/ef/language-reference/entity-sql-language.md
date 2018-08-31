---
title: Lenguaje Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 1df5372bed2c4c4b026662e0d1912683dd8752e9
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2018
ms.locfileid: "43331959"
---
# <a name="entity-sql-language"></a>Lenguaje Entity SQL
Entity SQL es un lenguaje de consulta independiente del almacenamiento que se parece a SQL. Entity SQL permite consultar los datos de la entidad, ya sea como objetos o en un formato tabular. Considere el uso de Entity SQL en los siguientes casos:  
  
-   Cuando una consulta se debe construir dinámicamente en tiempo de ejecución. En este caso, también debe considerar el uso de los métodos del generador de consultas de <xref:System.Data.Objects.ObjectQuery%601> en lugar de construir una cadena de consulta de Entity SQL en tiempo de ejecución.  
  
-   Si desea definir una consulta como parte de la definición del modelo. Entity SQL solo se admite en un modelo de datos. Para obtener más información, consulte [elemento QueryView (MSL)](https://msdn.microsoft.com/library/f0426b34-45cb-4fd7-9777-e0570c5e0e80)  
  
-   Si utiliza EntityClient para devolver los datos de la entidad de solo lectura como conjuntos de filas utilizando <xref:System.Data.EntityClient.EntityDataReader>. Para obtener más información, consulte [proveedor de EntityClient para Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
-   Si ya es un experto en lenguajes de consulta basados en SQL, Entity SQL puede parecerle el más natural.  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a>Utilizar Entity SQL con el proveedor de EntityClient  
 Si desea utilizar Entity SQL con el proveedor de EntityClient, consulte los siguientes temas para obtener más información:  
  
 [Proveedor de EntityClient para Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [Compilación de una cadena de conexión EntityConnection](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [Ejecución de una consulta que devuelve resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Ejecución de una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Ejecución de una consulta que devuelve resultados RefType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Ejecución de una consulta que devuelve tipos complejos](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Ejecución de una consulta que devuelve colecciones anidadas](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Ejecución de una consulta parametrizada de Entity SQL usando EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Ejecución de un procedimiento almacenado parametrizado usando EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Ejecución de una consulta polimórfica](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Navegación por las relaciones con el operador Navigate](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a>Utilizar Entity SQL con consultas de objeto  
 Si desea utilizar Entity SQL con consultas de objeto, consulte los siguientes temas para obtener más información:  
  
 [Cómo: ejecutar una consulta que devuelve objetos de tipo de entidad](https://msdn.microsoft.com/library/f73e137d-1534-42bb-9e31-99ca42c19b48)  
  
 [Cómo: ejecutar una consulta parametrizada](https://msdn.microsoft.com/library/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
  
 [Cómo: navegar por las relaciones mediante propiedades de navegación](https://msdn.microsoft.com/library/b1d71c7d-16a7-4b46-96ac-690176bd5057)  
  
 [Cómo: llamar a una función definida por el usuario](https://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)  
  
 [Cómo: filtrar datos](https://msdn.microsoft.com/library/776f8556-3350-4572-804a-b1513515c1b2)  
  
 [Cómo: ordenar datos](https://msdn.microsoft.com/library/c05f2506-cb9d-4ebc-822b-300042ad53e7)  
  
 [Cómo: agrupar datos](https://msdn.microsoft.com/library/df801d9d-9a8a-4157-97a6-5016b18998e1)  
  
 [Cómo: agregar datos](https://msdn.microsoft.com/library/4cf04ce8-3c0f-4f88-9d97-8fac8622598d)  
  
 [Cómo: ejecutar una consulta que devuelve objetos de tipo anónimo](https://msdn.microsoft.com/library/3b264025-e911-4d73-90ce-992d2b9d189d)  
  
 [Cómo: ejecutar una consulta que devuelve una colección de tipos primitivos](https://msdn.microsoft.com/library/115b52c0-4f27-4253-8991-284b450000b5)  
  
 [Cómo: consultar objetos relacionados en EntityCollection](https://msdn.microsoft.com/library/11ce946f-16f8-4c1d-9d80-f740853807ba)  
  
 [Cómo: ordenar la unión de dos consultas](https://msdn.microsoft.com/library/853c583a-eaba-4400-830d-be974e735313)  
  
 [Cómo: resultados de la página a través de la consulta](https://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a>Vea también  
 [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)  
 [Referencia del lenguaje](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
