---
title: "Proveedor de EntityClient para Entity Framework | Microsoft Docs"
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
ms.assetid: 8c5db787-78e6-4a34-8dc1-188bca0aca5e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Proveedor de EntityClient para Entity Framework
El proveedor de EntityClient es un proveedor de datos que usan las aplicaciones de Entity Framework para tener acceso a los datos descritos en un modelo conceptual.  Para obtener más información sobre los modelos conceptuales, vea [Modelado y asignación](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md).  EntityClient utiliza otros proveedores de datos .NET Framework para tener acceso al origen de datos.  Por ejemplo, EntityClient utiliza el Proveedor de datos .NET Framework para SQL Server \(SqlClient\) al tener acceso a una base de datos de SQL Server.  Para obtener información acerca del proveedor SqlClient, vea [SqlClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md).  El proveedor de EntityClient se implementa en el espacio de nombres <xref:System.Data.EntityClient>.  
  
## Administrar conexiones  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] se basa en proveedores de datos [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] específicos del almacenamiento proporcionando un objeto <xref:System.Data.EntityClient.EntityConnection> a un proveedor de datos subyacente y una base de datos relacional.  Para crear un objeto <xref:System.Data.EntityClient.EntityConnection>, se ha de hacer referencia a un conjunto de metadatos que contiene la asignación y los modelos necesarios, y también el nombre de un proveedor de datos específico del almacenamiento y una cadena de conexión.  Una vez activado el objeto <xref:System.Data.EntityClient.EntityConnection>, se puede tener acceso a las entidades a través de las clases generadas desde el modelo conceptual.  
  
 Se puede especificar una cadena de conexión en el archivo app.config.  
  
 El espacio de nombres <xref:System.Data.EntityClient> también incluye la clase <xref:System.Data.EntityClient.EntityConnectionStringBuilder>.  Esta clase permite que los programadores creen mediante programación cadenas de conexión sintácticamente correctas, y que analicen y recompilen las cadenas de conexión existentes, utilizando las propiedades y los métodos de la clase.  Para obtener más información, consulta [Cómo generar una cadena de conexión EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md).  
  
## Crear consultas  
 El lenguaje de [!INCLUDE[esql](../../../../../includes/esql-md.md)] es un dialecto independiente del almacenamiento de SQL que trabaja directamente con esquemas de entidades conceptuales y admite conceptos de Entity Data Model, como la herencia y las relaciones.  La clase <xref:System.Data.EntityClient.EntityCommand> se utiliza para ejecutar un comando de [!INCLUDE[esql](../../../../../includes/esql-md.md)] con un modelo de la entidad.  Cuando se crean objetos de <xref:System.Data.EntityClient.EntityCommand>, se puede especificar un nombre de procedimiento almacenado o un texto de consulta.  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] trabaja con proveedores de datos específicos del almacenamiento para traducir el [!INCLUDE[esql](../../../../../includes/esql-md.md)] genérico en consultas específicas del almacenamiento.  Para obtener más información acerca de cómo escribir consultas de [!INCLUDE[esql](../../../../../includes/esql-md.md)], vea [Lenguaje Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md).  
  
 En el ejemplo siguiente se crea un objeto de <xref:System.Data.EntityClient.EntityCommand> y se asigna un texto de consulta de [!INCLUDE[esql](../../../../../includes/esql-md.md)] a su propiedad <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=fullName>.  Esta consulta de [!INCLUDE[esql](../../../../../includes/esql-md.md)] solicita productos ordenados por el precio de venta del modelo conceptual.  El código siguiente no tiene conocimiento alguno del modelo de almacenamiento.  
  
 `EntityCommand cmd = conn.CreateCommand();`  
  
 `cmd.CommandText = @"` `SELECT VALUE p`  
  
 `FROM AdventureWorksEntities.Product AS p`  
  
 `ORDER BY p.ListPrice ";`  
  
## Ejecutar consultas  
 Cuando se ejecuta una consulta, se analiza y se convierte en un árbol de comandos canónico.  Todo el procesamiento subsiguiente se realiza en el árbol de comandos.  El árbol de comandos es el medio de comunicación entre el espacio de nombres <xref:System.Data.EntityClient> y el proveedor de datos [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] subyacente, como <xref:System.Data.SqlClient>.  
  
 <xref:System.Data.EntityClient.EntityDataReader> muestra los resultados de ejecutar <xref:System.Data.EntityClient.EntityCommand> en un modelo conceptual.  Para ejecutar el comando que devuelve el <xref:System.Data.EntityClient.EntityDataReader>, llame a <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.  <xref:System.Data.EntityClient.EntityDataReader> implementa <xref:System.Data.IExtendedDataRecord> para describir resultados estructurados enriquecidos.  
  
## Administrar transacciones  
 En Entity Framework, hay dos maneras de utilizar las transacciones: automática y explícita.  Las transacciones automáticas usan el espacio de nombres <xref:System.Transactions> y las transacciones explícitas usan la clase <xref:System.Data.EntityClient.EntityTransaction>.  
  
 Para actualizar los datos que se exponen a través de un modelo conceptual; vea [How to: Manage Transactions in the Entity Framework](http://msdn.microsoft.com/es-es/4a55eb7f-f826-4a48-9df1-aebe2352ebef).  
  
## En esta sección  
 [Cómo generar una cadena de conexión EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [Ejecutar una consulta que devuelve resultados PrimitiveType](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Ejecutar una consulta que devuelve resultados StructuralType](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Cómo: Ejecutar una consulta que devuelve resultados RefType](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Cómo: Ejecutar una consulta que devuelve tipos complejos](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Cómo ejecutar una consulta que devuelve colecciones anidadas](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Cómo ejecutar una consulta de Entity SQL parametrizada con EntityCommand](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Cómo ejecutar un procedimiento almacenado parametrizado usando EntityCommand](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Cómo ejecutar una consulta polimórfica](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Cómo: Navegar por las relaciones con el operador Navigate](../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## Vea también  
 [Managing Connections and Transactions](http://msdn.microsoft.com/es-es/b6659d2a-9a45-4e98-acaa-d7a8029e5b99)   
 [ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)   
 [Referencia del lenguaje](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)