---
title: Recuperar información del esquema de la base de datos
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: c0aaadc82771d1c2a36d797bc157d88b8d3cacdc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177363"
---
# <a name="retrieving-database-schema-information"></a>Recuperar información del esquema de la base de datos

La obtención de información de esquema de una base de datos se efectúa con el proceso de detección de esquemas. La detección de esquemas permite a las aplicaciones solicitar que los proveedores administrados busquen y devuelvan información sobre el esquema de la base de datos, también conocido como *metadatos*, de una base de datos determinada. Los diferentes elementos del esquema de base de datos, como tablas, columnas y procedimientos almacenados, se exponen a través de colecciones de esquemas. Cada colección de esquemas contiene diversa información de esquema relativa al proveedor que se está utilizando.  
  
 Cada uno de los proveedores administrados de .NET Framework implementa el método **GetSchema** en la clase **Connection** , y la información de esquema que se devuelve desde el método **GetSchema** tiene el formato <xref:System.Data.DataTable> . El método **GetSchema** es un método sobrecargado que proporciona parámetros opcionales para especificar la colección de esquemas que se va a devolver y restringir la cantidad de información devuelta.  
  
 Los proveedores de datos de .NET Framework para OLE DB, ODBC, Oracle y SqlClient proporcionan un método **GetSchemaTable** que devuelve un DataTable que describe los metadatos de columna del **DataReader**.  
  
 Además el proveedor de datos .NET Framework para OLE DB también expone información de esquema mediante el método <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> del objeto <xref:System.Data.OleDb.OleDbConnection>. Como argumentos, **GetOleDbSchemaTable** toma un <xref:System.Data.OleDb.OleDbSchemaGuid> que identifica la información de esquema que se va a devolver y una matriz de restricciones en esas columnas devueltas. **GetOleDbSchemaTable** devuelve un <xref:System.Data.DataTable> rellenado con la información de esquema solicitada.  
  
## <a name="in-this-section"></a>En esta sección  

 [GetSchema y colecciones de esquema](getschema-and-schema-collections.md)  
 Describe el método **GetSchema** y cómo se puede utilizar para recuperar y restringir la información de esquema de una base de datos.  
  
 Restricciones de esquema  
 Describe las restricciones de esquema que se pueden usar con **GetSchema**.  
  
 [Colecciones de esquemas comunes](common-schema-collections.md)  
 Describe todas las colecciones de esquemas comunes que admiten todos los proveedores administrados de .NET Framework.  
  
 [Colecciones de esquemas de SQL Server](sql-server-schema-collections.md)  
 Describe la colección de esquemas compatibles con el proveedor de datos .NET Framework para SQL Server.  
  
 [Colecciones de esquemas de Oracle](oracle-schema-collections.md)  
 Describe la colección de esquemas compatibles con el proveedor de datos .NET Framework para Oracle.  
  
 [Colecciones de esquemas de ODBC](odbc-schema-collections.md)  
 Describe las colecciones de esquemas para los controladores ODBC.  
  
 [Colecciones de esquemas de OLE DB](ole-db-schema-collections.md)  
 Describe las colecciones de esquemas para los proveedores OLE DB.  
  
## <a name="reference"></a>Referencia  

 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 Describe el método **GetSchema** de la <xref:System.Data.Common.DbConnection> clase.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 Describe el método **GetSchema** de la <xref:System.Data.Odbc.OdbcConnection> clase.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 Describe el método **GetSchema** de la <xref:System.Data.OleDb.OleDbConnection> clase.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 Describe el método **GetSchema** de la <xref:System.Data.OracleClient.OracleConnection> clase.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 Describe el método **GetSchema** de la <xref:System.Data.SqlClient.SqlConnection> clase.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 Describe el método **GetSchemaTable** de la <xref:System.Data.Common.DbDataReader> clase.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 Describe el método **GetSchemaTable** de la <xref:System.Data.Odbc.OdbcDataReader> clase.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 Describe el método **GetSchemaTable** de la <xref:System.Data.OleDb.OleDbDataReader> clase.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 Describe el método **GetSchemaTable** de la <xref:System.Data.OracleClient.OracleDataReader> clase.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 Describe el método **GetSchemaTable** de la <xref:System.Data.SqlClient.SqlDataReader> clase.  
  
## <a name="see-also"></a>Consulte también

- [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)
- [Información general de ADO.NET](ado-net-overview.md)
