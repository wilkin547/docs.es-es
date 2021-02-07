---
description: Más información acerca de cómo establecer la conexión
title: Establecer la conexión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3af512f3-87d9-4005-9e2f-abb1060ff43f
ms.openlocfilehash: e7f8c837476a678f003eb0477934bb8bd08fd896
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724341"
---
# <a name="establishing-the-connection"></a><span data-ttu-id="0fafa-103">Establecer la conexión</span><span class="sxs-lookup"><span data-stu-id="0fafa-103">Establishing the Connection</span></span>

<span data-ttu-id="0fafa-104">Para conectarse a Microsoft SQL Server, use el objeto <xref:System.Data.SqlClient.SqlConnection> del proveedor de datos .NET Framework para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0fafa-104">To connect to Microsoft SQL Server, use the <xref:System.Data.SqlClient.SqlConnection> object of the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="0fafa-105">Para conectarse a un origen de datos OLE DB, use el objeto <xref:System.Data.OleDb.OleDbConnection> del proveedor de datos .NET Framework para OLE DB.</span><span class="sxs-lookup"><span data-stu-id="0fafa-105">To connect to an OLE DB data source, use the <xref:System.Data.OleDb.OleDbConnection> object of the .NET Framework Data Provider for OLE DB.</span></span> <span data-ttu-id="0fafa-106">Para conectarse a un origen de datos ODBC, utilice el objeto <xref:System.Data.Odbc.OdbcConnection> del proveedor de datos .NET Framework para ODBC.</span><span class="sxs-lookup"><span data-stu-id="0fafa-106">To connect to an ODBC data source, use the <xref:System.Data.Odbc.OdbcConnection> object of the .NET Framework Data Provider for ODBC.</span></span> <span data-ttu-id="0fafa-107">Para conectarse a un origen de datos Oracle, utilice el objeto <xref:System.Data.OracleClient.OracleConnection> del proveedor de datos .NET Framework para ODBC.</span><span class="sxs-lookup"><span data-stu-id="0fafa-107">To connect to an Oracle data source, use the <xref:System.Data.OracleClient.OracleConnection> object of the .NET Framework Data Provider for Oracle.</span></span> <span data-ttu-id="0fafa-108">Para almacenar y recuperar de forma segura las cadenas de conexión, vea [Proteger la información de conexión](protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="0fafa-108">For securely storing and retrieving connection strings, see [Protecting Connection Information](protecting-connection-information.md).</span></span>  
  
