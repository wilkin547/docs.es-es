---
title: Obtener un objeto DbProviderFactory
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a16e4a4d-6a5b-45db-8635-19570e4572ae
ms.openlocfilehash: 0e2efd593019199ff641610b8602825cc60d4661
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149471"
---
# <a name="obtaining-a-dbproviderfactory"></a>Obtener un objeto DbProviderFactory
El proceso de obtención de <xref:System.Data.Common.DbProviderFactory> implica pasar información sobre un proveedor de datos a la clase <xref:System.Data.Common.DbProviderFactories>. En función de esta información, el método <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> crea un generador del proveedor fuertemente tipado. Por ejemplo, para crear <xref:System.Data.SqlClient.SqlClientFactory>, se puede pasar a `GetFactory` una cadena con el nombre de proveedor especificado como "System.Data.SqlClient". La otra sobrecarga de `GetFactory` toma <xref:System.Data.DataRow>. Una vez creado el generador del proveedor, se pueden utilizar sus métodos para crear objetos adicionales. Entre los métodos de `SqlClientFactory` se incluyen <xref:System.Data.SqlClient.SqlClientFactory.CreateConnection%2A>, <xref:System.Data.SqlClient.SqlClientFactory.CreateCommand%2A> y <xref:System.Data.SqlClient.SqlClientFactory.CreateDataAdapter%2A>.  
  
> [!NOTE]
> Las clases <xref:System.Data.OracleClient.OracleClientFactory>, <xref:System.Data.Odbc.OdbcFactory> y <xref:System.Data.OleDb.OleDbFactory> de .NET Framework también proporcionan una funcionalidad similar.  
  
## <a name="registering-dbproviderfactories"></a>Registrar DbProviderFactories  
 Cada proveedor de datos de .NET Framework que admite una clase basada en fábrica registra información de configuración en la sección **DbProviderFactories** del archivo **machine.config** del equipo local. El siguiente fragmento del archivo de configuración muestra la sintaxis y formato de <xref:System.Data.SqlClient>.  
  
```xml  
<system.data>  
  <DbProviderFactories>  
    <add name="SqlClient Data Provider"  
     invariant="System.Data.SqlClient"
     description=".Net Framework Data Provider for SqlServer"
     type="System.Data.SqlClient.SqlClientFactory, System.Data,
     Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
    />  
  </DbProviderFactories>  
</system.data>  
```  
  
 El atributo **invariable** identifica el proveedor de datos subyacente. Esta sintaxis de nomenclatura en tres partes también se utiliza al crear un nuevo generador y para identificar al proveedor en un archivo de configuración de la aplicación, de manera que el nombre de proveedor, junto con sus cadenas de conexión asociadas, se puedan recuperar en tiempo de conexión.  
  
## <a name="retrieving-provider-information"></a>Recuperar información del proveedor  
 Se puede recuperar información acerca de todos los proveedores de datos instalados en el equipo local utilizando el método <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A>. Devuelve un <xref:System.Data.DataTable> **dbProviderFactories** con nombre que contiene las columnas descritas en la tabla siguiente.  
  
|Índice de columna|Nombre de la columna|Salida de ejemplo|Descripción|  
|--------------------|-----------------|--------------------|-----------------|  
|0|**Nombre**|Proveedor de datos SqlClient|Nombre legible del proveedor de datos|  
|1|**Descripción**|Proveedor de datos .NET Framework para SqlServer|Descripción legible del proveedor de datos|  
|2|**InvariantName**|System.Data.SqlClient|Nombre que se puede utilizar mediante programación para hacer referencia al proveedor de datos|  
|3|**AssemblyQualifiedName**|System.Data.SqlClient.SqlClientFactory, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089|Nombre completo de la clase de generador, el cual tiene información suficiente para crear la instancia del objeto|  
  
 Este `DataTable` se puede utilizar para permitir a un usuario seleccionar un <xref:System.Data.DataRow> en tiempo de ejecución. El `DataRow` seleccionado se puede pasar al método <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> para crear un <xref:System.Data.Common.DbProviderFactory> fuertemente tipado. Un <xref:System.Data.DataRow> seleccionado se puede pasar al método `GetFactory` para crear el objeto `DbProviderFactory` deseado.  
  
