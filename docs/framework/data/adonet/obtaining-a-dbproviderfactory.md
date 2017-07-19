---
title: "Obtener DbProviderFactory | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a16e4a4d-6a5b-45db-8635-19570e4572ae
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Obtener DbProviderFactory
El proceso de obtención de <xref:System.Data.Common.DbProviderFactory> implica pasar información sobre un proveedor de datos a la clase <xref:System.Data.Common.DbProviderFactories>.  En función de esta información, el método <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> crea un generador del proveedor fuertemente tipado.  Por ejemplo, para crear <xref:System.Data.SqlClient.SqlClientFactory>, se puede pasar a `GetFactory` una cadena con el nombre de proveedor especificado como "System.Data.SqlClient".  La otra sobrecarga de `GetFactory` toma <xref:System.Data.DataRow>.  Una vez creado el generador del proveedor, se pueden utilizar sus métodos para crear objetos adicionales.  Entre los métodos de `SqlClientFactory` se incluyen <xref:System.Data.SqlClient.SqlClientFactory.CreateConnection%2A>, <xref:System.Data.SqlClient.SqlClientFactory.CreateCommand%2A> y <xref:System.Data.SqlClient.SqlClientFactory.CreateDataAdapter%2A>.  
  
> [!NOTE]
>  Las clases <xref:System.Data.OracleClient.OracleClientFactory>, <xref:System.Data.Odbc.OdbcFactory> y <xref:System.Data.OleDb.OleDbFactory> de .NET Framework también proporcionan una funcionalidad similar.  
  
## Registrar DbProviderFactories  
 Todos los proveedores de datos .NET Framework que admiten una clase basada en generador registran información de configuración en la sección **DbProviderFactories** del archivo **machine.config** del equipo local.  El siguiente fragmento del archivo de configuración muestra la sintaxis y formato de <xref:System.Data.SqlClient>.  
  
```  
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
  
 El atributo **invariant** identifica el proveedor de datos subyacente.  Esta sintaxis de nomenclatura en tres partes también se utiliza al crear un nuevo generador y para identificar al proveedor en un archivo de configuración de la aplicación, de manera que el nombre de proveedor, junto con sus cadenas de conexión asociadas, se puedan recuperar en tiempo de conexión.  
  
## Recuperar información del proveedor  
 Se puede recuperar información acerca de todos los proveedores de datos instalados en el equipo local utilizando el método <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A>.  Devuelve un <xref:System.Data.DataTable> denominado **DbProviderFactories** que contiene las columnas descritas en la tabla siguiente.  
  
|Índice de columna|Nombre de columna|Resultado de ejemplo|Descripción|  
|-----------------------|-----------------------|--------------------------|-----------------|  
|0|**Name**|Proveedor de datos SqlClient|Nombre legible del proveedor de datos|  
|1|**Descripción**|Proveedor de datos .NET Framework para SqlServer|Descripción legible del proveedor de datos|  
|2|**InvariantName**|`System.Data.SqlClient`|Nombre que se puede utilizar mediante programación para hacer referencia al proveedor de datos|  
|3|**AssemblyQualifiedName**|System.Data.SqlClient.SqlClientFactory, System.Data, Version\=2.0.0.0, Culture\=neutral, PublicKeyToken\=b77a5c561934e089|Nombre completo de la clase de generador, el cual tiene información suficiente para crear la instancia del objeto|  
  
 Este `DataTable` se puede utilizar para permitir a un usuario seleccionar un <xref:System.Data.DataRow> en tiempo de ejecución.  El `DataRow` seleccionado se puede pasar al método <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> para crear un <xref:System.Data.Common.DbProviderFactory> fuertemente tipado.  Un <xref:System.Data.DataRow> seleccionado se puede pasar al método `GetFactory` para crear el objeto `DbProviderFactory` deseado.  
  
## Enumerar las clases de generador del proveedor instaladas  
 Este ejemplo muestra cómo el método <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A> devuelve un <xref:System.Data.DataTable> con información sobre los proveedores instalados.  El código recorre en iteración cada fila de `DataTable` y muestra información de todos los proveedores instalados en la ventana de la consola.  
  
 [!code-csharp[DataWorks DbProviderFactories#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/VB/source.vb#1)]  
  
## Utilizar archivos de configuración de la aplicación para almacenar información del generador  
 El patrón de diseño utilizado para trabajar con generadores implica almacenar información de cadena de conexión y proveedor en un archivo de configuración de la aplicación, como **app.config** para una aplicación Windows y **web.config** para una aplicación ASP.NET.  
  
 El siguiente fragmento de archivo de configuración muestra cómo guardar dos cadenas de conexión, una denominada "NorthwindSQL", para la conexión a la base de datos Northwind de SQL Server, y la otra denominada "NorthwindAccess", para una conexión a la base de datos Northwind de Access\/Jet.  El nombre **invariant** se utiliza para el atributo **providerName**.  
  
```  
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
  
### Recuperar una cadena de conexión por el nombre de proveedor  
 Para crear un generador del proveedor, debe proporcionar una cadena de conexión así como el nombre del proveedor.  Este ejemplo muestra cómo recuperar una cadena de conexión desde un archivo de configuración de la aplicación pasando el nombre del proveedor en el formato invariable "*System.Data.ProviderName*".  El código recorre en iteración <xref:System.Configuration.ConnectionStringSettingsCollection>.  Devuelve correctamente <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>; en caso contrario, `null` \(`Nothing` en Visual Basic\).  Si existen varias entradas para un proveedor, se devuelve la primera que se encuentra.  Para obtener más información y ejemplos sobre recuperación de cadenas de conexión desde archivos de configuración, vea [Cadenas de conexión y archivos de configuración](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)..  
  
> [!NOTE]
>  Se necesita una referencia a `System.Configuration.dll` para que se ejecute el código.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/VB/source.vb#1)]  
  
## Crear DbProviderFactory y DbConnection  
 Este ejemplo muestra cómo crear un objeto <xref:System.Data.Common.DbProviderFactory> y <xref:System.Data.Common.DbConnection> pasando el nombre del proveedor en el formato "*System.Data.ProviderName*" y una cadena de conexión.  Se devuelve correctamente un objeto `DbConnection`; `null` \(`Nothing` en Visual Basic\), en caso de producirse un error.  
  
 El código obtiene `DbProviderFactory` llamando a <xref:System.Data.Common.DbProviderFactories.GetFactory%2A>.  Entonces, el método <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A> crea el objeto <xref:System.Data.Common.DbConnection> y la propiedad <xref:System.Data.Common.DbConnection.ConnectionString%2A> se establece en la cadena de conexión.  
  
 [!code-csharp[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/VB/source.vb#1)]  
  
## Vea también  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)   
 [Cadenas de conexión](../../../../docs/framework/data/adonet/connection-strings.md)   
 [Using the Configuration Classes](../Topic/Using%20the%20Configuration%20Classes.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)