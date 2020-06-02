---
title: Generadores de cadenas de conexión
description: Obtenga información sobre las clases de generador de cadenas de conexión usadas para diferentes proveedores en ADO.NET, todas las cuales heredan de DbConnectionStringBuilder.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8434b608-c4d3-43d3-8ae3-6d8c6b726759
ms.openlocfilehash: e493140b4cf5a939e8ae8f42b617fb739ed09dec
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287069"
---
# <a name="connection-string-builders"></a><span data-ttu-id="6187c-103">Generadores de cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="6187c-103">Connection String Builders</span></span>
<span data-ttu-id="6187c-104">En versiones anteriores de ADO.NET, no se realizaban comprobaciones en tiempo de compilación de las cadenas de conexión con valores de cadena concatenados, de modo que, en tiempo de ejecución, una palabra clave incorrecta generara una <xref:System.ArgumentException> .</span><span class="sxs-lookup"><span data-stu-id="6187c-104">In earlier versions of ADO.NET, compile-time checking of connection strings with concatenated string values did not occur, so that at run time, an incorrect keyword generated an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="6187c-105">Cada uno de los proveedores de datos de .NET Framework admite una sintaxis diferente para las palabras clave de cadena de conexión, lo que hacía difícil construir cadenas de conexión válidas si se realiza manualmente.</span><span class="sxs-lookup"><span data-stu-id="6187c-105">Each of the .NET Framework data providers supported different syntax for connection string keywords, which made constructing valid connection strings difficult if done manually.</span></span> <span data-ttu-id="6187c-106">Para solucionar este problema, ADO.NET 2,0 presentó nuevos generadores de cadenas de conexión para cada proveedor de datos .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6187c-106">To address this problem, ADO.NET 2.0 introduced new connection string builders for each .NET Framework data provider.</span></span> <span data-ttu-id="6187c-107">Cada uno de los proveedores de datos incluye una clase creadora de cadenas de conexión fuertemente tipadas que hereda de <xref:System.Data.Common.DbConnectionStringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="6187c-107">Each data provider includes a strongly typed connection string builder class that inherits from <xref:System.Data.Common.DbConnectionStringBuilder>.</span></span> <span data-ttu-id="6187c-108">En la tabla siguiente se enumeran los proveedores de datos de .NET Framework y sus clases de generador de cadenas de conexión asociadas.</span><span class="sxs-lookup"><span data-stu-id="6187c-108">The following table lists the .NET Framework data providers and their associated connection string builder classes.</span></span>  
  
|<span data-ttu-id="6187c-109">Proveedor</span><span class="sxs-lookup"><span data-stu-id="6187c-109">Provider</span></span>|<span data-ttu-id="6187c-110">Clase ConnectionStringBuilder</span><span class="sxs-lookup"><span data-stu-id="6187c-110">ConnectionStringBuilder class</span></span>|  
|--------------|-----------------------------------|  
|<xref:System.Data.SqlClient>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OleDb>|<xref:System.Data.OleDb.OleDbConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.Odbc>|<xref:System.Data.Odbc.OdbcConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OracleClient>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|  
  
