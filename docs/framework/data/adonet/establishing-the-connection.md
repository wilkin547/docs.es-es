---
title: "Establecer la conexión"
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
ms.assetid: 3af512f3-87d9-4005-9e2f-abb1060ff43f
caps.latest.revision: "7"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 416d89aef35fef5dd0ac2bca92fb8a90d757a2d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="establishing-the-connection"></a><span data-ttu-id="91f63-102">Establecer la conexión</span><span class="sxs-lookup"><span data-stu-id="91f63-102">Establishing the Connection</span></span>
<span data-ttu-id="91f63-103">Para conectarse a Microsoft SQL Server, use el objeto <xref:System.Data.SqlClient.SqlConnection> del proveedor de datos .NET Framework para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="91f63-103">To connect to Microsoft SQL Server, use the <xref:System.Data.SqlClient.SqlConnection> object of the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="91f63-104">Para conectarse a un origen de datos OLE DB, use el objeto <xref:System.Data.OleDb.OleDbConnection> del proveedor de datos .NET Framework para OLE DB.</span><span class="sxs-lookup"><span data-stu-id="91f63-104">To connect to an OLE DB data source, use the <xref:System.Data.OleDb.OleDbConnection> object of the .NET Framework Data Provider for OLE DB.</span></span> <span data-ttu-id="91f63-105">Para conectarse a un origen de datos ODBC, utilice el objeto <xref:System.Data.Odbc.OdbcConnection> del proveedor de datos .NET Framework para ODBC.</span><span class="sxs-lookup"><span data-stu-id="91f63-105">To connect to an ODBC data source, use the <xref:System.Data.Odbc.OdbcConnection> object of the .NET Framework Data Provider for ODBC.</span></span> <span data-ttu-id="91f63-106">Para conectarse a un origen de datos Oracle, utilice el objeto <xref:System.Data.OracleClient.OracleConnection> del proveedor de datos .NET Framework para ODBC.</span><span class="sxs-lookup"><span data-stu-id="91f63-106">To connect to an Oracle data source, use the <xref:System.Data.OracleClient.OracleConnection> object of the .NET Framework Data Provider for Oracle.</span></span> <span data-ttu-id="91f63-107">Para almacenar de forma segura y recuperar cadenas de conexión, vea [protección de información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="91f63-107">For securely storing and retrieving connection strings, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="closing-connections"></a><span data-ttu-id="91f63-108">Cierre de conexiones</span><span class="sxs-lookup"><span data-stu-id="91f63-108">Closing Connections</span></span>  
 <span data-ttu-id="91f63-109">Recomendamos cerrar siempre la conexión cuando termine de utilizarla, para que la conexión pueda regresar al grupo.</span><span class="sxs-lookup"><span data-stu-id="91f63-109">We recommend that you always close the connection when you are finished using it, so that the connection can be returned to the pool.</span></span> <span data-ttu-id="91f63-110">El bloque `Using` de Visual Basic o C# elimina automáticamente la conexión cuando el código sale del bloque, incluso en el caso de una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="91f63-110">The `Using` block in Visual Basic or C# automatically disposes of the connection when the code exits the block, even in the case of an unhandled exception.</span></span> <span data-ttu-id="91f63-111">Vea [mediante la instrucción](~/docs/csharp/language-reference/keywords/using-statement.md) y [instrucción Using](~/docs/visual-basic/language-reference/statements/using-statement.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="91f63-111">See [using Statement](~/docs/csharp/language-reference/keywords/using-statement.md) and [Using Statement](~/docs/visual-basic/language-reference/statements/using-statement.md) for more information.</span></span>  
  
 <span data-ttu-id="91f63-112">También puede utilizar los métodos `Close` o `Dispose` del objeto de conexión correspondiente al proveedor que esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="91f63-112">You can also use the `Close` or `Dispose` methods of the connection object for the provider that you are using.</span></span> <span data-ttu-id="91f63-113">Es posible que las conexiones que no se cierran explícitamente no se puedan agregar ni puedan regresar al grupo.</span><span class="sxs-lookup"><span data-stu-id="91f63-113">Connections that are not explicitly closed might not be added or returned to the pool.</span></span> <span data-ttu-id="91f63-114">Por ejemplo, una conexión que se ha salido del ámbito pero que no se ha cerrado explícitamente solo se devolverá al grupo de conexión si se ha alcanzado el tamaño máximo del grupo y la conexión aún es válida.</span><span class="sxs-lookup"><span data-stu-id="91f63-114">For example, a connection that has gone out of scope but that has not been explicitly closed will only be returned to the connection pool if the maximum pool size has been reached and the connection is still valid.</span></span> <span data-ttu-id="91f63-115">Para obtener más información, consulte [OLE DB, ODBC y agrupación de conexiones de Oracle](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="91f63-115">For more information, see [OLE DB, ODBC, and Oracle Connection Pooling](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91f63-116">No llame a `Close` o `Dispose` en un **conexión**, **DataReader**, o cualquier otro objeto administrado en el `Finalize` método de la clase.</span><span class="sxs-lookup"><span data-stu-id="91f63-116">Do not call `Close` or `Dispose` on a **Connection**, a **DataReader**, or any other managed object in the `Finalize` method of your class.</span></span> <span data-ttu-id="91f63-117">En un finalizador, libere solo los recursos no administrados que pertenezcan directamente a su clase.</span><span class="sxs-lookup"><span data-stu-id="91f63-117">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="91f63-118">Si la clase no dispone de recursos no administrados, no incluya un método `Finalize` en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="91f63-118">If your class does not own any unmanaged resources, do not include a `Finalize` method in your class definition.</span></span> <span data-ttu-id="91f63-119">Para obtener más información, consulte [recolección](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="91f63-119">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91f63-120">Los eventos de inicio y cierre de sesión no se provocarán en el servidor cuando se busque una conexión desde el grupo de conexiones o se devuelva a éste, puesto que la conexión no está cerrada realmente cuando se devuelve al grupo de conexiones.</span><span class="sxs-lookup"><span data-stu-id="91f63-120">Login and logout events will not be raised on the server when a connection is fetched from or returned to the connection pool, because the connection is not actually closed when it is returned to the connection pool.</span></span> <span data-ttu-id="91f63-121">Para obtener más información, consulte [SQL Server Connection Pooling (ADO.NET)](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="91f63-121">For more information, see [SQL Server Connection Pooling (ADO.NET)](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span>  
  
## <a name="connecting-to-sql-server"></a><span data-ttu-id="91f63-122">Conexión a SQL Server</span><span class="sxs-lookup"><span data-stu-id="91f63-122">Connecting to SQL Server</span></span>  
 <span data-ttu-id="91f63-123">El proveedor de datos .NET Framework para SQL Server admite un formato de cadena de conexión que es similar al de OLE DB (ADO).</span><span class="sxs-lookup"><span data-stu-id="91f63-123">The .NET Framework Data Provider for SQL Server supports a connection string format that is similar to the OLE DB (ADO) connection string format.</span></span> <span data-ttu-id="91f63-124">Para consultar los nombres y valores válidos de formato de cadena, vea la propiedad <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> del objeto <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="91f63-124">For valid string format names and values, see the <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> property of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="91f63-125">También puede usar la clase <xref:System.Data.SqlClient.SqlConnectionStringBuilder> para crear cadenas de conexión sintácticamente válidas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="91f63-125">You can also use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> class to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="91f63-126">Para obtener más información, consulte [generadores de cadenas de conexión](../../../../docs/framework/data/adonet/connection-string-builders.md).</span><span class="sxs-lookup"><span data-stu-id="91f63-126">For more information, see [Connection String Builders](../../../../docs/framework/data/adonet/connection-string-builders.md).</span></span>  
  
 <span data-ttu-id="91f63-127">El siguiente código de ejemplo demuestra cómo crear y abrir una conexión a una base de datos SQL Server.</span><span class="sxs-lookup"><span data-stu-id="91f63-127">The following code example demonstrates how to create and open a connection to a SQL Server database.</span></span>  
  
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
  
### <a name="integrated-security-and-aspnet"></a><span data-ttu-id="91f63-128">Seguridad integrada y ASP.NET</span><span class="sxs-lookup"><span data-stu-id="91f63-128">Integrated Security and ASP.NET</span></span>  
 <span data-ttu-id="91f63-129">La seguridad integrada de SQL Server (también conocida como conexiones de confianza) ayuda a proteger las conexiones a SQL Server dado que no expone el identificador y la contraseña de un usuario en la cadena de conexión y es el método recomendado para autenticar una conexión.</span><span class="sxs-lookup"><span data-stu-id="91f63-129">SQL Server integrated security (also known as trusted connections) helps to provide protection when connecting to SQL Server as it does not expose a user ID and password in the connection string and is the recommended method for authenticating a connection.</span></span> <span data-ttu-id="91f63-130">La seguridad integrada utiliza la identidad de seguridad actual, o símbolo (token), del proceso en ejecución, que</span><span class="sxs-lookup"><span data-stu-id="91f63-130">Integrated security uses the current security identity, or token, of the executing process.</span></span> <span data-ttu-id="91f63-131">en aplicaciones de escritorio, es normalmente la identidad del usuario que actualmente ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="91f63-131">For desktop applications, this is typically the identity of the currently logged-on user.</span></span>  
  
 <span data-ttu-id="91f63-132">La identidad de seguridad para aplicaciones ASP.NET se puede establecer en una de varias opciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="91f63-132">The security identity for ASP.NET applications can be set to one of several different options.</span></span> <span data-ttu-id="91f63-133">Para entender mejor la identidad de seguridad que una aplicación ASP.NET utiliza al conectarse a SQL Server, vea [suplantación de ASP.NET](http://msdn.microsoft.com/library/a0cb3024-562f-4184-9d3c-095504787d3d), [la autenticación de ASP.NET](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1), y [Cómo: acceso SQL La seguridad integrada de servidor mediante Windows](http://msdn.microsoft.com/library/683f9c9f-4375-4de6-8111-943c4423fde5).</span><span class="sxs-lookup"><span data-stu-id="91f63-133">To better understand the security identity that an ASP.NET application uses when connecting to SQL Server, see [ASP.NET Impersonation](http://msdn.microsoft.com/library/a0cb3024-562f-4184-9d3c-095504787d3d), [ASP.NET Authentication](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1), and [How to: Access SQL Server Using Windows Integrated Security](http://msdn.microsoft.com/library/683f9c9f-4375-4de6-8111-943c4423fde5).</span></span>  
  
## <a name="connecting-to-an-ole-db-data-source"></a><span data-ttu-id="91f63-134">Conexión a un origen de datos OLE DB</span><span class="sxs-lookup"><span data-stu-id="91f63-134">Connecting to an OLE DB Data Source</span></span>  
 <span data-ttu-id="91f63-135">El proveedor de datos de .NET Framework para OLE DB proporciona conectividad a orígenes de datos expuestos mediante OLE DB (a través de SQLOLEDB, el proveedor OLE DB para SQL Server), con el **OleDbConnection** objeto.</span><span class="sxs-lookup"><span data-stu-id="91f63-135">The .NET Framework Data Provider for OLE DB provides connectivity to data sources exposed using OLE DB (through SQLOLEDB, the OLE DB Provider for SQL Server), using the **OleDbConnection** object.</span></span>  
  
 <span data-ttu-id="91f63-136">En el proveedor de datos .NET Framework para OLE DB, el formato de cadena de conexión es idéntico al utilizado en ADO, con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="91f63-136">For the .NET Framework Data Provider for OLE DB, the connection string format is identical to the connection string format used in ADO, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="91f63-137">El **proveedor** palabra clave es necesaria.</span><span class="sxs-lookup"><span data-stu-id="91f63-137">The **Provider** keyword is required.</span></span>  
  
-   <span data-ttu-id="91f63-138">El **URL**, **proveedor remoto**, y **servidor remoto** palabras clave no se admite.</span><span class="sxs-lookup"><span data-stu-id="91f63-138">The **URL**, **Remote Provider**, and **Remote Server** keywords are not supported.</span></span>  
  
 <span data-ttu-id="91f63-139">Para obtener más información acerca de las cadenas de conexión OLE DB, vea el tema <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="91f63-139">For more information about OLE DB connection strings, see the <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> topic.</span></span> <span data-ttu-id="91f63-140">También puede usar <xref:System.Data.OleDb.OleDbConnectionStringBuilder> para crear cadenas de conexión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="91f63-140">You can also use the <xref:System.Data.OleDb.OleDbConnectionStringBuilder> to create connection strings at run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91f63-141">El **OleDbConnection** objeto no admite la configuración ni la recuperación de propiedades dinámicas específicas de un proveedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="91f63-141">The **OleDbConnection** object does not support setting or retrieving dynamic properties specific to an OLE DB provider.</span></span> <span data-ttu-id="91f63-142">Solo se admiten las propiedades que se pueden proporcionar en la cadena de conexión para el proveedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="91f63-142">Only properties that can be passed in the connection string for the OLE DB provider are supported.</span></span>  
  
 <span data-ttu-id="91f63-143">El siguiente código de ejemplo demuestra cómo crear y abrir una conexión a un origen de datos OLE DB.</span><span class="sxs-lookup"><span data-stu-id="91f63-143">The following code example demonstrates how to create and open a connection to an OLE DB data source.</span></span>  
  
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
  
## <a name="do-not-use-universal-data-link-files"></a><span data-ttu-id="91f63-144">No utilice archivos de vínculo de datos universal</span><span class="sxs-lookup"><span data-stu-id="91f63-144">Do Not Use Universal Data Link Files</span></span>  
 <span data-ttu-id="91f63-145">Es posible proporcionar información de conexión para un **OleDbConnection** en un archivo de vínculo de datos Universal (UDL); sin embargo conviene evitarlo.</span><span class="sxs-lookup"><span data-stu-id="91f63-145">It is possible to supply connection information for an **OleDbConnection** in a Universal Data Link (UDL) file; however you should avoid doing so.</span></span> <span data-ttu-id="91f63-146">Los archivos UDL no están cifrados y exponen la información de cadena de conexión en texto sin cifrar.</span><span class="sxs-lookup"><span data-stu-id="91f63-146">UDL files are not encrypted, and expose connection string information in clear text.</span></span> <span data-ttu-id="91f63-147">Un archivo UDL no se puede proteger mediante .NET Framework, ya que se trata de un recurso basado en un archivo externo a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="91f63-147">Because a UDL file is an external file-based resource to your application, it cannot be secured using the .NET Framework.</span></span>  
  
## <a name="connecting-to-an-odbc-data-source"></a><span data-ttu-id="91f63-148">Conexión a un origen de datos ODBC</span><span class="sxs-lookup"><span data-stu-id="91f63-148">Connecting to an ODBC Data Source</span></span>  
 <span data-ttu-id="91f63-149">El proveedor de datos de .NET Framework para ODBC proporciona conectividad a orígenes de datos expuestos mediante ODBC utilizando el **OdbcConnection** objeto.</span><span class="sxs-lookup"><span data-stu-id="91f63-149">The .NET Framework Data Provider for ODBC provides connectivity to data sources exposed using ODBC using the **OdbcConnection** object.</span></span>  
  
 <span data-ttu-id="91f63-150">En el proveedor de datos .NET Framework para ODBC, el formato de cadena de conexión está diseñado para que coincida lo más posible con el de ODBC.</span><span class="sxs-lookup"><span data-stu-id="91f63-150">For the .NET Framework Data Provider for ODBC, the connection string format is designed to match the ODBC connection string format as closely as possible.</span></span> <span data-ttu-id="91f63-151">También puede proporcionar un nombre de origen de datos (DSN) ODBC.</span><span class="sxs-lookup"><span data-stu-id="91f63-151">You may also supply an ODBC data source name (DSN).</span></span> <span data-ttu-id="91f63-152">Para obtener más detalles sobre la **OdbcConnection** , consulte el <xref:System.Data.Odbc.OdbcConnection>.</span><span class="sxs-lookup"><span data-stu-id="91f63-152">For more detail on the **OdbcConnection** , see the <xref:System.Data.Odbc.OdbcConnection>.</span></span>  
  
 <span data-ttu-id="91f63-153">El siguiente código de ejemplo demuestra cómo crear y abrir una conexión a un origen de datos ODBC.</span><span class="sxs-lookup"><span data-stu-id="91f63-153">The following code example demonstrates how to create and open a connection to an ODBC data source.</span></span>  
  
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
  
## <a name="connecting-to-an-oracle-data-source"></a><span data-ttu-id="91f63-154">Conexión a un origen de datos Oracle</span><span class="sxs-lookup"><span data-stu-id="91f63-154">Connecting to an Oracle Data Source</span></span>  
 <span data-ttu-id="91f63-155">El proveedor de datos de .NET Framework para Oracle proporciona conectividad a orígenes de datos de Oracle mediante la **OracleConnection** objeto.</span><span class="sxs-lookup"><span data-stu-id="91f63-155">The .NET Framework Data Provider for Oracle provides connectivity to Oracle data sources using the **OracleConnection** object.</span></span>  
  
 <span data-ttu-id="91f63-156">En el proveedor de datos .NET Framework para Oracle, el formato de cadena de conexión está diseñado para que coincida lo más posible con el del proveedor OLE DB para Oracle (MSDAORA).</span><span class="sxs-lookup"><span data-stu-id="91f63-156">For the .NET Framework Data Provider for Oracle, the connection string format is designed to match the OLE DB Provider for Oracle (MSDAORA) connection string format as closely as possible.</span></span> <span data-ttu-id="91f63-157">Para obtener más detalles sobre la **OracleConnection**, consulte el <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="91f63-157">For more detail on the **OracleConnection**, see the <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
 <span data-ttu-id="91f63-158">El siguiente código de ejemplo demuestra cómo crear y abrir una conexión a un origen de datos Oracle.</span><span class="sxs-lookup"><span data-stu-id="91f63-158">The following code example demonstrates how to create and open a connection to an Oracle data source.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="91f63-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="91f63-159">See Also</span></span>  
 [<span data-ttu-id="91f63-160">Conexión a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="91f63-160">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="91f63-161">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="91f63-161">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="91f63-162">Agrupación de conexiones de OLE DB, ODBC y Oracle</span><span class="sxs-lookup"><span data-stu-id="91f63-162">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 [<span data-ttu-id="91f63-163">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="91f63-163">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
