---
title: "Cadenas de conexión y archivos de configuración"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 37df2641-661e-407a-a3fb-7bf9540f01e8
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 447b2d6c0e5eeafeaff89aa1d6430eec72d59a4d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="connection-strings-and-configuration-files"></a>Cadenas de conexión y archivos de configuración
La incrustación de cadenas de conexión en el código de la aplicación puede producir vulnerabilidades en la seguridad y problemas de mantenimiento. Las cadenas de conexión sin cifrar compiladas en el código de origen de una aplicación pueden verse mediante la [Ildasm.exe (Desensamblador de IL)](../../../../docs/framework/tools/ildasm-exe-il-disassembler.md) herramienta. Además, si la cadena de conexión cambia en algún momento, será necesario compilar de nuevo la aplicación. Por estas razones, se recomienda almacenar las cadenas de conexión en un archivo de configuración de la aplicación.  
  
## <a name="working-with-application-configuration-files"></a>Trabajar con archivos de configuración de la aplicación  
 Los archivos de configuración de la aplicación contienen valores específicos de una aplicación determinada. Por ejemplo, una aplicación ASP.NET puede tener uno o más **web.config** archivos y una aplicación de Windows pueden tener un elemento opcional **app.config** archivo. Los archivos de configuración comparten elementos comunes, aunque su nombre y ubicación varían en función del host de la aplicación.  
  
### <a name="the-connectionstrings-section"></a>Sección connectionStrings  
 Las cadenas de conexión se pueden almacenar como pares de clave/valor en el **connectionStrings** sección de la **configuración** elemento de un archivo de configuración de aplicación. Los elementos secundarios incluyen **agregar**, **borrar**, y **quitar**.  
  
 El siguiente fragmento del archivo de configuración muestra el esquema y la sintaxis para almacenar una cadena de conexión. El **nombre** atributo es un nombre que se proporciona para identificar de forma única una cadena de conexión para que se puede recuperar en tiempo de ejecución. El **providerName** es el nombre invariable del proveedor de datos de .NET Framework, que está registrado en el archivo machine.config.  
  
```xml  
<?xml version='1.0' encoding='utf-8'?>  
  <configuration>  
    <connectionStrings>  
      <clear />  
      <add name="Name"   
       providerName="System.Data.ProviderName"   
       connectionString="Valid Connection String;" />  
    </connectionStrings>  
  </configuration>  
```  
  