## <a name="closing-connections"></a><span data-ttu-id="0fafa-109">Cierre de conexiones</span><span class="sxs-lookup"><span data-stu-id="0fafa-109">Closing Connections</span></span>  

 <span data-ttu-id="0fafa-110">Recomendamos cerrar siempre la conexión cuando termine de utilizarla, para que la conexión pueda regresar al grupo.</span><span class="sxs-lookup"><span data-stu-id="0fafa-110">We recommend that you always close the connection when you are finished using it, so that the connection can be returned to the pool.</span></span> <span data-ttu-id="0fafa-111">El bloque `Using` de Visual Basic o C# elimina automáticamente la conexión cuando el código sale del bloque, incluso en el caso de una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="0fafa-111">The `Using` block in Visual Basic or C# automatically disposes of the connection when the code exits the block, even in the case of an unhandled exception.</span></span> <span data-ttu-id="0fafa-112">Vea [Instrucción using](../../../csharp/language-reference/keywords/using-statement.md) e [Instrucción using](../../../visual-basic/language-reference/statements/using-statement.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0fafa-112">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) and [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md) for more information.</span></span>  
  
 <span data-ttu-id="0fafa-113">También puede utilizar los métodos `Close` o `Dispose` del objeto de conexión correspondiente al proveedor que esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="0fafa-113">You can also use the `Close` or `Dispose` methods of the connection object for the provider that you are using.</span></span> <span data-ttu-id="0fafa-114">Es posible que las conexiones que no se cierran explícitamente no se puedan agregar ni puedan regresar al grupo.</span><span class="sxs-lookup"><span data-stu-id="0fafa-114">Connections that are not explicitly closed might not be added or returned to the pool.</span></span> <span data-ttu-id="0fafa-115">Por ejemplo, una conexión que se ha salido del ámbito pero que no se ha cerrado explícitamente solo se devolverá al grupo de conexión si se ha alcanzado el tamaño máximo del grupo y la conexión aún es válida.</span><span class="sxs-lookup"><span data-stu-id="0fafa-115">For example, a connection that has gone out of scope but that has not been explicitly closed will only be returned to the connection pool if the maximum pool size has been reached and the connection is still valid.</span></span> <span data-ttu-id="0fafa-116">Para obtener más información, vea [agrupación de conexiones de OLE DB, ODBC y Oracle](ole-db-odbc-and-oracle-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="0fafa-116">For more information, see [OLE DB, ODBC, and Oracle Connection Pooling](ole-db-odbc-and-oracle-connection-pooling.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fafa-117">No llame a `Close` o a `Dispose` en un objeto **Connection**, un objeto **DataReader** o cualquier otro objeto administrado en el método `Finalize` de la clase.</span><span class="sxs-lookup"><span data-stu-id="0fafa-117">Do not call `Close` or `Dispose` on a **Connection**, a **DataReader**, or any other managed object in the `Finalize` method of your class.</span></span> <span data-ttu-id="0fafa-118">En un finalizador, libere solo los recursos no administrados que pertenezcan directamente a su clase.</span><span class="sxs-lookup"><span data-stu-id="0fafa-118">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="0fafa-119">Si la clase no dispone de recursos no administrados, no incluya un método `Finalize` en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="0fafa-119">If your class does not own any unmanaged resources, do not include a `Finalize` method in your class definition.</span></span> <span data-ttu-id="0fafa-120">Para obtener más información, consulte [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="0fafa-120">For more information, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fafa-121">Los eventos de inicio y cierre de sesión no se provocarán en el servidor cuando se busque una conexión desde el grupo de conexiones o se devuelva a éste, puesto que la conexión no está cerrada realmente cuando se devuelve al grupo de conexiones.</span><span class="sxs-lookup"><span data-stu-id="0fafa-121">Login and logout events will not be raised on the server when a connection is fetched from or returned to the connection pool, because the connection is not actually closed when it is returned to the connection pool.</span></span> <span data-ttu-id="0fafa-122">Para obtener más información, vea [Agrupación de conexiones de SQL Server (ADO.NET)](sql-server-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="0fafa-122">For more information, see [SQL Server Connection Pooling (ADO.NET)](sql-server-connection-pooling.md).</span></span>  
  
## <a name="connecting-to-sql-server"></a><span data-ttu-id="0fafa-123">Conectarse a SQL Server</span><span class="sxs-lookup"><span data-stu-id="0fafa-123">Connecting to SQL Server</span></span>  

 <span data-ttu-id="0fafa-124">El proveedor de datos .NET Framework para SQL Server admite un formato de cadena de conexión que es similar al de OLE DB (ADO).</span><span class="sxs-lookup"><span data-stu-id="0fafa-124">The .NET Framework Data Provider for SQL Server supports a connection string format that is similar to the OLE DB (ADO) connection string format.</span></span> <span data-ttu-id="0fafa-125">Para consultar los nombres y valores válidos de formato de cadena, vea la propiedad <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> del objeto <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="0fafa-125">For valid string format names and values, see the <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> property of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="0fafa-126">También puede usar la clase <xref:System.Data.SqlClient.SqlConnectionStringBuilder> para crear cadenas de conexión sintácticamente válidas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0fafa-126">You can also use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> class to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="0fafa-127">Para obtener más información, vea [Generadores de cadenas de conexión](connection-string-builders.md).</span><span class="sxs-lookup"><span data-stu-id="0fafa-127">For more information, see [Connection String Builders](connection-string-builders.md).</span></span>  
  
 <span data-ttu-id="0fafa-128">El siguiente código de ejemplo demuestra cómo crear y abrir una conexión a una base de datos SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0fafa-128">The following code example demonstrates how to create and open a connection to a SQL Server database.</span></span>  
  
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
  
### <a name="integrated-security-and-aspnet"></a><span data-ttu-id="0fafa-129">Seguridad integrada y ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0fafa-129">Integrated Security and ASP.NET</span></span>  

 <span data-ttu-id="0fafa-130">La seguridad integrada de SQL Server (también conocida como conexiones de confianza) ayuda a proteger las conexiones a SQL Server dado que no expone el identificador y la contraseña de un usuario en la cadena de conexión y es el método recomendado para autenticar una conexión.</span><span class="sxs-lookup"><span data-stu-id="0fafa-130">SQL Server integrated security (also known as trusted connections) helps to provide protection when connecting to SQL Server as it does not expose a user ID and password in the connection string and is the recommended method for authenticating a connection.</span></span> <span data-ttu-id="0fafa-131">La seguridad integrada utiliza la identidad de seguridad actual, o símbolo (token), del proceso en ejecución, que</span><span class="sxs-lookup"><span data-stu-id="0fafa-131">Integrated security uses the current security identity, or token, of the executing process.</span></span> <span data-ttu-id="0fafa-132">en aplicaciones de escritorio, es normalmente la identidad del usuario que actualmente ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="0fafa-132">For desktop applications, this is typically the identity of the currently logged-on user.</span></span>  
  
 <span data-ttu-id="0fafa-133">La identidad de seguridad para aplicaciones ASP.NET se puede establecer en una de varias opciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="0fafa-133">The security identity for ASP.NET applications can be set to one of several different options.</span></span> <span data-ttu-id="0fafa-134">Para comprender mejor la identidad de seguridad que usa una aplicación de ASP.NET al conectarse a SQL Server, consulte [Suplantación de ASP.NET](/previous-versions/aspnet/xh507fc5(v=vs.100)), [Autenticación de ASP.NET](/previous-versions/aspnet/eeyk640h(v=vs.100))y [Procedimiento de acceso a SQL Server mediante la seguridad integrada de Windows](/previous-versions/aspnet/bsz5788z(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="0fafa-134">To better understand the security identity that an ASP.NET application uses when connecting to SQL Server, see [ASP.NET Impersonation](/previous-versions/aspnet/xh507fc5(v=vs.100)), [ASP.NET Authentication](/previous-versions/aspnet/eeyk640h(v=vs.100)), and [How to: Access SQL Server Using Windows Integrated Security](/previous-versions/aspnet/bsz5788z(v=vs.100)).</span></span>  
  
## <a name="connecting-to-an-ole-db-data-source"></a><span data-ttu-id="0fafa-135">Conexión a un origen de datos OLE DB</span><span class="sxs-lookup"><span data-stu-id="0fafa-135">Connecting to an OLE DB Data Source</span></span>  

 <span data-ttu-id="0fafa-136">El proveedor de datos de .NET Framework para OLE DB proporciona conectividad a los orígenes de datos expuestos mediante OLE DB (a través de SQLOLEDB, el proveedor de OLE DB para SQL Server), mediante el objeto **OleDbConnection** .</span><span class="sxs-lookup"><span data-stu-id="0fafa-136">The .NET Framework Data Provider for OLE DB provides connectivity to data sources exposed using OLE DB (through SQLOLEDB, the OLE DB Provider for SQL Server), using the **OleDbConnection** object.</span></span>  
  
 <span data-ttu-id="0fafa-137">En el proveedor de datos .NET Framework para OLE DB, el formato de cadena de conexión es idéntico al utilizado en ADO, con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="0fafa-137">For the .NET Framework Data Provider for OLE DB, the connection string format is identical to the connection string format used in ADO, with the following exceptions:</span></span>  
  
- <span data-ttu-id="0fafa-138">La palabra clave **Provider** es obligatoria.</span><span class="sxs-lookup"><span data-stu-id="0fafa-138">The **Provider** keyword is required.</span></span>  
  
- <span data-ttu-id="0fafa-139">No se admiten las palabras clave **URL**, **proveedor remoto** y **servidor remoto** .</span><span class="sxs-lookup"><span data-stu-id="0fafa-139">The **URL**, **Remote Provider**, and **Remote Server** keywords are not supported.</span></span>  
  
 <span data-ttu-id="0fafa-140">Para obtener más información acerca de las cadenas de conexión OLE DB, vea el tema <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="0fafa-140">For more information about OLE DB connection strings, see the <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> topic.</span></span> <span data-ttu-id="0fafa-141">También puede usar <xref:System.Data.OleDb.OleDbConnectionStringBuilder> para crear cadenas de conexión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0fafa-141">You can also use the <xref:System.Data.OleDb.OleDbConnectionStringBuilder> to create connection strings at run time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fafa-142">El objeto **OleDbConnection** no admite la configuración ni la recuperación de propiedades dinámicas específicas de un proveedor de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="0fafa-142">The **OleDbConnection** object does not support setting or retrieving dynamic properties specific to an OLE DB provider.</span></span> <span data-ttu-id="0fafa-143">Solo se admiten las propiedades que se pueden proporcionar en la cadena de conexión para el proveedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="0fafa-143">Only properties that can be passed in the connection string for the OLE DB provider are supported.</span></span>  
  
 <span data-ttu-id="0fafa-144">El siguiente código de ejemplo demuestra cómo crear y abrir una conexión a un origen de datos OLE DB.</span><span class="sxs-lookup"><span data-stu-id="0fafa-144">The following code example demonstrates how to create and open a connection to an OLE DB data source.</span></span>  
  
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
  
## <a name="do-not-use-universal-data-link-files"></a><span data-ttu-id="0fafa-145">No utilice archivos de vínculo de datos universal</span><span class="sxs-lookup"><span data-stu-id="0fafa-145">Do Not Use Universal Data Link Files</span></span>  

 <span data-ttu-id="0fafa-146">Es posible proporcionar información de conexión para un **OleDbConnection** en un archivo de vínculo de datos universal (UdL); sin embargo, debe evitar hacerlo.</span><span class="sxs-lookup"><span data-stu-id="0fafa-146">It is possible to supply connection information for an **OleDbConnection** in a Universal Data Link (UDL) file; however you should avoid doing so.</span></span> <span data-ttu-id="0fafa-147">Los archivos UDL no están cifrados y exponen la información de cadena de conexión en texto sin cifrar.</span><span class="sxs-lookup"><span data-stu-id="0fafa-147">UDL files are not encrypted, and expose connection string information in clear text.</span></span> <span data-ttu-id="0fafa-148">Un archivo UDL no se puede proteger mediante .NET Framework, ya que se trata de un recurso basado en un archivo externo a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0fafa-148">Because a UDL file is an external file-based resource to your application, it cannot be secured using the .NET Framework.</span></span>  
  
## <a name="connecting-to-an-odbc-data-source"></a><span data-ttu-id="0fafa-149">Conexión a un origen de datos ODBC</span><span class="sxs-lookup"><span data-stu-id="0fafa-149">Connecting to an ODBC Data Source</span></span>  

 <span data-ttu-id="0fafa-150">El proveedor de datos de .NET Framework para ODBC proporciona conectividad a los orígenes de datos expuestos mediante ODBC mediante el objeto **OdbcConnection** .</span><span class="sxs-lookup"><span data-stu-id="0fafa-150">The .NET Framework Data Provider for ODBC provides connectivity to data sources exposed using ODBC using the **OdbcConnection** object.</span></span>  
  
 <span data-ttu-id="0fafa-151">En el proveedor de datos .NET Framework para ODBC, el formato de cadena de conexión está diseñado para que coincida lo más posible con el de ODBC.</span><span class="sxs-lookup"><span data-stu-id="0fafa-151">For the .NET Framework Data Provider for ODBC, the connection string format is designed to match the ODBC connection string format as closely as possible.</span></span> <span data-ttu-id="0fafa-152">También puede proporcionar un nombre de origen de datos (DSN) ODBC.</span><span class="sxs-lookup"><span data-stu-id="0fafa-152">You may also supply an ODBC data source name (DSN).</span></span> <span data-ttu-id="0fafa-153">Para obtener más información sobre **OdbcConnection** , vea <xref:System.Data.Odbc.OdbcConnection> .</span><span class="sxs-lookup"><span data-stu-id="0fafa-153">For more detail on the **OdbcConnection** , see the <xref:System.Data.Odbc.OdbcConnection>.</span></span>  
  
 <span data-ttu-id="0fafa-154">El siguiente código de ejemplo demuestra cómo crear y abrir una conexión a un origen de datos ODBC.</span><span class="sxs-lookup"><span data-stu-id="0fafa-154">The following code example demonstrates how to create and open a connection to an ODBC data source.</span></span>  
  
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
  
## <a name="connecting-to-an-oracle-data-source"></a><span data-ttu-id="0fafa-155">Conexión a un origen de datos Oracle</span><span class="sxs-lookup"><span data-stu-id="0fafa-155">Connecting to an Oracle Data Source</span></span>  

 <span data-ttu-id="0fafa-156">El proveedor de datos de .NET Framework para Oracle proporciona conectividad a los orígenes de datos de Oracle mediante el objeto **OracleConnection** .</span><span class="sxs-lookup"><span data-stu-id="0fafa-156">The .NET Framework Data Provider for Oracle provides connectivity to Oracle data sources using the **OracleConnection** object.</span></span>  
  
 <span data-ttu-id="0fafa-157">En el proveedor de datos .NET Framework para Oracle, el formato de cadena de conexión está diseñado para que coincida lo más posible con el del proveedor OLE DB para Oracle (MSDAORA).</span><span class="sxs-lookup"><span data-stu-id="0fafa-157">For the .NET Framework Data Provider for Oracle, the connection string format is designed to match the OLE DB Provider for Oracle (MSDAORA) connection string format as closely as possible.</span></span> <span data-ttu-id="0fafa-158">Para obtener más información sobre **OracleConnection**, vea <xref:System.Data.OracleClient.OracleConnection> .</span><span class="sxs-lookup"><span data-stu-id="0fafa-158">For more detail on the **OracleConnection**, see the <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
 <span data-ttu-id="0fafa-159">El siguiente código de ejemplo demuestra cómo crear y abrir una conexión a un origen de datos Oracle.</span><span class="sxs-lookup"><span data-stu-id="0fafa-159">The following code example demonstrates how to create and open a connection to an Oracle data source.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0fafa-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fafa-160">See also</span></span>

- [<span data-ttu-id="0fafa-161">Conectarse a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="0fafa-161">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="0fafa-162">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="0fafa-162">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="0fafa-163">Agrupación de conexiones de OLE DB, ODBC y Oracle</span><span class="sxs-lookup"><span data-stu-id="0fafa-163">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)
- [<span data-ttu-id="0fafa-164">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0fafa-164">ADO.NET Overview</span></span>](ado-net-overview.md)