## <a name="connection-string-injection-attacks"></a><span data-ttu-id="6187c-111">Ataques de inyección de cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="6187c-111">Connection String Injection Attacks</span></span>  
 <span data-ttu-id="6187c-112">Cuando se utiliza la concatenación dinámica de cadenas para generar cadenas de conexión basadas en datos introducidos por el usuario, se pueden producir ataques de inyección de cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="6187c-112">A connection string injection attack can occur when dynamic string concatenation is used to build connection strings that are based on user input.</span></span> <span data-ttu-id="6187c-113">Si no se valida la cadena y no se crean secuencias de escape para los caracteres o el texto malintencionado, los atacantes pueden tener acceso a datos confidenciales y a otros recursos del servidor.</span><span class="sxs-lookup"><span data-stu-id="6187c-113">If the string is not validated and malicious text or characters not escaped, an attacker can potentially access sensitive data or other resources on the server.</span></span> <span data-ttu-id="6187c-114">Por ejemplo, un atacante puede realizar un ataque si proporciona un punto y coma y anexa un valor adicional.</span><span class="sxs-lookup"><span data-stu-id="6187c-114">For example, an attacker could mount an attack by supplying a semicolon and appending an additional value.</span></span> <span data-ttu-id="6187c-115">La cadena de conexión se analiza utilizando un algoritmo del tipo "el último gana", y la entrada hostil se sustituye por un valor legítimo.</span><span class="sxs-lookup"><span data-stu-id="6187c-115">The connection string is parsed by using a "last one wins" algorithm, and the hostile input is substituted for a legitimate value.</span></span>  
  
 <span data-ttu-id="6187c-116">Las clases compiladoras de cadenas de conexión se han diseñado para eliminar la adivinación y desarrollar protección ante errores de sintaxis y vulnerabilidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6187c-116">The connection string builder classes are designed to eliminate guesswork and protect against syntax errors and security vulnerabilities.</span></span> <span data-ttu-id="6187c-117">Proporcionan métodos y propiedades que corresponden a los pares clave-valor conocidos permitidos por cada proveedor de datos.</span><span class="sxs-lookup"><span data-stu-id="6187c-117">They provide methods and properties corresponding to the known key/value pairs permitted by each data provider.</span></span> <span data-ttu-id="6187c-118">Cada clase mantiene una colección fija de sinónimos y puede convertir un sinónimo al correspondiente nombre de clave conocido.</span><span class="sxs-lookup"><span data-stu-id="6187c-118">Each class maintains a fixed collection of synonyms and can translate from a synonym to the corresponding well-known key name.</span></span> <span data-ttu-id="6187c-119">En los pares clave-valor se realizan comprobaciones y los pares no válidos inician una excepción.</span><span class="sxs-lookup"><span data-stu-id="6187c-119">Checks are performed for valid key/value pairs and an invalid pair throws an exception.</span></span> <span data-ttu-id="6187c-120">Además, los valores inyectados se controlan de forma segura.</span><span class="sxs-lookup"><span data-stu-id="6187c-120">In addition, injected values are handled in a safe manner.</span></span>  
  
 <span data-ttu-id="6187c-121">En el ejemplo siguiente se muestra cómo <xref:System.Data.SqlClient.SqlConnectionStringBuilder> controla un valor adicional insertado en la configuración `Initial Catalog`.</span><span class="sxs-lookup"><span data-stu-id="6187c-121">The following example demonstrates how the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handles an inserted extra value for the `Initial Catalog` setting.</span></span>  
  
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
  
 <span data-ttu-id="6187c-122">El resultado muestra que <xref:System.Data.SqlClient.SqlConnectionStringBuilder> controla esta situación correctamente, ya que establece el escape del valor adicional entre comillas dobles en lugar de anexarlo a la cadena de conexión como un nuevo par clave-valor.</span><span class="sxs-lookup"><span data-stu-id="6187c-122">The output shows that the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handled this correctly by escaping the extra value in double quotation marks instead of appending it to the connection string as a new key/value pair.</span></span>  
  
```output  
data source=(local);Integrated Security=True;  
initial catalog="AdventureWorks;NewValue=Bad"  
```  
  