> [!NOTE]
>  Puede guardar parte de la cadena de conexión en un archivo de configuración y usar la clase <xref:System.Data.Common.DbConnectionStringBuilder> para completarla en tiempo de ejecución. Esto resulta útil en escenarios en los que no se conocen los elementos de la cadena de conexión por anticipado o cuando no desea guardar información confidencial en un archivo de configuración. Para obtener más información, consulte [generadores de cadenas de conexión](../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
### <a name="using-external-configuration-files"></a>Uso de archivos de configuración externos  
 Los archivos de configuración externos son archivos independientes que contienen un fragmento de un archivo de configuración compuesto de una sola sección. El archivo de configuración principal hace referencia al archivo de configuración externo. Almacenar el **connectionStrings** sección en un archivo físicamente independiente resulta útil en situaciones donde se pueden editar las cadenas de conexión una vez implementada la aplicación. Por ejemplo, si se modifican los archivos de configuración, ASP.NET reinicia de forma predeterminada el dominio de la aplicación, lo que provoca la pérdida de la información de estado. Sin embargo, la modificación de un archivo de configuración externo no provoca el reinicio de la aplicación. Los archivos de configuración externos no se limitan a ASP.NET; también se pueden utilizar en aplicaciones Windows. Además, la seguridad y permisos de acceso a los archivos se pueden usar para restringir el acceso a los archivos de configuración externos. El trabajo con archivos de configuración externos en tiempo de ejecución es transparente y no requiere código especial.  
  
 Para almacenar cadenas de conexión en un archivo de configuración externo, cree un archivo independiente que contiene únicamente el **connectionStrings** sección. No incluya elementos, secciones ni atributos adicionales. En este ejemplo se muestra la sintaxis de un archivo de configuración externo.  
  
```xml  
<connectionStrings>  
  <add name="Name"   
   providerName="System.Data.ProviderName"   
   connectionString="Valid Connection String;" />  
</connectionStrings>  
```  
  
 En el archivo de configuración de la aplicación principal, use la **configSource** atributo para especificar el nombre completo y la ubicación del archivo externo. En este ejemplo se hace referencia a un archivo de configuración externo denominado `connections.config`.  
  
```xml  
<?xml version='1.0' encoding='utf-8'?>  
<configuration>  
    <connectionStrings configSource="connections.config"/>  
</configuration>  
```  
  
## <a name="retrieving-connection-strings-at-run-time"></a>Recuperar cadenas de conexión en tiempo de ejecución  
 .NET Framework 2.0 incorpora nuevas clases en el espacio de nombres <xref:System.Configuration> para simplificar la recuperación de las cadenas de conexión de los archivos de configuración en tiempo de ejecución. La cadena de conexión se puede recuperar mediante programación con el nombre de la cadena o el nombre de proveedor.  
  
> [!NOTE]
>  El **machine.config** archivo también contiene un **connectionStrings** sección, que contiene las cadenas de conexión utilizadas por Visual Studio. Al recuperar cadenas de conexión mediante el nombre del proveedor de la **app.config** archivo en una aplicación de Windows, las cadenas de conexión **machine.config** obtener cargar primero y, a continuación, las entradas de **app.config**. Agregar **borrar** inmediatamente después de la **connectionStrings** elemento quita todas las referencias heredadas de la estructura de datos en la memoria, por lo que solo las cadenas de conexión definen en la variable local **app.config** se consideran archivos.  
  
### <a name="working-with-the-configuration-classes"></a>Trabajar con clases de configuración  
 A partir de .NET Framework 2.0, se usa el elemento <xref:System.Configuration.ConfigurationManager> al trabajar con archivos de configuración en el equipo local, reemplazando al elemento desusado <xref:System.Configuration.ConfigurationSettings>. <xref:System.Web.Configuration.WebConfigurationManager> se usa para trabajar con archivos de configuración de ASP.NET. Está diseñado para trabajar con archivos de configuración en un servidor Web y permite el acceso mediante programación a secciones del archivo de configuración como **system.web**.  
  
> [!NOTE]
>  El acceso a los archivos de configuración en tiempo de ejecución requiere la concesión de permisos al llamador; los permisos necesarios dependen del tipo de aplicación, del archivo de configuración y de la ubicación. Para obtener más información, consulte [usando las clases de configuración](http://msdn.microsoft.com/library/98d2b386-baf6-4a17-974b-76e3b4c87acc) y <xref:System.Web.Configuration.WebConfigurationManager> para las aplicaciones ASP.NET, y <xref:System.Configuration.ConfigurationManager> para aplicaciones de Windows.  
  
 Puede usar <xref:System.Configuration.ConnectionStringSettingsCollection> para recuperar cadenas de conexión de archivos de configuración de aplicación. Contiene una colección de <xref:System.Configuration.ConnectionStringSettings> objetos, cada uno de los cuales representa una única entrada en la **connectionStrings** sección. Sus propiedades se asignan a los atributos de cadenas de conexión, lo que permite recuperar una cadena de conexión mediante la especificación de su nombre o del nombre del proveedor.  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|<xref:System.Configuration.ConnectionStringSettings.Name%2A>|Nombre de la cadena de conexión. Se asigna a la **nombre** atributo.|  
|<xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>|Nombre completo del proveedor. Se asigna a la **providerName** atributo.|  
|<xref:System.Configuration.ConnectionStringSettings.ConnectionString%2A>|La cadena de conexión. Se asigna a la **connectionString** atributo.|  
  
### <a name="example-listing-all-connection-strings"></a>Ejemplo: mostrar todas las cadenas de conexión  
 Este ejemplo recorre en iteración la colección `ConnectionStringSettings` y muestra las propiedades <xref:System.Configuration.ConnectionStringSettings.Name%2A>, <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A> y <xref:System.Configuration.ConnectionStringSettings.ConnectionString%2A> en la ventana de la consola.  
  
> [!NOTE]
>  System.Configuration.dll no se incluye en todos los tipos de proyectos y es posible que deba establecer una referencia a este elemento para usar las clases de configuración. El nombre y la ubicación de un archivo de configuración de aplicación determinado varían en función del tipo de aplicación y del proceso de hospedaje.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfig#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfig/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfig#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfig/VB/source.vb#1)]  
  
### <a name="example-retrieving-a-connection-string-by-name"></a>Ejemplo: recuperar una cadena de conexión por su nombre  
 El siguiente ejemplo muestra cómo recuperar una cadena de conexión de un archivo de configuración mediante la especificación del nombre. El código crea un objeto <xref:System.Configuration.ConnectionStringSettings>, de forma que el parámetro de entrada proporcionado coincida con el nombre de <xref:System.Configuration.ConfigurationManager.ConnectionStrings%2A>. Si no se encuentra una coincidencia de nombre, la función devuelve `null` (`Nothing` en Visual Basic).  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByName#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByName/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByName#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByName/VB/source.vb#1)]  
  
### <a name="example-retrieving-a-connection-string-by-provider-name"></a>Ejemplo: recuperar una cadena de conexión por el nombre de proveedor  
 En este ejemplo se muestra cómo recuperar una cadena de conexión especificando el nombre invariable de proveedor en el formato *System.Data.ProviderName*. El código recorre en iteración <xref:System.Configuration.ConnectionStringSettingsCollection> y devuelve la cadena de conexión del primer valor de <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A> encontrado. Si no se encuentra el nombre del proveedor, la función devuelve `null` (`Nothing` en Visual Basic).  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/VB/source.vb#1)]  
  
## <a name="encrypting-configuration-file-sections-using-protected-configuration"></a>Cifrar secciones del archivo de configuración mediante una configuración protegida  
 ASP.NET 2.0 incorpora una nueva característica denominada *configuración protegida*, que permite cifrar información confidencial en un archivo de configuración. Si bien se ha diseñado principalmente para ASP.NET, la configuración protegida también se puede usar para cifrar secciones del archivo de configuración en aplicaciones Windows. Para obtener una descripción detallada de las capacidades de configuración protegida, vea [Encrypting Configuration Information Using Protected Configuration](http://msdn.microsoft.com/library/51cdfe5b-9d82-458c-94ff-c551c4f38ed1).  
  
 Fragmento de archivo de configuración siguiente muestra la **connectionStrings** sección después de que se ha cifrado. El **configProtectionProvider** especifica el proveedor de configuración protegida que se utiliza para cifrar y descifrar las cadenas de conexión. El **EncryptedData** sección contiene el texto cifrado.  
  
```xml  
<connectionStrings configProtectionProvider="DataProtectionConfigurationProvider">  
  <EncryptedData>  
    <CipherData>  
      <CipherValue>AQAAANCMnd8BFdERjHoAwE/Cl+sBAAAAH2... </CipherValue>  
    </CipherData>  
  </EncryptedData>  
</connectionStrings>  
```  
  
 Cuando se recupera la cadena de conexión cifrada en tiempo de ejecución, .NET Framework usa el proveedor especificado para descifrar el **CipherValue** y ponerla a disposición de la aplicación. No es necesario escribir ningún código adicional para administrar el proceso de descifrado.  
  
### <a name="protected-configuration-providers"></a>Proveedores de configuración protegida  
 Los proveedores de configuración protegida se registran en el **configProtectedData** sección de la **machine.config** de archivos en el equipo local, como se muestra en el siguiente fragmento, que se muestra en los dos proveedores de configuración protegida que se suministra con .NET Framework. Los valores que se muestran se han truncado para facilitar la lectura.  
  
```xml  
<configProtectedData defaultProvider="RsaProtectedConfigurationProvider">  
  <providers>  
    <add name="RsaProtectedConfigurationProvider"   
      type="System.Configuration.RsaProtectedConfigurationProvider, ... />  
    <add name="DataProtectionConfigurationProvider"   
      type="System.Configuration.DpapiProtectedConfigurationProvider, ... />  
  </providers>  
</configProtectedData>  
```  
  
 Puede configurar proveedores de configuración protegida adicionales agregándolos a la **machine.config** archivo. Asimismo, puede crear su propio proveedor de configuración protegida heredando de la clase base abstracta <xref:System.Configuration.ProtectedConfigurationProvider>. En la tabla siguiente se describen los dos archivos de configuración incluidos en .NET Framework.  
  
|Proveedor|Descripción|  
|--------------|-----------------|  
|<!--zz<xref:System.Configuration.RSAProtectedConfigurationProvider>-->`System.Configuration.RSAProtectedConfigurationProvider`|Usa el algoritmo de cifrado RSA para cifrar y descifrar datos. Los algoritmos RSA se pueden usar para el cifrado de clave pública y para firmas digitales. También se conoce como cifrado de "clave pública" o asimétrico, ya que usa dos claves diferentes. Puede usar el [herramienta de registro de IIS de ASP.NET (Aspnet_regiis.exe)](http://msdn.microsoft.com/library/6491c41e-e2b0-481f-9863-db3614d5f96b) para cifrar secciones de un archivo Web.config y administrar las claves de cifrado. ASP.NET descifra el archivo de configuración cuando lo procesa. La identidad de la aplicación ASP.NET debe tener acceso de lectura a la clave de cifrado utilizada para cifrar y descifrar las secciones cifradas.|  
|<!--zz<xref:System.Configuration.DPAPIProtectedConfigurationProvider>-->`System.Configuration.DPAPIProtectedConfigurationProvider`|Usa la API de protección de datos (DPAPI) de Windows para cifrar y descifrar las secciones de configuración. Usa los servicios criptográficos integrados de Windows y se puede configurar para la protección específica de equipo o para la protección específica de cuenta de usuario. La protección específica de equipo resulta útil cuando varias aplicaciones del mismo servidor deben compartir información. La protección específica de cuenta de usuario se puede utilizar para los servicios que se ejecutan con una identidad de usuario concreta, como un entorno de hospedaje compartido. Cada aplicación se ejecuta con una identidad independiente que limita el acceso a recursos como los archivos y las bases de datos.|  
  
 Ambos proveedores proporcionan cifrado de datos de alta seguridad. No obstante, si prevé usar el mismo archivo de configuración de cifrado en varios servidores como, por ejemplo, una granja de servidores web, solo `RsaProtectedConfigurationProvider` permite exportar las claves de cifrado usadas para cifrar los datos e importarlas a otro servidor. Para obtener más información, consulte [importar y exportar protegido configuración contenedores de claves RSA](http://msdn.microsoft.com/library/f3022b39-f17f-48c1-b067-025eab0ce8bc).  
  
### <a name="using-the-configuration-classes"></a>Uso de clases de configuración  
 El espacio de nombres <xref:System.Configuration> proporciona clases para trabajar con valores de configuración mediante programación. La clase <xref:System.Configuration.ConfigurationManager> proporciona acceso a los archivos de configuración de equipo, aplicación y usuario. Si va a crear una aplicación de ASP.NET, puede usar el <xref:System.Web.Configuration.WebConfigurationManager> (clase), que proporciona la misma funcionalidad, mientras que permite obtener acceso a configuración que son únicos para las aplicaciones de ASP.NET, como los que se encuentra en  **\< System.Web >**.  
  
> [!NOTE]
>  El espacio de nombres <xref:System.Security.Cryptography> contiene clases que proporcionan opciones adicionales para cifrar y descifrar datos. Use estas clases si requiere servicios criptográficos que no están disponibles cuando se usa la configuración protegida. Algunas de estas clases son contenedores de Microsoft CryptoAPI no administrado, mientras que otras son simplemente implementaciones administradas. Para más información, vea [Servicios criptográficos](http://msdn.microsoft.com/library/68a1e844-c63c-44af-9247-f6716eb23781).  
  
### <a name="appconfig-example"></a>Ejemplo de App.config  
 En este ejemplo se muestra cómo alternar el cifrado el **connectionStrings** sección un **app.config** archivo para una aplicación de Windows. En este ejemplo, el procedimiento recibe el nombre de la aplicación como argumento, por ejemplo, "MyApplication.exe". El **app.config** archivo, a continuación, se cifra y se copia a la carpeta que contiene el ejecutable con el nombre "MyApplication.exe.config".  
  
> [!NOTE]
>  La cadena de conexión solo se puede descifrar en el equipo donde se ha cifrado.  
  
 El código usa el <xref:System.Configuration.ConfigurationManager.OpenExeConfiguration%2A> método para abrir el **app.config** archivo para edición y el <xref:System.Configuration.ConfigurationManager.GetSection%2A> método devuelve el **connectionStrings** sección. A continuación, el código comprueba la propiedad <xref:System.Configuration.SectionInformation.IsProtected%2A> y llama a <xref:System.Configuration.SectionInformation.ProtectSection%2A> para cifrar la sección si no está cifrada. Para descifrar la sección se llama al método <xref:System.Configuration.SectionInformation.UnprotectSection%2A>. El método <xref:System.Configuration.Configuration.Save%2A> completa la operación y guarda los cambios.  
  
> [!NOTE]
>  Para ejecutar el código, debe establecer una referencia al archivo `System.Configuration.dll` del proyecto.  
  
 [!code-csharp[DataWorks ConnectionStrings.Encrypt#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStrings.Encrypt/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStrings.Encrypt#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStrings.Encrypt/VB/source.vb#1)]  
  
### <a name="webconfig-example"></a>Ejemplo de Web.config  
 Este ejemplo usa el método <xref:System.Web.Configuration.WebConfigurationManager.OpenWebConfiguration%2A> de `WebConfigurationManager`. Tenga en cuenta que en este caso puede indicar la ruta de acceso relativa a la **Web.config** archivo mediante una tilde. El código requiere una referencia a la clase `System.Web.Configuration`.  
  
 [!code-csharp[DataWorks ConnectionStringsWeb.Encrypt#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringsWeb.Encrypt/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringsWeb.Encrypt#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringsWeb.Encrypt/VB/source.vb#1)]  
  
 Para obtener más información, proteger las aplicaciones ASP.NET, vea [NIB: seguridad de ASP.NET](http://msdn.microsoft.com/library/04b37532-18d9-40b4-8e5f-ee09a70b311d) y [prácticas de seguridad de ASP.NET 2.0 de un vistazo](http://go.microsoft.com/fwlink/?LinkId=59997) en el centro de desarrollo de ASP.NET.  
  
## <a name="see-also"></a>Vea también  
 [Generadores de cadenas de conexión](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 [Utilizar las clases de configuración](http://msdn.microsoft.com/library/98d2b386-baf6-4a17-974b-76e3b4c87acc)  
 [Configurar aplicaciones](../../../../docs/framework/configure-apps/index.md)  
 [Administración de sitios Web ASP.NET](http://msdn.microsoft.com/library/1298034b-5f7d-464d-abd1-ad9e6b3eeb7e)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
