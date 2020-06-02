---
title: Sintaxis de cadenas de conexión
description: Obtenga información sobre la sintaxis de las cadenas de conexión en ADO.NET. La sintaxis de cada proveedor se documenta en la propiedad ConnectionString.
ms.date: 05/22/2018
ms.assetid: 0977aeee-04d1-4cce-bbed-750c77fce06e
ms.openlocfilehash: bb29365a4729e731ddeffc7cfa61e379c3144a46
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287056"
---
# <a name="connection-string-syntax"></a>Sintaxis de cadenas de conexión
Cada proveedor de datos .NET Framework tiene un objeto `Connection` que hereda de la clase <xref:System.Data.Common.DbConnection>, así como una propiedad <xref:System.Data.Common.DbConnection.ConnectionString%2A> específica del proveedor. La sintaxis de la cadena de conexión específica de cada proveedor se indica en su propiedad `ConnectionString`. En la tabla siguiente se muestran los cuatro proveedores de datos que se incluyen en .NET Framework.  
  
|proveedor de datos de .NET Framework (.NET Framework data provider)|Descripción|  
|----------------------------------|-----------------|  
|<xref:System.Data.SqlClient>|Proporciona acceso de datos para Microsoft SQL Server. Para obtener más información acerca de la sintaxis de la cadena de conexión, vea <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.|  
|<xref:System.Data.OleDb>|Proporciona acceso de datos para orígenes de datos que se exponen mediante OLE DB. Para obtener más información acerca de la sintaxis de la cadena de conexión, vea <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>.|  
|<xref:System.Data.Odbc>|Proporciona acceso de datos para orígenes de datos que se exponen mediante ODBC. Para obtener más información acerca de la sintaxis de la cadena de conexión, vea <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A>.|  
|<xref:System.Data.OracleClient>|Proporciona acceso de datos para Oracle versión 8.1.7 o superior. Para obtener más información acerca de la sintaxis de la cadena de conexión, vea <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>.|  
  
## <a name="connection-string-builders"></a>Generadores de cadenas de conexión  
 ADO.NET 2.0 presentó los siguientes compiladores de cadenas de conexión para los proveedores de datos .NET Framework.  
  
- <xref:System.Data.SqlClient.SqlConnectionStringBuilder>  
  
- <xref:System.Data.OleDb.OleDbConnectionStringBuilder>  
  
- <xref:System.Data.Odbc.OdbcConnectionStringBuilder>  
  
- <xref:System.Data.OracleClient.OracleConnectionStringBuilder>  
  
 Los compiladores de cadenas de conexión permiten crear cadenas de conexión sintácticamente válidas en tiempo de ejecución. Por tanto, el usuario no tiene que concatenar manualmente los valores de las cadenas de conexión del código. Para obtener más información, vea [Generadores de cadenas de conexión](connection-string-builders.md).  

## <a name="windows-authentication"></a>Autenticación de Windows  
 Se recomienda usar la autenticación de Windows (a veces denominada *seguridad integrada*) para conectarse a los orígenes de datos que lo admiten. La sintaxis utilizada en la cadena de conexión varía dependiendo del proveedor. En la siguiente tabla se muestra la sintaxis de autenticación de Windows utilizada con los proveedores de datos .NET Framework.  
  
|Proveedor|Sintaxis|  
|--------------|------------|  
|`SqlClient`|`Integrated Security=true;`<br /><br /> `-- or --`<br /><br /> `Integrated Security=SSPI;`|  
|`OleDb`|`Integrated Security=SSPI;`|  
|`Odbc`|`Trusted_Connection=yes;`|  
|`OracleClient`|`Integrated Security=yes;`|  
  
> [!NOTE]
> `Integrated Security=true` produce una excepción cuando se usa con el proveedor `OleDb`.  
  
## <a name="sqlclient-connection-strings"></a>Cadenas de conexión SqlClient  
La sintaxis de una cadena de conexión de <xref:System.Data.SqlClient.SqlConnection> se documenta en la propiedad <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType>. Puede usar la propiedad <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> para obtener o establecer una cadena de conexión para una base de datos de SQL Server. Si necesita conectarse a una versión anterior de SQL Server, debe usar el proveedor de datos .NET Framework para OleDb (<xref:System.Data.OleDb>). La mayoría de las palabras clave de cadenas de conexión se corresponden también con las propiedades de <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.  

