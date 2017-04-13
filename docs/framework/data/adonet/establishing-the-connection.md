---
title: "Establecer la conexi&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3af512f3-87d9-4005-9e2f-abb1060ff43f
caps.latest.revision: 7
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Establecer la conexi&#243;n
Para conectarse a Microsoft SQL Server, use el objeto <xref:System.Data.SqlClient.SqlConnection> del proveedor de datos .NET Framework para SQL Server.  Para conectarse a un origen de datos OLE DB, use el objeto <xref:System.Data.OleDb.OleDbConnection> del proveedor de datos .NET Framework para OLE DB.  Para conectarse a un origen de datos ODBC, utilice el objeto <xref:System.Data.Odbc.OdbcConnection> del proveedor de datos .NET Framework para ODBC.  Para conectarse a un origen de datos Oracle, utilice el objeto <xref:System.Data.OracleClient.OracleConnection> del proveedor de datos .NET Framework para ODBC.  Para almacenar y recuperar de forma segura cadenas de conexión, vea [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## Cierre de conexiones  
 Recomendamos cerrar siempre la conexión cuando termine de utilizarla, para que la conexión pueda regresar al grupo.  El bloque `Using` de Visual Basic o C\# elimina automáticamente la conexión cuando el código sale del bloque, incluso en el caso de una excepción no controlada.  Para obtener más información, vea [using \(Instrucción\)](../Topic/using%20Statement%20\(C%23%20Reference\).md) y [Using \(Instrucción\)](../Topic/Using%20Statement%20\(Visual%20Basic\).md).  
  
 También puede utilizar los métodos `Close` o `Dispose` del objeto de conexión correspondiente al proveedor que esté utilizando.  Es posible que las conexiones que no se cierran explícitamente no se puedan agregar ni puedan regresar al grupo.  Por ejemplo, una conexión que se ha salido del ámbito pero que no se ha cerrado explícitamente solo se devolverá al grupo de conexión si se ha alcanzado el tamaño máximo del grupo y la conexión aún es válida.  Para obtener más información, consulta [Agrupación de conexiones OLE DB, ODBC y Oracle](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md).  
  
> [!NOTE]
>  No llame a `Close` o a `Dispose` en un objeto **Connection**, un objeto **DataReader** o cualquier otro objeto administrado en el método `Finalize` de la clase.  En un finalizador, libere solo los recursos no administrados que pertenezcan directamente a su clase.  Si la clase no dispone de recursos no administrados, no incluya un método `Finalize` en la definición de clase.  Para obtener más información, consulta [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
> [!NOTE]
>  Los eventos de inicio y cierre de sesión no se provocarán en el servidor cuando se busque una conexión desde el grupo de conexiones o se devuelva a éste, puesto que la conexión no está cerrada realmente cuando se devuelve al grupo de conexiones.  Para obtener más información, consulta [Agrupación de conexiones en SQL Server \(ADO.NET\)](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).  
  
## Conexión a SQL Server  
 El proveedor de datos .NET Framework para SQL Server admite un formato de cadena de conexión que es similar al de OLE DB \(ADO\).  Para consultar los nombres y valores válidos de formato de cadena, vea la propiedad <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> del objeto <xref:System.Data.SqlClient.SqlConnection>.  También puede usar la clase <xref:System.Data.SqlClient.SqlConnectionStringBuilder> para crear cadenas de conexión sintácticamente válidas en tiempo de ejecución.  Para obtener más información, consulta [Compiladores de cadenas de conexión](../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
 El siguiente código de ejemplo demuestra cómo crear y abrir una conexión a una base de datos SQL Server.  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New SqlConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (SqlConnection connection = new SqlConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
### Seguridad integrada y ASP.NET  
 La seguridad integrada de SQL Server \(también conocida como conexiones de confianza\) ayuda a proteger las conexiones a SQL Server dado que no expone el identificador y la contraseña de un usuario en la cadena de conexión y es el método recomendado para autenticar una conexión.  La seguridad integrada utiliza la identidad de seguridad actual, o símbolo \(token\), del proceso en ejecución, que  en aplicaciones de escritorio, es normalmente la identidad del usuario que actualmente ha iniciado la sesión.  
  
 La identidad de seguridad para aplicaciones ASP.NET se puede establecer en una de varias opciones diferentes.  Para comprender mejor la identidad de seguridad que utiliza una aplicación ASP.NET al establecer una conexión a SQL Server, vea [ASP.NET Impersonation](../Topic/ASP.NET%20Impersonation.md), [ASP.NET Authentication](../Topic/ASP.NET%20Authentication.md) y [How to: Access SQL Server Using Windows Integrated Security](../Topic/How%20to:%20Access%20SQL%20Server%20Using%20Windows%20Integrated%20Security.md).  
  
## Conexión a un origen de datos OLE DB  
 El proveedor de datos .NET Framework para OLE DB proporciona conectividad a orígenes de datos expuestos mediante OLE DB \(a través de SQLOLEDB, el proveedor OLE DB para SQL Server\) usando el objeto **OleDbConnection**.  
  
 En el proveedor de datos .NET Framework para OLE DB, el formato de cadena de conexión es idéntico al utilizado en ADO, con las siguientes excepciones:  
  
-   Se necesita la palabra clave **Proveedor**.  
  
-   No se admiten las palabras clave **URL**, **Proveedor remoto** y **Servidor remoto**.  
  
 Para obtener más información acerca de las cadenas de conexión OLE DB, vea el tema <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>.  También puede usar <xref:System.Data.OleDb.OleDbConnectionStringBuilder> para crear cadenas de conexión en tiempo de ejecución.  
  
> [!NOTE]
>  El objeto **OleDbConnection** no admite la configuración ni la recuperación de propiedades dinámicas específicas de un proveedor OLE DB.  Solo se admiten las propiedades que se pueden proporcionar en la cadena de conexión para el proveedor OLE DB.  
  
 El siguiente código de ejemplo demuestra cómo crear y abrir una conexión a un origen de datos OLE DB.  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OleDbConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OleDbConnection connection =   
  new OleDbConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
## No utilice archivos de vínculo de datos universal  
 Se puede proporcionar información de conexión para un objeto **OleDbConnection** en un archivo UDL \(Universal Data Link\), pero conviene evitarlo.  Los archivos UDL no están cifrados y exponen la información de cadena de conexión en texto sin cifrar.  Un archivo UDL no se puede proteger mediante .NET Framework, ya que se trata de un recurso basado en un archivo externo a la aplicación.  
  
## Conexión a un origen de datos ODBC  
 El proveedor de datos .NET Framework para ODBC proporciona conectividad a orígenes de datos expuestos mediante ODBC utilizando el objeto **OdbcConnection**.  
  
 En el proveedor de datos .NET Framework para ODBC, el formato de cadena de conexión está diseñado para que coincida lo más posible con el de ODBC.  También puede proporcionar un nombre de origen de datos \(DSN\) ODBC.  Para obtener información más detallada acerca de **OdbcConnection**, vea la [Clase OdbcConnection](frlrfSystemDataOdbcOdbcConnectionClassTopic).  
  
 El siguiente código de ejemplo demuestra cómo crear y abrir una conexión a un origen de datos ODBC.  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OdbcConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OdbcConnection connection =   
  new OdbcConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
## Conexión a un origen de datos Oracle  
 El proveedor de datos .NET Framework para Oracle proporciona conectividad a orígenes de datos Oracle utilizando el objeto **OracleConnection**.  
  
 En el proveedor de datos .NET Framework para Oracle, el formato de cadena de conexión está diseñado para que coincida lo más posible con el del proveedor OLE DB para Oracle \(MSDAORA\).  Para obtener información más detallada acerca de **OracleConnection**, vea la [Clase OracleConnection](frlrfSystemDataOracleClientOracleConnectionClassTopic).  
  
 El siguiente código de ejemplo demuestra cómo crear y abrir una conexión a un origen de datos Oracle.  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OracleConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OracleConnection connection =   
  new OracleConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
OracleConnection nwindConn = new OracleConnection("Data Source=MyOracleServer;Integrated Security=yes;");  
nwindConn.Open();  
```  
  
## Vea también  
 [Conectarse a un origen de datos](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)   
 [Cadenas de conexión](../../../../docs/framework/data/adonet/connection-strings.md)   
 [Agrupación de conexiones OLE DB, ODBC y Oracle](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)