## <a name="building-connection-strings-from-configuration-files"></a><span data-ttu-id="6187c-123">Crear cadenas de conexión a partir de archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="6187c-123">Building Connection Strings from Configuration Files</span></span>  
 <span data-ttu-id="6187c-124">Si determinados elementos de una cadena de conexión se conocen de antemano, se pueden almacenar en un archivo de configuración y recuperar en tiempo de ejecución para construir una cadena de conexión completa.</span><span class="sxs-lookup"><span data-stu-id="6187c-124">If certain elements of a connection string are known beforehand, they can be stored in a configuration file and retrieved at run time to construct a complete connection string.</span></span> <span data-ttu-id="6187c-125">Por ejemplo, se puede conocer por adelantado el nombre de la base de datos, pero no el del servidor.</span><span class="sxs-lookup"><span data-stu-id="6187c-125">For example, the name of the database might be known in advance, but not the name of the server.</span></span> <span data-ttu-id="6187c-126">También es posible que desee que un usuario indique un nombre y una contraseña en tiempo de ejecución sin que pueda inyectar otros valores en ella.</span><span class="sxs-lookup"><span data-stu-id="6187c-126">Or you might want a user to supply a name and password at run time without being able to inject other values into the connection string.</span></span>  
  
 <span data-ttu-id="6187c-127">Uno de los constructores sobrecargados de un compilador de cadenas de conexión toma <xref:System.String> como argumento, lo que permite proporcionar una cadena de conexión parcial que se puede completar después con los datos introducidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="6187c-127">One of the overloaded constructors for a connection string builder takes a <xref:System.String> as an argument, which enables you to supply a partial connection string that can then be completed from user input.</span></span> <span data-ttu-id="6187c-128">La cadena de conexión parcial se puede almacenar en un archivo de configuración y recuperarse en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6187c-128">The partial connection string can be stored in a configuration file and retrieved at run time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6187c-129">El espacio de nombres <xref:System.Configuration> permite el acceso mediante programación a archivos de configuración que usan <xref:System.Web.Configuration.WebConfigurationManager> en aplicaciones web y <xref:System.Configuration.ConfigurationManager> en aplicaciones Windows.</span><span class="sxs-lookup"><span data-stu-id="6187c-129">The <xref:System.Configuration> namespace allows programmatic access to configuration files that use the <xref:System.Web.Configuration.WebConfigurationManager> for Web applications and the <xref:System.Configuration.ConfigurationManager> for Windows applications.</span></span> <span data-ttu-id="6187c-130">Para obtener más información sobre cómo trabajar con cadenas de conexión y archivos de configuración, vea [cadenas de conexión y archivos de configuración](connection-strings-and-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="6187c-130">For more information about working with connection strings and configuration files, see [Connection Strings and Configuration Files](connection-strings-and-configuration-files.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="6187c-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6187c-131">Example</span></span>  
 <span data-ttu-id="6187c-132">En este ejemplo se muestra la recuperación de una cadena de conexión incluida en un archivo de configuración y cómo se completa mediante el establecimiento de las propiedades <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A> y <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> de <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="6187c-132">This example demonstrates retrieving a partial connection string from a configuration file and completing it by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A>, and <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> properties of the <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span> <span data-ttu-id="6187c-133">El archivo de configuración se define de la siguiente forma.</span><span class="sxs-lookup"><span data-stu-id="6187c-133">The configuration file is defined as follows.</span></span>  
  
```xml  
<connectionStrings>  
  <clear/>  
  <add name="partialConnectString"
    connectionString="Initial Catalog=Northwind;"  
    providerName="System.Data.SqlClient" />  
</connectionStrings>  
```  
  
> [!NOTE]
> <span data-ttu-id="6187c-134">Para ejecutar el código, debe establecer una referencia al archivo `System.Configuration.dll` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6187c-134">You must set a reference to the `System.Configuration.dll` in your project for the code to run.</span></span>  
  
 [!code-csharp[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/CS/source.cs#1)]
 [!code-vb[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6187c-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6187c-135">See also</span></span>

- [<span data-ttu-id="6187c-136">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="6187c-136">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="6187c-137">Privacidad y seguridad de datos</span><span class="sxs-lookup"><span data-stu-id="6187c-137">Privacy and Data Security</span></span>](privacy-and-data-security.md)
- [<span data-ttu-id="6187c-138">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6187c-138">ADO.NET Overview</span></span>](ado-net-overview.md)
