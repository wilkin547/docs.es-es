---
title: "Recuperar informaci&#243;n de esquema de la base de datos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Recuperar informaci&#243;n de esquema de la base de datos
La obtención de información de esquema de una base de datos se efectúa con el proceso de detección de esquemas.  La detección de esquemas permite que las aplicaciones soliciten a los proveedores administrados que busquen y devuelvan información acerca del esquema de base de datos, también conocido como *metadatos*, de una base de datos dada.  Los diferentes elementos del esquema de base de datos, como tablas, columnas y procedimientos almacenados, se exponen a través de colecciones de esquemas.  Cada colección de esquemas contiene diversa información de esquema relativa al proveedor que se está utilizando.  
  
 Cada uno de los proveedores administrados de .NET Framework implementa el método **GetSchema** en la clase **Connection**, y la información de esquema que devuelve el método **GetSchema** viene en forma de una <xref:System.Data.DataTable>.  El método **GetSchema** es un método sobrecargado que proporciona parámetros opcionales para especificar la colección de esquemas que se devolverá y para restringir la cantidad de información devuelta.  
  
 Los proveedores de datos .NET Framework para OLE DB, ODBC, Oracle y SqlClient proporcionan un método **GetSchemaTable** que devuelve una DataTable donde se describen los metadatos de columna del **DataReader**.  
  
 Además el proveedor de datos .NET Framework para OLE DB también expone información de esquema mediante el método <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> del objeto <xref:System.Data.OleDb.OleDbConnection>.  **GetOleDbSchemaTable** toma como argumentos un objeto <xref:System.Data.OleDb.OleDbSchemaGuid> que identifica la información de esquema que se devuelve y una matriz de restricciones en esas columnas devueltas.  **GetOleDbSchemaTable** devuelve una <xref:System.Data.DataTable> rellena con la información de esquema solicitada.  
  
## En esta sección  
 [GetSchema y colecciones de esquemas](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 Describe el método **GetSchema** y cómo se puede utilizar para recuperar y restringir información de esquema desde una base de datos.  
  
 Restricciones de esquema  
 Describe las restricciones de esquema que se pueden usar con **GetSchema**.  
  
 [Colecciones de esquemas comunes](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 Describe todas las colecciones de esquemas comunes que admiten todos los proveedores administrados de .NET Framework.  
  
 [Colecciones de esquemas SQL Server](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 Describe la colección de esquemas compatibles con el proveedor de datos .NET Framework para SQL Server.  
  
 [Colecciones de esquemas de Oracle](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 Describe la colección de esquemas compatibles con el proveedor de datos .NET Framework para Oracle.  
  
 [Colecciones de esquemas ODBC](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 Describe las colecciones de esquemas para los controladores ODBC.  
  
 [Colecciones de esquemas OLE DB](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 Describe las colecciones de esquemas para los proveedores OLE DB.  
  
## Referencia  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 Describe el método **GetSchema** de la clase <xref:System.Data.Common.DbConnection>.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 Describe el método **GetSchema** de la clase <xref:System.Data.Odbc.OdbcConnection>.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 Describe el método **GetSchema** de la clase <xref:System.Data.OleDb.OleDbConnection>.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 Describe el método **GetSchema** de la clase <xref:System.Data.OracleClient.OracleConnection>.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 Describe el método **GetSchema** de la clase <xref:System.Data.SqlClient.SqlConnection>.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 Describe el método **GetSchemaTable** de la clase <xref:System.Data.Common.DbDataReader>.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 Describe el método **GetSchemaTable** de la clase <xref:System.Data.Odbc.OdbcDataReader>.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 Describe el método **GetSchemaTable** de la clase <xref:System.Data.OleDb.OleDbDataReader>.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 Describe el método **GetSchemaTable** de la clase <xref:System.Data.OracleClient.OracleDataReader>.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 Describe el método **GetSchemaTable** de la clase <xref:System.Data.SqlClient.SqlDataReader>.  
  
## Vea también  
 [Recuperación y modificación de datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)