> [!IMPORTANT]
> La configuración predeterminada de la `Persist Security Info` palabra clave es `false` . Si se establece en `true` o `yes`, permite obtener información de seguridad confidencial de la conexión, incluidos el identificador de usuario y la contraseña, una vez abierta la conexión. Mantenga `Persist Security Info` establecido en `false` para asegurarse de que un origen que no es de confianza no tiene acceso a información confidencial de la cadena de conexión.  

### <a name="windows-authentication-with-sqlclient"></a>Autenticación de Windows con SqlClient
 Cada una de las siguientes formas de sintaxis utiliza la autenticación de Windows para conectarse a la base de datos **AdventureWorks** en un servidor local.  
  
```csharp  
"Persist Security Info=False;Integrated Security=true;  
    Initial Catalog=AdventureWorks;Server=MSSQL1"  
"Persist Security Info=False;Integrated Security=SSPI;  
    database=AdventureWorks;server=(local)"  
"Persist Security Info=False;Trusted_Connection=True;  
    database=AdventureWorks;server=(local)"  
```  
  
### <a name="sql-server-authentication-with-sqlclient"></a>Autenticación SQL Server con SqlClient
 Es preferible utilizar la autenticación de Windows para conectarse a SQL Server. No obstante, si se requiere autenticación de SQL Server, deberá utilizar la siguiente sintaxis para especificar un nombre de usuario y una contraseña. En este ejemplo, los asteriscos representan un nombre de usuario y una contraseña válidos.  
  
```csharp  
"Persist Security Info=False;User ID=*****;Password=*****;Initial Catalog=AdventureWorks;Server=MySqlServer"  
```  

Cuando se conecte a Azure SQL Database o a Azure SQL Data Warehouse y proporcione un inicio de sesión en el formato, asegúrese de `user@servername` que el `servername` valor del inicio de sesión coincida con el valor proporcionado para `Server=` .

> [!NOTE]
> La autenticación de Windows tiene prioridad sobre los inicios de sesión de SQL Server. Si especifica Integrated Security=true junto con un nombre de usuario y una contraseña, se ignorarán el nombre de usuario y la contraseña, y se usará la autenticación de Windows.  

### <a name="connect-to-a-named-instance-of-sql-server"></a>Conectarse a una instancia con nombre de SQL Server
Para conectarse a una instancia con nombre de SQL Server, use la sintaxis del *nombre nombre\instancia del servidor* .  
  
```csharp  
"Data Source=MySqlServer\MSSQL1;"  
```  

A la hora de crear una cadena de conexión, también puede establecer la propiedad <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A> del `SqlConnectionStringBuilder` en el nombre de instancia. La propiedad <xref:System.Data.SqlClient.SqlConnection.DataSource%2A> de un objeto <xref:System.Data.SqlClient.SqlConnection> es de solo lectura.  
  
### <a name="type-system-version-changes"></a>Cambios en Type System Version  
 La `Type System Version` palabra clave en un <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> especifica la representación del lado cliente de los tipos de SQL Server. Para obtener más información sobre la palabra clave <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType>, vea `Type System Version`.  
  
## <a name="connecting-and-attaching-to-sql-server-express-user-instances"></a>Concatenar y adjuntar a instancias de usuario de SQL Server Express  
 Las instancias de usuario son una característica de SQL Server Express. Permiten que un usuario que ejecuta una cuenta de Windows local y con privilegios mínimos adjunte y ejecute una base de datos de SQL Server sin necesidad de tener privilegios administrativos. Una instancia de usuario se ejecuta con las credenciales de Windows del usuario, no como un servicio.  
  
 Para obtener más información sobre cómo trabajar con instancias de usuario, vea [SQL Server Express las instancias de usuario](./sql/sql-server-express-user-instances.md).  
  
## <a name="using-trustservercertificate"></a>Usar TrustServerCertificate  
 La `TrustServerCertificate` palabra clave solo es válida cuando se conecta a una instancia de SQL Server con un certificado válido. Cuando `TrustServerCertificate` se establece en `true`, la capa de transporte utilizará SSL para cifrar el canal y evitar recorrer la cadena de certificados para validar la confianza.  
  
```csharp  
"TrustServerCertificate=true;"
```  
  
> [!NOTE]
> Si `TrustServerCertificate` se establece en `true` y se activa el cifrado, se utilizará el nivel de cifrado especificado en el servidor aunque `Encrypt` esté establecido en `false` en la cadena de conexión. De lo contrario, se producirá un error en la conexión.  
  
