---
title: Ejecutar un comando
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
ms.assetid: 40494916-c25a-4cb8-8f7c-fcb8d378464e
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c4879c49a410dfb40999f3163d8b23158cb71f0e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="executing-a-command"></a><span data-ttu-id="77452-102">Ejecutar un comando</span><span class="sxs-lookup"><span data-stu-id="77452-102">Executing a Command</span></span>
<span data-ttu-id="77452-103">Cada proveedor de datos .NET Framework incluido en .NET Framework dispone de su propio objeto command que hereda de <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="77452-103">Each .NET Framework data provider included with the .NET Framework has its own command object that inherits from <xref:System.Data.Common.DbCommand>.</span></span> <span data-ttu-id="77452-104">El proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbCommand>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlCommand>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcCommand> y el proveedor de datos .NET Framework para Oracle incluye un objeto <xref:System.Data.OracleClient.OracleCommand>.</span><span class="sxs-lookup"><span data-stu-id="77452-104">The .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbCommand> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlCommand> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcCommand> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleCommand> object.</span></span> <span data-ttu-id="77452-105">Cada uno de estos objetos expone métodos para ejecutar comandos que se basan en el tipo de comando y el valor devuelto deseado, tal como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="77452-105">Each of these objects exposes methods for executing commands based on the type of command and desired return value, as described in the following table.</span></span>  
  
|<span data-ttu-id="77452-106">Comando</span><span class="sxs-lookup"><span data-stu-id="77452-106">Command</span></span>|<span data-ttu-id="77452-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="77452-107">Return Value</span></span>|  
|-------------|------------------|  
|`ExecuteReader`|<span data-ttu-id="77452-108">Devuelve un objeto `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="77452-108">Returns a `DataReader` object.</span></span>|  
|`ExecuteScalar`|<span data-ttu-id="77452-109">Devuelve un solo valor escalar.</span><span class="sxs-lookup"><span data-stu-id="77452-109">Returns a single scalar value.</span></span>|  
|`ExecuteNonQuery`|<span data-ttu-id="77452-110">Ejecuta un comando que no devuelve ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="77452-110">Executes a command that does not return any rows.</span></span>|  
|`ExecuteXMLReader`|<span data-ttu-id="77452-111">Devuelve un valor <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="77452-111">Returns an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="77452-112">Solo está disponible para un objeto `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="77452-112">Available for a `SqlCommand` object only.</span></span>|  
  
 <span data-ttu-id="77452-113">Cada objeto command fuertemente tipado admite también una enumeración <xref:System.Data.CommandType> que especifica cómo se interpreta una cadena de comando, tal como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="77452-113">Each strongly typed command object also supports a <xref:System.Data.CommandType> enumeration that specifies how a command string is interpreted, as described in the following table.</span></span>  
  
|<span data-ttu-id="77452-114">CommandType</span><span class="sxs-lookup"><span data-stu-id="77452-114">CommandType</span></span>|<span data-ttu-id="77452-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="77452-115">Description</span></span>|  
|-----------------|-----------------|  
|`Text`|<span data-ttu-id="77452-116">Comando de SQL que define las instrucciones que se van a ejecutar en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="77452-116">An SQL command defining the statements to be executed at the data source.</span></span>|  
|`StoredProcedure`|<span data-ttu-id="77452-117">Nombre del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="77452-117">The name of the stored procedure.</span></span> <span data-ttu-id="77452-118">Puede usar la propiedad `Parameters` de un comando para tener acceso a los parámetros de entrada y de salida y a los valores devueltos, independientemente del método `Execute` al que se llame.</span><span class="sxs-lookup"><span data-stu-id="77452-118">You can use the `Parameters` property of a command to access input and output parameters and return values, regardless of which `Execute` method is called.</span></span> <span data-ttu-id="77452-119">Al usar `ExecuteReader`, no es posible el acceso a los valores devueltos y los parámetros de salida hasta que se cierra `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="77452-119">When using `ExecuteReader`, return values and output parameters will not be accessible until the `DataReader` is closed.</span></span>|  
|`TableDirect`|<span data-ttu-id="77452-120">Nombre de una tabla.</span><span class="sxs-lookup"><span data-stu-id="77452-120">The name of a table.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="77452-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="77452-121">Example</span></span>  
 <span data-ttu-id="77452-122">En el ejemplo de código siguiente se muestra cómo se crea un objeto <xref:System.Data.SqlClient.SqlCommand> para ejecutar un procedimiento almacenado mediante el establecimiento de sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="77452-122">The following code example demonstrates how to create a <xref:System.Data.SqlClient.SqlCommand> object to execute a stored procedure by setting its properties.</span></span> <span data-ttu-id="77452-123">Para especificar el parámetro de entrada del procedimiento almacenado se usa un objeto <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="77452-123">A <xref:System.Data.SqlClient.SqlParameter> object is used to specify the input parameter to the stored procedure.</span></span> <span data-ttu-id="77452-124">El comando se ejecuta con el método <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> y el resultado de <xref:System.Data.SqlClient.SqlDataReader> se muestra en la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="77452-124">The command is executed using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method, and the output from the <xref:System.Data.SqlClient.SqlDataReader> is displayed in the console window.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/VB/source.vb#1)]  
  
### <a name="troubleshooting-commands"></a><span data-ttu-id="77452-125">Solución de problemas de comandos</span><span class="sxs-lookup"><span data-stu-id="77452-125">Troubleshooting Commands</span></span>  
 <span data-ttu-id="77452-126">El proveedor de datos .NET Framework para SQL Server agrega contadores de rendimiento que permiten detectar problemas intermitentes relacionados con errores en la ejecución de comandos.</span><span class="sxs-lookup"><span data-stu-id="77452-126">The .NET Framework Data Provider for SQL Server adds performance counters to enable you to detect intermittent problems related to failed command executions.</span></span> <span data-ttu-id="77452-127">Para obtener más información, consulte [contadores de rendimiento](../../../../docs/framework/data/adonet/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="77452-127">For more information see [Performance Counters](../../../../docs/framework/data/adonet/performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77452-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="77452-128">See Also</span></span>  
 [<span data-ttu-id="77452-129">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="77452-129">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="77452-130">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="77452-130">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="77452-131">Trabajar con DataReaders</span><span class="sxs-lookup"><span data-stu-id="77452-131">Working with DataReaders</span></span>](http://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [<span data-ttu-id="77452-132">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="77452-132">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
