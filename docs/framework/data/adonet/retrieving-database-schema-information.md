---
title: Recuperar información del esquema de la base de datos
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 885d3c9ad61c9099c960ddb0c0f77fa8a98dbefa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61664251"
---
# <a name="retrieving-database-schema-information"></a>Recuperar información del esquema de la base de datos
La obtención de información de esquema de una base de datos se efectúa con el proceso de detección de esquemas. Detección de esquemas permite que las aplicaciones soliciten a los proveedores administrados encontraron y devuelvan información acerca del esquema de base de datos, también conocido como *metadatos*, de una base de datos. Los diferentes elementos del esquema de base de datos, como tablas, columnas y procedimientos almacenados, se exponen a través de colecciones de esquemas. Cada colección de esquemas contiene diversa información de esquema relativa al proveedor que se está utilizando.  
  
 Cada una de las implementan proveedores administrados de .NET Framework la **GetSchema** método en el **conexión** clase y la información de esquema que se devuelve desde el **GetSchema**método viene en forma de un <xref:System.Data.DataTable>. El **GetSchema** método es un método sobrecargado que proporciona parámetros opcionales para especificar la colección de esquemas para devolver y para restringir la cantidad de información devuelta.  
  
 Los proveedores de datos de .NET Framework para OLE DB, ODBC, Oracle y SqlClient proporcionan un **GetSchemaTable** método que devuelve un objeto DataTable que describe los metadatos de columna de la **DataReader**.  
  
 Además el proveedor de datos .NET Framework para OLE DB también expone información de esquema mediante el método <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> del objeto <xref:System.Data.OleDb.OleDbConnection>. Como argumentos, **GetOleDbSchemaTable** toma un <xref:System.Data.OleDb.OleDbSchemaGuid> que identifica la información de esquema para devolver y una matriz de restricciones en esas columnas devueltas. **GetOleDbSchemaTable** devuelve un <xref:System.Data.DataTable> rellena con la información de esquema solicitada.  
  
## <a name="in-this-section"></a>En esta sección  
 [GetSchema y colecciones de esquema](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 Describe el **GetSchema** método y cómo se puede usar para recuperar y restringir información de esquema desde una base de datos.  
  
 Restricciones de esquema  
 Describe las restricciones de esquema que se pueden usar con **GetSchema**.  
  
 [Colecciones de esquemas comunes](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 Describe todas las colecciones de esquemas comunes que admiten todos los proveedores administrados de .NET Framework.  
  
 [Colecciones de esquemas de SQL Server](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 Describe la colección de esquemas compatibles con el proveedor de datos .NET Framework para SQL Server.  
  
 [Colecciones de esquemas de Oracle](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 Describe la colección de esquemas compatibles con el proveedor de datos .NET Framework para Oracle.  
  
 [Colecciones de esquemas de ODBC](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 Describe las colecciones de esquemas para los controladores ODBC.  
  
 [Colecciones de esquemas de OLE DB](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 Describe las colecciones de esquemas para los proveedores OLE DB.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 Describe el **GetSchema** método de la <xref:System.Data.Common.DbConnection> clase.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 Describe el **GetSchema** método de la <xref:System.Data.Odbc.OdbcConnection> clase.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 Describe el **GetSchema** método de la <xref:System.Data.OleDb.OleDbConnection> clase.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 Describe el **GetSchema** método de la <xref:System.Data.OracleClient.OracleConnection> clase.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 Describe el **GetSchema** método de la <xref:System.Data.SqlClient.SqlConnection> clase.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 Describe el **GetSchemaTable** método de la <xref:System.Data.Common.DbDataReader> clase.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 Describe el **GetSchemaTable** método de la <xref:System.Data.Odbc.OdbcDataReader> clase.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 Describe el **GetSchemaTable** método de la <xref:System.Data.OleDb.OleDbDataReader> clase.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 Describe el **GetSchemaTable** método de la <xref:System.Data.OracleClient.OracleDataReader> clase.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 Describe el **GetSchemaTable** método de la <xref:System.Data.SqlClient.SqlDataReader> clase.  
  
## <a name="see-also"></a>Vea también

- [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
