---
title: Generadores de cadenas de conexión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8434b608-c4d3-43d3-8ae3-6d8c6b726759
ms.openlocfilehash: 1c65b0c2c9ae19aa008ecd8fb453d8e41b7c4167
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43737508"
---
# <a name="connection-string-builders"></a>Generadores de cadenas de conexión
En versiones anteriores de [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], comprobación de las cadenas de conexión con la cadena concatenada valores no se produjeron, por lo que en tiempo de ejecución genera una palabra clave incorrecta en el tiempo de compilación un <xref:System.ArgumentException>. Cada uno de los proveedores de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] admitía una sintaxis diferente para las palabras claves de cadenas de conexión, lo que dificultaba la construcción de cadenas de conexión válidas de forma manual. Para solucionar este problema, [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 2.0 incorporó nuevos compiladores de cadenas de conexión para cada proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Cada uno de los proveedores de datos incluye una clase creadora de cadenas de conexión fuertemente tipadas que hereda de <xref:System.Data.Common.DbConnectionStringBuilder>. En la tabla siguiente se indican los proveedores de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y sus clases compiladoras de cadenas de conexión asociadas.  
  
|Proveedor|Clase ConnectionStringBuilder|  
|--------------|-----------------------------------|  
|<xref:System.Data.SqlClient>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OleDb>|<xref:System.Data.OleDb.OleDbConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.Odbc>|<xref:System.Data.Odbc.OdbcConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OracleClient>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|  
  
## <a name="connection-string-injection-attacks"></a>Ataques de inyección de cadenas de conexión  
 Cuando se utiliza la concatenación dinámica de cadenas para generar cadenas de conexión basadas en datos introducidos por el usuario, se pueden producir ataques de inyección de cadenas de conexión. Si no se valida la cadena y no se crean secuencias de escape para los caracteres o el texto malintencionado, los atacantes pueden tener acceso a datos confidenciales y a otros recursos del servidor. Por ejemplo, un atacante puede realizar un ataque si proporciona un punto y coma y anexa un valor adicional. La cadena de conexión se analiza utilizando un algoritmo del tipo "el último gana", y la entrada hostil se sustituye por un valor legítimo.  
  
 Las clases compiladoras de cadenas de conexión se han diseñado para eliminar la adivinación y desarrollar protección ante errores de sintaxis y vulnerabilidades de seguridad. Proporcionan métodos y propiedades que corresponden a los pares clave-valor conocidos permitidos por cada proveedor de datos. Cada clase mantiene una colección fija de sinónimos y puede convertir un sinónimo al correspondiente nombre de clave conocido. En los pares clave-valor se realizan comprobaciones y los pares no válidos inician una excepción. Además, los valores inyectados se controlan de forma segura.  
  
 En el ejemplo siguiente se muestra cómo <xref:System.Data.SqlClient.SqlConnectionStringBuilder> controla un valor adicional insertado en la configuración `Initial Catalog`.  
  
```vb  
Dim builder As New System.Data.SqlClient.SqlConnectionStringBuilder  
builder("Data Source") = "(local)"  
builder("Integrated Security") = True  
builder("Initial Catalog") = "AdventureWorks;NewValue=Bad"  
Console.WriteLine(builder.ConnectionString)  
```  
  
```csharp  
System.Data.SqlClient.SqlConnectionStringBuilder builder =  
  new System.Data.SqlClient.SqlConnectionStringBuilder();  
builder["Data Source"] = "(local)";  
builder["integrated Security"] = true;  
builder["Initial Catalog"] = "AdventureWorks;NewValue=Bad";  
Console.WriteLine(builder.ConnectionString);  
```  
  
 El resultado muestra que <xref:System.Data.SqlClient.SqlConnectionStringBuilder> controla esta situación correctamente, ya que establece el escape del valor adicional entre comillas dobles en lugar de anexarlo a la cadena de conexión como un nuevo par clave-valor.  
  
```  
data source=(local);Integrated Security=True;  
initial catalog="AdventureWorks;NewValue=Bad"  
```  
  
## <a name="building-connection-strings-from-configuration-files"></a>Crear cadenas de conexión a partir de archivos de configuración  
 Si determinados elementos de una cadena de conexión se conocen de antemano, se pueden almacenar en un archivo de configuración y recuperar en tiempo de ejecución para construir una cadena de conexión completa. Por ejemplo, se puede conocer por adelantado el nombre de la base de datos, pero no el del servidor. También es posible que desee que un usuario indique un nombre y una contraseña en tiempo de ejecución sin que pueda inyectar otros valores en ella.  
  
 Uno de los constructores sobrecargados de un compilador de cadenas de conexión toma <xref:System.String> como argumento, lo que permite proporcionar una cadena de conexión parcial que se puede completar después con los datos introducidos por el usuario. La cadena de conexión parcial se puede almacenar en un archivo de configuración y recuperarse en tiempo de ejecución.  
  
> [!NOTE]
>  El espacio de nombres <xref:System.Configuration> permite el acceso mediante programación a archivos de configuración que usan <xref:System.Web.Configuration.WebConfigurationManager> en aplicaciones web y <xref:System.Configuration.ConfigurationManager> en aplicaciones Windows. Para obtener más información sobre cómo trabajar con cadenas de conexión y archivos de configuración, consulte [las cadenas de conexión y archivos de configuración](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).  
  
### <a name="example"></a>Ejemplo  
 En este ejemplo se muestra la recuperación de una cadena de conexión incluida en un archivo de configuración y cómo se completa mediante el establecimiento de las propiedades <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A> y <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> de <xref:System.Data.SqlClient.SqlConnectionStringBuilder>. El archivo de configuración se define de la siguiente forma.  
  
```xml  
<connectionStrings>  
  <clear/>  
  <add name="partialConnectString"   
    connectionString="Initial Catalog=Northwind;"  
    providerName="System.Data.SqlClient" />  
</connectionStrings>  
```  
  
> [!NOTE]
>  Para ejecutar el código, debe establecer una referencia al archivo `System.Configuration.dll` del proyecto.  
  
 [!code-csharp[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/CS/source.cs#1)]
 [!code-vb[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Cadenas de conexión](../../../../docs/framework/data/adonet/connection-strings.md)  
 [Privacidad y seguridad de datos](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