## <a name="listing-the-installed-provider-factory-classes"></a>Enumerar las clases de generador del proveedor instaladas  
 Este ejemplo muestra cómo el método <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A> devuelve un <xref:System.Data.DataTable> con información sobre los proveedores instalados. El código recorre en iteración cada fila de `DataTable` y muestra información de todos los proveedores instalados en la ventana de la consola.  
  
 [!code-csharp[DataWorks DbProviderFactories#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/VB/source.vb#1)]  
  
## <a name="using-application-configuration-files-to-store-factory-information"></a>Utilizar archivos de configuración de la aplicación para almacenar información del generador  
 El patrón de diseño utilizado para trabajar con fábricas implica almacenar información de proveedor y cadena de conexión en un archivo de configuración de aplicación, como **app.config** para una aplicación de Windows y **web.config** para una aplicación de ASP.NET.  
  
 El siguiente fragmento de archivo de configuración muestra cómo guardar dos cadenas de conexión, una denominada "NorthwindSQL", para la conexión a la base de datos Northwind de SQL Server, y la otra denominada "NorthwindAccess", para una conexión a la base de datos Northwind de Access/Jet. El nombre **invariable** se utiliza para el atributo **providerName.**  
  
```xml  
<configuration>  
  <connectionStrings>  
    <clear/>  
    <add name="NorthwindSQL"
     providerName="System.Data.SqlClient"
     connectionString=  
     "Data Source=MSSQL1;Initial Catalog=Northwind;Integrated Security=true"  
    />  
  
    <add name="NorthwindAccess"
     providerName="System.Data.OleDb"
     connectionString=  
     "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=C:\Data\Northwind.mdb;"  
    />  
  </connectionStrings>  
</configuration>  
```  
  
### <a name="retrieving-a-connection-string-by-provider-name"></a>Recuperar una cadena de conexión por el nombre de proveedor  
 Para crear un generador del proveedor, debe proporcionar una cadena de conexión así como el nombre del proveedor. En este ejemplo se muestra cómo recuperar una cadena de conexión de un archivo de configuración de aplicación pasando el nombre del proveedor en el formato invariable "*System.Data.ProviderName*". El código recorre en iteración <xref:System.Configuration.ConnectionStringSettingsCollection>. Devuelve correctamente <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>; en caso contrario, `null` (`Nothing` en Visual Basic). Si existen varias entradas para un proveedor, se devuelve la primera que se encuentra. Para obtener más información y ejemplos de recuperación de cadenas de conexión de archivos de configuración, vea Cadenas de [conexión y archivos](connection-strings-and-configuration-files.md)de configuración .  
  
> [!NOTE]
> Se necesita una referencia a `System.Configuration.dll` para que se ejecute el código.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/VB/source.vb#1)]  
  
## <a name="creating-the-dbproviderfactory-and-dbconnection"></a>Crear DbProviderFactory y DbConnection  
 En este ejemplo se <xref:System.Data.Common.DbProviderFactory> muestra <xref:System.Data.Common.DbConnection> cómo crear un y object pasándole el nombre del proveedor en el formato "*System.Data.ProviderName*" y una cadena de conexión. Se devuelve correctamente un objeto `DbConnection`; `null` (`Nothing` en Visual Basic), en caso de producirse un error.  
  
 El código obtiene `DbProviderFactory` llamando a <xref:System.Data.Common.DbProviderFactories.GetFactory%2A>. Entonces, el método <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A> crea el objeto <xref:System.Data.Common.DbConnection> y la propiedad <xref:System.Data.Common.DbConnection.ConnectionString%2A> se establece en la cadena de conexión.  
  
 [!code-csharp[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/VB/source.vb#1)]  
  
## <a name="see-also"></a>Consulte también

- [Objetos DbProviderFactory](dbproviderfactories.md)
- [Cadenas de conexión](connection-strings.md)
- [Utilizar las clases Configuration](https://docs.microsoft.com/previous-versions/aspnet/ms228063(v=vs.100))
- [Información general de ADO.NET](ado-net-overview.md)
