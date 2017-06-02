---
title: "Lenguaje Entity SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Lenguaje Entity SQL
Entity SQL es un lenguaje de consulta independiente del almacenamiento que se parece a SQL.  Entity SQL permite consultar los datos de la entidad, ya sea como objetos o en un formato tabular.  Considere el uso de Entity SQL en los siguientes casos:  
  
-   Cuando una consulta se debe construir dinámicamente en tiempo de ejecución.  En este caso, también debe considerar el uso de los métodos del generador de consultas de <xref:System.Data.Objects.ObjectQuery%601> en lugar de construir una cadena de consulta de Entity SQL en tiempo de ejecución.  
  
-   Si desea definir una consulta como parte de la definición del modelo.  Entity SQL solo se admite en un modelo de datos.  Para obtener más información, vea [QueryView Element \(MSL\)](http://msdn.microsoft.com/es-es/f0426b34-45cb-4fd7-9777-e0570c5e0e80)  
  
-   Si utiliza EntityClient para devolver los datos de la entidad de solo lectura como conjuntos de filas utilizando <xref:System.Data.EntityClient.EntityDataReader>.  Para obtener más información, consulta [Proveedor de EntityClient para Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
-   Si ya es un experto en lenguajes de consulta basados en SQL, Entity SQL puede parecerle el más natural.  
  
## Utilizar Entity SQL con el proveedor de EntityClient  
 Si desea utilizar Entity SQL con el proveedor de EntityClient, consulte los siguientes temas para obtener más información:  
  
 [Proveedor de EntityClient para Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [Cómo generar una cadena de conexión EntityConnection](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [Ejecutar una consulta que devuelve resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Cómo: Ejecutar una consulta que devuelve resultados RefType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Cómo: Ejecutar una consulta que devuelve tipos complejos](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Cómo ejecutar una consulta que devuelve colecciones anidadas](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Cómo ejecutar una consulta de Entity SQL parametrizada con EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Cómo ejecutar un procedimiento almacenado parametrizado usando EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Cómo ejecutar una consulta polimórfica](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Cómo: Navegar por las relaciones con el operador Navigate](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## Utilizar Entity SQL con consultas de objeto  
 Si desea utilizar Entity SQL con consultas de objeto, consulte los siguientes temas para obtener más información:  
  
 [How to: Execute a Query that Returns Entity Type Objects](http://msdn.microsoft.com/es-es/f73e137d-1534-42bb-9e31-99ca42c19b48)  
  
 [How to: Execute a Parameterized Query](http://msdn.microsoft.com/es-es/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
  
 [How to: Navigate Relationships Using Navigation Properties](http://msdn.microsoft.com/es-es/b1d71c7d-16a7-4b46-96ac-690176bd5057)  
  
 [How to: Call a User\-Defined Function](http://msdn.microsoft.com/es-es/ad131b86-8b4e-4747-8605-d4fc64fb9d02)  
  
 [How to: Filter Data](http://msdn.microsoft.com/es-es/776f8556-3350-4572-804a-b1513515c1b2)  
  
 [How to: Sort Data](http://msdn.microsoft.com/es-es/c05f2506-cb9d-4ebc-822b-300042ad53e7)  
  
 [How to: Group Data](http://msdn.microsoft.com/es-es/df801d9d-9a8a-4157-97a6-5016b18998e1)  
  
 [How to: Aggregate Data](http://msdn.microsoft.com/es-es/4cf04ce8-3c0f-4f88-9d97-8fac8622598d)  
  
 [How to: Execute a Query that Returns Anonymous Type Objects](http://msdn.microsoft.com/es-es/3b264025-e911-4d73-90ce-992d2b9d189d)  
  
 [How to: Execute a Query that Returns a Collection of Primitive Types](http://msdn.microsoft.com/es-es/115b52c0-4f27-4253-8991-284b450000b5)  
  
 [How to: Query Related Objects in an EntityCollection](http://msdn.microsoft.com/es-es/11ce946f-16f8-4c1d-9d80-f740853807ba)  
  
 [How to: Order the Union of Two Queries](http://msdn.microsoft.com/es-es/853c583a-eaba-4400-830d-be974e735313)  
  
 [How to: Page Through Query Results](http://msdn.microsoft.com/es-es/ffc0f920-e7de-42e0-9b12-ef356421d030)  
  
## En esta sección  
 [Información general de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## Vea también  
 [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)   
 [Referencia del lenguaje](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)