### <a name="enabling-encryption"></a>Habilitar el cifrado  
 Para habilitar el cifrado cuando no se ha aprovisionado un certificado en el servidor, las opciones **forzar cifrado de protocolo** y **confiar en certificado de servidor** deben establecerse en Administrador de configuración de SQL Server. En ese caso, el cifrado utilizará un certificado de servidor autofirmado sin validación si no se ha proporcionado ningún certificado comprobable en el servidor.  
  
 La configuración de las aplicaciones no puede reducir el nivel de seguridad configurado en SQL Server, sino que en todo caso puede reforzarlo. Una aplicación puede solicitar el cifrado estableciendo `TrustServerCertificate` las `Encrypt` palabras clave y en `true` , garantizando que el cifrado se realiza incluso cuando no se ha aprovisionado un certificado de servidor y no se ha configurado el **cifrado de protocolo** para el cliente. Sin embargo, si en la configuración del cliente no está habilitado `TrustServerCertificate`, seguirá siendo necesario un certificado de servidor.  
  
 En la siguiente tabla se describen todos los casos.  
  
|Cliente configurado con Forzar cifrado de protocolo|Cliente configurado con Confiar en certificado de servidor|Cadena de conexión/atributo Cifrar/Utilizar cifrado para los datos|Cadena de conexión/atributo Confiar en certificado de servidor|Resultado|  
|----------------------------------------------|---------------------------------------------|-------------------------------------------------------------------|-----------------------------------------------------------|------------|  
|No|N/D|No (valor predeterminado)|Se ignora.|No se produce el cifrado.|  
|No|N/D|Sí|No (valor predeterminado)|El cifrado solamente se produce si hay un certificado de servidor comprobable; de lo contrario, se produce un error en el intento de conexión.|  
|No|N/D|Sí|Sí|El cifrado se produce siempre, pero puede que se utilice un certificado de servidor autofirmado.|  
|Sí|No|Se ignora.|Se ignora.|El cifrado solo se produce si hay un certificado de servidor que se pueda comprobar; de lo contrario, se produce un error en el intento de conexión.|  
|Sí|Sí|No (valor predeterminado)|Se ignora.|El cifrado se produce siempre, pero puede que se utilice un certificado de servidor autofirmado.|  
|Sí|Sí|Sí|No (valor predeterminado)|El cifrado solo se produce si hay un certificado de servidor que se pueda comprobar; de lo contrario, se produce un error en el intento de conexión.|  
|Sí|Sí|Sí|Sí|El cifrado se produce siempre, pero puede que se utilice un certificado de servidor autofirmado.|  
  
 Para obtener más información, vea [Usar el cifrado sin validación](/sql/relational-databases/native-client/features/using-encryption-without-validation).
  
## <a name="oledb-connection-strings"></a>Cadenas de conexión OleDb  
 La propiedad <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> de un objeto <xref:System.Data.OleDb.OleDbConnection> permite obtener o establecer una cadena de conexión para un origen de datos OLE DB, como Microsoft Access. Asimismo puede crear una cadena de conexión de `OleDb` en tiempo de ejecución mediante la clase <xref:System.Data.OleDb.OleDbConnectionStringBuilder>.  
  
### <a name="oledb-connection-string-syntax"></a>Sintaxis de cadena de conexión OleDb  
 Para una cadena de conexión <xref:System.Data.OleDb.OleDbConnection>, debe proporcionar un nombre de proveedor. La siguiente cadena de conexión conecta a una base de datos Microsoft Access mediante el proveedor Jet. Tenga en cuenta que las palabras clave `User ID` y `Password` son opcionales si la base de datos no está protegida (opción predeterminada).  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0; Data Source=d:\Northwind.mdb;User ID=Admin;Password=;
```  
  
 Si la base de datos Jet está protegida mediante la seguridad de nivel de usuario, debe proporcionar la ubicación del archivo de información de grupo de trabajo (.mdw). Este archivo se usa para validar las credenciales presentadas en la cadena de conexión.  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0;Data Source=d:\Northwind.mdb;Jet OLEDB:System Database=d:\NorthwindSystem.mdw;User ID=*****;Password=*****;  
```  
  
> [!IMPORTANT]
> Es posible proporcionar información de conexión para un **OleDbConnection** en un archivo de vínculo de datos universal (UdL); sin embargo, debe evitar hacerlo. Los archivos UDL no están cifrados y exponen la información de cadena de conexión en texto sin cifrar. Un archivo UDL no se puede proteger mediante .NET Framework, ya que se trata de un recurso basado en un archivo externo a la aplicación. Los archivos UDL no se admiten en **SqlClient**.  
  
