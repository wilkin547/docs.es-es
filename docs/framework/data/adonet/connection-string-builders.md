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
# <a name="connection-string-builders"></a><span data-ttu-id="501fe-102">Generadores de cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="501fe-102">Connection String Builders</span></span>
<span data-ttu-id="501fe-103">En versiones anteriores de [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], comprobación de las cadenas de conexión con la cadena concatenada valores no se produjeron, por lo que en tiempo de ejecución genera una palabra clave incorrecta en el tiempo de compilación un <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="501fe-103">In earlier versions of [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], compile-time checking of connection strings with concatenated string values did not occur, so that at run time, an incorrect keyword generated an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="501fe-104">Cada uno de los proveedores de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] admitía una sintaxis diferente para las palabras claves de cadenas de conexión, lo que dificultaba la construcción de cadenas de conexión válidas de forma manual.</span><span class="sxs-lookup"><span data-stu-id="501fe-104">Each of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers supported different syntax for connection string keywords, which made constructing valid connection strings difficult if done manually.</span></span> <span data-ttu-id="501fe-105">Para solucionar este problema, [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 2.0 incorporó nuevos compiladores de cadenas de conexión para cada proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="501fe-105">To address this problem, [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 2.0 introduced new connection string builders for each [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider.</span></span> <span data-ttu-id="501fe-106">Cada uno de los proveedores de datos incluye una clase creadora de cadenas de conexión fuertemente tipadas que hereda de <xref:System.Data.Common.DbConnectionStringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="501fe-106">Each data provider includes a strongly typed connection string builder class that inherits from <xref:System.Data.Common.DbConnectionStringBuilder>.</span></span> <span data-ttu-id="501fe-107">En la tabla siguiente se indican los proveedores de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y sus clases compiladoras de cadenas de conexión asociadas.</span><span class="sxs-lookup"><span data-stu-id="501fe-107">The following table lists the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers and their associated connection string builder classes.</span></span>  
  
|<span data-ttu-id="501fe-108">Proveedor</span><span class="sxs-lookup"><span data-stu-id="501fe-108">Provider</span></span>|<span data-ttu-id="501fe-109">Clase ConnectionStringBuilder</span><span class="sxs-lookup"><span data-stu-id="501fe-109">ConnectionStringBuilder class</span></span>|  
|--------------|-----------------------------------|  
|<xref:System.Data.SqlClient>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OleDb>|<xref:System.Data.OleDb.OleDbConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.Odbc>|<xref:System.Data.Odbc.OdbcConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OracleClient>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|  
  
## <a name="connection-string-injection-attacks"></a><span data-ttu-id="501fe-110">Ataques de inyección de cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="501fe-110">Connection String Injection Attacks</span></span>  
 <span data-ttu-id="501fe-111">Cuando se utiliza la concatenación dinámica de cadenas para generar cadenas de conexión basadas en datos introducidos por el usuario, se pueden producir ataques de inyección de cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="501fe-111">A connection string injection attack can occur when dynamic string concatenation is used to build connection strings that are based on user input.</span></span> <span data-ttu-id="501fe-112">Si no se valida la cadena y no se crean secuencias de escape para los caracteres o el texto malintencionado, los atacantes pueden tener acceso a datos confidenciales y a otros recursos del servidor.</span><span class="sxs-lookup"><span data-stu-id="501fe-112">If the string is not validated and malicious text or characters not escaped, an attacker can potentially access sensitive data or other resources on the server.</span></span> <span data-ttu-id="501fe-113">Por ejemplo, un atacante puede realizar un ataque si proporciona un punto y coma y anexa un valor adicional.</span><span class="sxs-lookup"><span data-stu-id="501fe-113">For example, an attacker could mount an attack by supplying a semicolon and appending an additional value.</span></span> <span data-ttu-id="501fe-114">La cadena de conexión se analiza utilizando un algoritmo del tipo "el último gana", y la entrada hostil se sustituye por un valor legítimo.</span><span class="sxs-lookup"><span data-stu-id="501fe-114">The connection string is parsed by using a "last one wins" algorithm, and the hostile input is substituted for a legitimate value.</span></span>  
  
 <span data-ttu-id="501fe-115">Las clases compiladoras de cadenas de conexión se han diseñado para eliminar la adivinación y desarrollar protección ante errores de sintaxis y vulnerabilidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="501fe-115">The connection string builder classes are designed to eliminate guesswork and protect against syntax errors and security vulnerabilities.</span></span> <span data-ttu-id="501fe-116">Proporcionan métodos y propiedades que corresponden a los pares clave-valor conocidos permitidos por cada proveedor de datos.</span><span class="sxs-lookup"><span data-stu-id="501fe-116">They provide methods and properties corresponding to the known key/value pairs permitted by each data provider.</span></span> <span data-ttu-id="501fe-117">Cada clase mantiene una colección fija de sinónimos y puede convertir un sinónimo al correspondiente nombre de clave conocido.</span><span class="sxs-lookup"><span data-stu-id="501fe-117">Each class maintains a fixed collection of synonyms and can translate from a synonym to the corresponding well-known key name.</span></span> <span data-ttu-id="501fe-118">En los pares clave-valor se realizan comprobaciones y los pares no válidos inician una excepción.</span><span class="sxs-lookup"><span data-stu-id="501fe-118">Checks are performed for valid key/value pairs and an invalid pair throws an exception.</span></span> <span data-ttu-id="501fe-119">Además, los valores inyectados se controlan de forma segura.</span><span class="sxs-lookup"><span data-stu-id="501fe-119">In addition, injected values are handled in a safe manner.</span></span>  
  
 <span data-ttu-id="501fe-120">En el ejemplo siguiente se muestra cómo <xref:System.Data.SqlClient.SqlConnectionStringBuilder> controla un valor adicional insertado en la configuración `Initial Catalog`.</span><span class="sxs-lookup"><span data-stu-id="501fe-120">The following example demonstrates how the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handles an inserted extra value for the `Initial Catalog` setting.</span></span>  
  
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
  
 <span data-ttu-id="501fe-121">El resultado muestra que <xref:System.Data.SqlClient.SqlConnectionStringBuilder> controla esta situación correctamente, ya que establece el escape del valor adicional entre comillas dobles en lugar de anexarlo a la cadena de conexión como un nuevo par clave-valor.</span><span class="sxs-lookup"><span data-stu-id="501fe-121">The output shows that the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handled this correctly by escaping the extra value in double quotation marks instead of appending it to the connection string as a new key/value pair.</span></span>  
  
```  
data source=(local);Integrated Security=True;  
initial catalog="AdventureWorks;NewValue=Bad"  
```  
  
## <a name="building-connection-strings-from-configuration-files"></a><span data-ttu-id="501fe-122">Crear cadenas de conexión a partir de archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="501fe-122">Building Connection Strings from Configuration Files</span></span>  
 <span data-ttu-id="501fe-123">Si determinados elementos de una cadena de conexión se conocen de antemano, se pueden almacenar en un archivo de configuración y recuperar en tiempo de ejecución para construir una cadena de conexión completa.</span><span class="sxs-lookup"><span data-stu-id="501fe-123">If certain elements of a connection string are known beforehand, they can be stored in a configuration file and retrieved at run time to construct a complete connection string.</span></span> <span data-ttu-id="501fe-124">Por ejemplo, se puede conocer por adelantado el nombre de la base de datos, pero no el del servidor.</span><span class="sxs-lookup"><span data-stu-id="501fe-124">For example, the name of the database might be known in advance, but not the name of the server.</span></span> <span data-ttu-id="501fe-125">También es posible que desee que un usuario indique un nombre y una contraseña en tiempo de ejecución sin que pueda inyectar otros valores en ella.</span><span class="sxs-lookup"><span data-stu-id="501fe-125">Or you might want a user to supply a name and password at run time without being able to inject other values into the connection string.</span></span>  
  
 <span data-ttu-id="501fe-126">Uno de los constructores sobrecargados de un compilador de cadenas de conexión toma <xref:System.String> como argumento, lo que permite proporcionar una cadena de conexión parcial que se puede completar después con los datos introducidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="501fe-126">One of the overloaded constructors for a connection string builder takes a <xref:System.String> as an argument, which enables you to supply a partial connection string that can then be completed from user input.</span></span> <span data-ttu-id="501fe-127">La cadena de conexión parcial se puede almacenar en un archivo de configuración y recuperarse en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="501fe-127">The partial connection string can be stored in a configuration file and retrieved at run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="501fe-128">El espacio de nombres <xref:System.Configuration> permite el acceso mediante programación a archivos de configuración que usan <xref:System.Web.Configuration.WebConfigurationManager> en aplicaciones web y <xref:System.Configuration.ConfigurationManager> en aplicaciones Windows.</span><span class="sxs-lookup"><span data-stu-id="501fe-128">The <xref:System.Configuration> namespace allows programmatic access to configuration files that use the <xref:System.Web.Configuration.WebConfigurationManager> for Web applications and the <xref:System.Configuration.ConfigurationManager> for Windows applications.</span></span> <span data-ttu-id="501fe-129">Para obtener más información sobre cómo trabajar con cadenas de conexión y archivos de configuración, consulte [las cadenas de conexión y archivos de configuración](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="501fe-129">For more information about working with connection strings and configuration files, see [Connection Strings and Configuration Files](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="501fe-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="501fe-130">Example</span></span>  
 <span data-ttu-id="501fe-131">En este ejemplo se muestra la recuperación de una cadena de conexión incluida en un archivo de configuración y cómo se completa mediante el establecimiento de las propiedades <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A> y <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> de <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="501fe-131">This example demonstrates retrieving a partial connection string from a configuration file and completing it by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A>, and <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> properties of the <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span> <span data-ttu-id="501fe-132">El archivo de configuración se define de la siguiente forma.</span><span class="sxs-lookup"><span data-stu-id="501fe-132">The configuration file is defined as follows.</span></span>  
  
```xml  
<connectionStrings>  
  <clear/>  
  <add name="partialConnectString"   
    connectionString="Initial Catalog=Northwind;"  
    providerName="System.Data.SqlClient" />  
</connectionStrings>  
```  
  
> [!NOTE]
>  <span data-ttu-id="501fe-133">Para ejecutar el código, debe establecer una referencia al archivo `System.Configuration.dll` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="501fe-133">You must set a reference to the `System.Configuration.dll` in your project for the code to run.</span></span>  
  
 [!code-csharp[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/CS/source.cs#1)]
 [!code-vb[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="501fe-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="501fe-134">See Also</span></span>  
 [<span data-ttu-id="501fe-135">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="501fe-135">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="501fe-136">Privacidad y seguridad de datos</span><span class="sxs-lookup"><span data-stu-id="501fe-136">Privacy and Data Security</span></span>](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 [<span data-ttu-id="501fe-137">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="501fe-137">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
