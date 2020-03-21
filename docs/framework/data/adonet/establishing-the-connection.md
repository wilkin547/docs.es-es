---
title: Establecer la conexión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3af512f3-87d9-4005-9e2f-abb1060ff43f
ms.openlocfilehash: 4606ecb370b7e85cf5ebd92754471f5253321251
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149666"
---
# <a name="establishing-the-connection"></a>Establecer la conexión
Para conectarse a Microsoft SQL Server, use el objeto <xref:System.Data.SqlClient.SqlConnection> del proveedor de datos .NET Framework para SQL Server. Para conectarse a un origen de datos OLE DB, use el objeto <xref:System.Data.OleDb.OleDbConnection> del proveedor de datos .NET Framework para OLE DB. Para conectarse a un origen de datos ODBC, utilice el objeto <xref:System.Data.Odbc.OdbcConnection> del proveedor de datos .NET Framework para ODBC. Para conectarse a un origen de datos Oracle, utilice el objeto <xref:System.Data.OracleClient.OracleConnection> del proveedor de datos .NET Framework para ODBC. Para almacenar y recuperar cadenas de conexión de forma segura, consulte [Protección de](protecting-connection-information.md)la información de conexión .  
  
## <a name="closing-connections"></a>Cierre de conexiones  
 Recomendamos cerrar siempre la conexión cuando termine de utilizarla, para que la conexión pueda regresar al grupo. El bloque `Using` de Visual Basic o C# elimina automáticamente la conexión cuando el código sale del bloque, incluso en el caso de una excepción no controlada. Consulte [Using Statement](../../../csharp/language-reference/keywords/using-statement.md) y Using [Statement](../../../visual-basic/language-reference/statements/using-statement.md) para obtener más información.  
  
 También puede utilizar los métodos `Close` o `Dispose` del objeto de conexión correspondiente al proveedor que esté utilizando. Es posible que las conexiones que no se cierran explícitamente no se puedan agregar ni puedan regresar al grupo. Por ejemplo, una conexión que se ha salido del ámbito pero que no se ha cerrado explícitamente solo se devolverá al grupo de conexión si se ha alcanzado el tamaño máximo del grupo y la conexión aún es válida. Para obtener más información, vea Agrupación de [conexiones OLE DB, ODBC y Oracle](ole-db-odbc-and-oracle-connection-pooling.md).  
  
> [!NOTE]
> No llame `Close` `Dispose` ni en un **Connection**, un **DataReader** `Finalize` o cualquier otro objeto administrado en el método de la clase. En un finalizador, libere solo los recursos no administrados que pertenezcan directamente a su clase. Si la clase no dispone de recursos no administrados, no incluya un método `Finalize` en la definición de clase. Para obtener más información, consulte [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md).  
  
> [!NOTE]
> Los eventos de inicio y cierre de sesión no se provocarán en el servidor cuando se busque una conexión desde el grupo de conexiones o se devuelva a éste, puesto que la conexión no está cerrada realmente cuando se devuelve al grupo de conexiones. Para más información, consulte el artículo sobre la [agrupación de conexiones de SQL Server (ADO.NET)](sql-server-connection-pooling.md).  
  
## <a name="connecting-to-sql-server"></a>Conectarse a SQL Server  
 El proveedor de datos .NET Framework para SQL Server admite un formato de cadena de conexión que es similar al de OLE DB (ADO). Para consultar los nombres y valores válidos de formato de cadena, vea la propiedad <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> del objeto <xref:System.Data.SqlClient.SqlConnection>. También puede usar la clase <xref:System.Data.SqlClient.SqlConnectionStringBuilder> para crear cadenas de conexión sintácticamente válidas en tiempo de ejecución. Para obtener más información, vea [Generadores de cadenas de conexión](connection-string-builders.md).  
  
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
  
