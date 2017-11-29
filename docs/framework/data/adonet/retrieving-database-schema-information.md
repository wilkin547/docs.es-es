---
title: "Recuperar información del esquema de la base de datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 71493eb91415b5f4695e771c7a549244629bb654
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-database-schema-information"></a>Recuperar información del esquema de la base de datos
La obtención de información de esquema de una base de datos se efectúa con el proceso de detección de esquemas. Detección de esquemas permite que las aplicaciones soliciten a los proveedores administrados buscan y devuelvan información acerca del esquema de base de datos, también conocido como *metadatos*, de una base de datos. Los diferentes elementos del esquema de base de datos, como tablas, columnas y procedimientos almacenados, se exponen a través de colecciones de esquemas. Cada colección de esquemas contiene diversa información de esquema relativa al proveedor que se está utilizando.  
  
 Cada uno de lo proveedores administrados de .NET Framework implementan la **GetSchema** método en el **conexión** clase y la información de esquema que se devuelve desde el **GetSchema**método viene en forma de un <xref:System.Data.DataTable>. El **GetSchema** método es un método sobrecargado que proporciona parámetros opcionales para especificar la colección de esquemas para devolver y para restringir la cantidad de información devuelta.  
  
 Los proveedores de datos de .NET Framework para OLE DB, ODBC, Oracle y SqlClient proporcionan un **GetSchemaTable** método que devuelve una DataTable donde se describen los metadatos de columna de la **DataReader**.  
  
 Además el proveedor de datos .NET Framework para OLE DB también expone información de esquema mediante el método <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> del objeto <xref:System.Data.OleDb.OleDbConnection>. Como argumentos, **GetOleDbSchemaTable** toma una <xref:System.Data.OleDb.OleDbSchemaGuid> que identifica la información de esquema que se devuelve y una matriz de restricciones en esas columnas devueltas. **GetOleDbSchemaTable** devuelve un <xref:System.Data.DataTable> rellena con la información de esquema solicitada.  
  
## <a name="in-this-section"></a>En esta sección  
 [GetSchema y colecciones de esquemas](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 Describe la **GetSchema** método y cómo se puede utilizar para recuperar y restringir información de esquema desde una base de datos.  
  
 Restricciones de esquema  
 Describe las restricciones de esquema que se pueden utilizar con **GetSchema**.  
  
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
  
## <a name="reference"></a>Referencia  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 Describe la **GetSchema** método de la <xref:System.Data.Common.DbConnection> clase.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 Describe la **GetSchema** método de la <xref:System.Data.Odbc.OdbcConnection> clase.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 Describe la **GetSchema** método de la <xref:System.Data.OleDb.OleDbConnection> clase.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 Describe la **GetSchema** método de la <xref:System.Data.OracleClient.OracleConnection> clase.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 Describe la **GetSchema** método de la <xref:System.Data.SqlClient.SqlConnection> clase.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 Describe la **GetSchemaTable** método de la <xref:System.Data.Common.DbDataReader> clase.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 Describe la **GetSchemaTable** método de la <xref:System.Data.Odbc.OdbcDataReader> clase.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 Describe la **GetSchemaTable** método de la <xref:System.Data.OleDb.OleDbDataReader> clase.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 Describe la **GetSchemaTable** método de la <xref:System.Data.OracleClient.OracleDataReader> clase.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 Describe la **GetSchemaTable** método de la <xref:System.Data.SqlClient.SqlDataReader> clase.  
  
## <a name="see-also"></a>Vea también  
 [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
