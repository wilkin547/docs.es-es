---
description: Más información acerca de cómo recuperar información de esquema de base de datos
title: Recuperar información del esquema de la base de datos
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 84ac94a72b23d0b1d6924600f2fd33b2a285eab8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663409"
---
# <a name="retrieving-database-schema-information"></a>Recuperar información del esquema de la base de datos

La obtención de información de esquema de una base de datos se efectúa con el proceso de detección de esquemas. La detección de esquemas permite que las aplicaciones soliciten a los proveedores administrados que busquen y devuelvan información sobre el esquema de la base de datos, también conocido como los *metadatos*, de una base de datos concreta. Los diferentes elementos del esquema de base de datos, como tablas, columnas y procedimientos almacenados, se exponen a través de colecciones de esquemas. Cada colección de esquemas contiene diversa información de esquema relativa al proveedor que se está utilizando.  
  
 Cada uno de los proveedores administrados de .NET Framework implementa el método **GetSchema** en la clase **Connection** , y la información de esquema que se devuelve desde el método **GetSchema** tiene el formato <xref:System.Data.DataTable> . El método **GetSchema** es un método sobrecargado que proporciona parámetros opcionales para especificar la colección de esquemas que se devolverá y restringe la cantidad de información devuelta.  
  
 Los proveedores de datos de .NET Framework para OLE DB, ODBC, Oracle y SqlClient proporcionan un método **GetSchemaTable** que devuelve un DataTable que describe los metadatos de columna del **DataReader**.  
  
 Además el proveedor de datos .NET Framework para OLE DB también expone información de esquema mediante el método <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> del objeto <xref:System.Data.OleDb.OleDbConnection>. Como argumentos, **GetOleDbSchemaTable** toma un <xref:System.Data.OleDb.OleDbSchemaGuid> que identifica la información de esquema que se va a devolver y una matriz de restricciones en esas columnas devueltas. **GetOleDbSchemaTable** devuelve un <xref:System.Data.DataTable> rellenado con la información de esquema solicitada.  
  
## <a name="in-this-section"></a>En esta sección  

 [Colecciones GetSchema y Schema](getschema-and-schema-collections.md)  
 Se describe el método **GetSchema**, y cómo se puede usar para recuperar y restringir la información del esquema de una base de datos.  
  
 Restricciones de esquema  
 Se describen las restricciones de esquema que se pueden usar con **GetSchema**.  
  
 [Colecciones de esquemas comunes](common-schema-collections.md)  
 Describe todas las colecciones de esquemas comunes que admiten todos los proveedores administrados de .NET Framework.  
  
 [SQL Server colecciones de esquemas](sql-server-schema-collections.md)  
 Describe la colección de esquemas compatibles con el proveedor de datos .NET Framework para SQL Server.  
  
 [Colecciones de esquemas de Oracle](oracle-schema-collections.md)  
 Describe la colección de esquemas compatibles con el proveedor de datos .NET Framework para Oracle.  
  
 [Colecciones de esquemas de ODBC](odbc-schema-collections.md)  
 Describe las colecciones de esquemas para los controladores ODBC.  
  
 [Colecciones de esquemas de OLE DB](ole-db-schema-collections.md)  
 Describe las colecciones de esquemas para los proveedores OLE DB.  
  
## <a name="reference"></a>Referencia  

 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 Se describe el método **GetSchema** de la clase <xref:System.Data.Common.DbConnection>.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 Se describe el método **GetSchema** de la clase <xref:System.Data.Odbc.OdbcConnection>.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 Se describe el método **GetSchema** de la clase <xref:System.Data.OleDb.OleDbConnection>.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 Se describe el método **GetSchema** de la clase <xref:System.Data.OracleClient.OracleConnection>.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 Se describe el método **GetSchema** de la clase <xref:System.Data.SqlClient.SqlConnection>.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 Se describe el método **GetSchemaTable** de la clase <xref:System.Data.Common.DbDataReader>.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 Se describe el método **GetSchemaTable** de la clase <xref:System.Data.Odbc.OdbcDataReader>.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 Se describe el método **GetSchemaTable** de la clase <xref:System.Data.OleDb.OleDbDataReader>.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 Se describe el método **GetSchemaTable** de la clase <xref:System.Data.OracleClient.OracleDataReader>.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 Se describe el método **GetSchemaTable** de la clase <xref:System.Data.SqlClient.SqlDataReader>.  
  
## <a name="see-also"></a>Vea también

- [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)
- [Información general de ADO.NET](ado-net-overview.md)