### <a name="integrated-security-and-aspnet"></a>Seguridad integrada y ASP.NET  
 La seguridad integrada de SQL Server (también conocida como conexiones de confianza) ayuda a proteger las conexiones a SQL Server dado que no expone el identificador y la contraseña de un usuario en la cadena de conexión y es el método recomendado para autenticar una conexión. La seguridad integrada utiliza la identidad de seguridad actual, o símbolo (token), del proceso en ejecución, que en aplicaciones de escritorio, es normalmente la identidad del usuario que actualmente ha iniciado la sesión.  
  
 La identidad de seguridad para aplicaciones ASP.NET se puede establecer en una de varias opciones diferentes. Para comprender mejor la identidad de seguridad que utiliza una aplicación ASP.NET al conectarse a SQL Server, vea [ASP.NET Suplantación](https://docs.microsoft.com/previous-versions/aspnet/xh507fc5(v=vs.100)), [autenticación de ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/eeyk640h(v=vs.100))y [Cómo: obtener acceso a SQL Server mediante](https://docs.microsoft.com/previous-versions/aspnet/bsz5788z(v=vs.100))la seguridad integrada de Windows .  
  
## <a name="connecting-to-an-ole-db-data-source"></a>Conexión a un origen de datos OLE DB  
 El proveedor de datos de .NET Framework para OLE DB proporciona conectividad a orígenes de datos expuestos mediante OLE DB (a través de SQLOLEDB, el proveedor OLE DB para SQL Server), mediante el objeto **OleDbConnection** .  
  
 En el proveedor de datos .NET Framework para OLE DB, el formato de cadena de conexión es idéntico al utilizado en ADO, con las siguientes excepciones:  
  
- Se requiere la palabra clave **Provider.**  
  
- No se admiten las palabras **clave URL,** **Proveedor remoto**y **Servidor remoto.**  
  
 Para obtener más información acerca de las cadenas de conexión OLE DB, vea el tema <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>. También puede usar <xref:System.Data.OleDb.OleDbConnectionStringBuilder> para crear cadenas de conexión en tiempo de ejecución.  
  
> [!NOTE]
> El objeto **OleDbConnection** no admite la configuración ni la recuperación de propiedades dinámicas específicas de un proveedor OLE DB. Solo se admiten las propiedades que se pueden proporcionar en la cadena de conexión para el proveedor OLE DB.  
  
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
  
## <a name="do-not-use-universal-data-link-files"></a>No utilice archivos de vínculo de datos universal  
 Es posible proporcionar información de conexión para un **OleDbConnection** en un archivo de vínculo de datos universal (UDL); sin embargo, debe evitar hacerlo. Los archivos UDL no están cifrados y exponen la información de cadena de conexión en texto sin cifrar. Un archivo UDL no se puede proteger mediante .NET Framework, ya que se trata de un recurso basado en un archivo externo a la aplicación.  
  
## <a name="connecting-to-an-odbc-data-source"></a>Conexión a un origen de datos ODBC  
 El proveedor de datos de .NET Framework para ODBC proporciona conectividad a orígenes de datos expuestos mediante ODBC mediante el objeto **OdbcConnection.**  
  
 En el proveedor de datos .NET Framework para ODBC, el formato de cadena de conexión está diseñado para que coincida lo más posible con el de ODBC. También puede proporcionar un nombre de origen de datos (DSN) ODBC. Para obtener más información sobre <xref:System.Data.Odbc.OdbcConnection> **OdbcConnection** , consulte el archivo .  
  
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
  
## <a name="connecting-to-an-oracle-data-source"></a>Conexión a un origen de datos Oracle  
 El proveedor de datos de .NET Framework para Oracle proporciona conectividad a orígenes de datos de Oracle mediante el objeto **OracleConnection.**  
  
 En el proveedor de datos .NET Framework para Oracle, el formato de cadena de conexión está diseñado para que coincida lo más posible con el del proveedor OLE DB para Oracle (MSDAORA). Para obtener más detalles sobre <xref:System.Data.OracleClient.OracleConnection> **OracleConnection**, consulte el archivo .  
  
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
  
## <a name="see-also"></a>Consulte también

- [Conectarse a un origen de datos](connecting-to-a-data-source.md)
- [Cadenas de conexión](connection-strings.md)
- [Agrupación de conexiones de OLE DB, ODBC y Oracle](ole-db-odbc-and-oracle-connection-pooling.md)
- [Información general de ADO.NET](ado-net-overview.md)