### <a name="using-datadirectory-to-connect-to-accessjet"></a>Utilizar DataDirectory para conectarse a Access/Jet  
 `DataDirectory` no es exclusivo de `SqlClient`. También se puede utilizar con los proveedores de datos de .NET <xref:System.Data.OleDb> y <xref:System.Data.Odbc>. La siguiente cadena <xref:System.Data.OleDb.OleDbConnection> de ejemplo muestra la sintaxis necesaria para conectarse a la base de datos Northwind.mdb situada en la carpeta app_data de la aplicación. La base de datos del sistema (System.mdw) también está almacenada en esa ubicación.  
  
```csharp  
"Provider=Microsoft.Jet.OLEDB.4.0;  
Data Source=|DataDirectory|\Northwind.mdb;  
Jet OLEDB:System Database=|DataDirectory|\System.mdw;"  
```  
  
> [!IMPORTANT]
> No es necesario especificar la ubicación de la base de datos del sistema en la cadena de conexión si la base de datos Access/Jet no está protegida. La seguridad está desactivada de forma predeterminada y todos los usuarios se conectan como el usuario Admin integrado, con una contraseña en blanco. Aun cuando la seguridad a nivel de usuario esté correctamente implementada, una base de datos Jet sigue siendo vulnerable a los ataques. Por eso no se recomienda almacenar información delicada en una base de datos Access/Jet a causa de la fragilidad inherente a su esquema de seguridad basado en archivos.  
  
### <a name="connecting-to-excel"></a>Conectarse a Excel  
 Para conectarse a un libro de Excel se utiliza el proveedor Microsoft Jet. En la siguiente cadena de conexión, la palabra clave `Extended Properties` establece propiedades que son específicas de Excel. "HDR=Yes;" indica que la primera fila contiene nombres de columna, no datos, e "IMEX=1;" indica al controlador que siempre lea las columnas de datos "entremezclados" como texto.  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0;Data Source=D:\MyExcel.xls;Extended Properties=""Excel 8.0;HDR=Yes;IMEX=1""  
```  
  
 Tenga en cuenta que el carácter de comilla doble necesario en `Extended Properties` también debe ir incluido entre comillas dobles.  
  
### <a name="data-shape-provider-connection-string-syntax"></a>Sintaxis de cadena de conexión del proveedor de formas de datos  
 Utilice las palabras clave `Provider` y `Data Provider` cuando use el proveedor de formas de datos de Microsoft. En el siguiente ejemplo se utiliza el proveedor de formas para conectarse a una instancia local de SQL Server.  
  
```csharp  
"Provider=MSDataShape;Data Provider=SQLOLEDB;Data Source=(local);Initial Catalog=pubs;Integrated Security=SSPI;"
```  
  
## <a name="odbc-connection-strings"></a>Cadenas de conexión Odbc  
 La propiedad <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A> de una <xref:System.Data.Odbc.OdbcConnection> permite obtener o establecer una cadena de conexión para un origen de datos OLE DB. Las cadenas de conexión Odbc también son compatibles con <xref:System.Data.Odbc.OdbcConnectionStringBuilder>.  
  
 En la siguiente cadena de conexión se utiliza el Controlador de texto de Microsoft.  
  
```csharp  
Driver={Microsoft Text Driver (*.txt; *.csv)};DBQ=d:\bin  
```  
  
### <a name="using-datadirectory-to-connect-to-visual-foxpro"></a>Utilizar DataDirectory para conectarse a Visual FoxPro  
 El siguiente ejemplo de cadena de conexión <xref:System.Data.Odbc.OdbcConnection> muestra cómo se utiliza `DataDirectory` para conectarse a un archivo de Microsoft Visual FoxPro.  
  
```csharp  
"Driver={Microsoft Visual FoxPro Driver};  
SourceDB=|DataDirectory|\MyData.DBC;SourceType=DBC;"  
```  
  
## <a name="oracle-connection-strings"></a>Cadenas de conexión Oracle  
 La propiedad <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A> de una <xref:System.Data.OracleClient.OracleConnection> permite obtener o establecer una cadena de conexión para un origen de datos OLE DB. Las cadenas de conexión Oracle también son compatibles con <xref:System.Data.OracleClient.OracleConnectionStringBuilder>.  
  
```csharp
Data Source=Oracle9i;User ID=*****;Password=*****;  
```  
  
 Para obtener más información acerca de la sintaxis de cadena de conexión ODBC, vea <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>.  
  
## <a name="see-also"></a>Consulte también

- [Cadenas de conexión](connection-strings.md)
- [Conectarse a un origen de datos](connecting-to-a-data-source.md)
- [Información general de ADO.NET](ado-net-overview.md)
