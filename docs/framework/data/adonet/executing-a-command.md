---
description: Más información acerca de cómo ejecutar un comando
title: Ejecutar un comando
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 40494916-c25a-4cb8-8f7c-fcb8d378464e
ms.openlocfilehash: 7b5fe46bf4d82fcd4f24cc0eb19e85a2ee9aca7b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724328"
---
# <a name="executing-a-command"></a><span data-ttu-id="d9d75-103">Ejecutar un comando</span><span class="sxs-lookup"><span data-stu-id="d9d75-103">Executing a Command</span></span>

<span data-ttu-id="d9d75-104">Cada proveedor de datos .NET Framework incluido en .NET Framework dispone de su propio objeto command que hereda de <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="d9d75-104">Each .NET Framework data provider included with the .NET Framework has its own command object that inherits from <xref:System.Data.Common.DbCommand>.</span></span> <span data-ttu-id="d9d75-105">El proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbCommand>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlCommand>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcCommand> y el proveedor de datos .NET Framework para Oracle incluye un objeto <xref:System.Data.OracleClient.OracleCommand>.</span><span class="sxs-lookup"><span data-stu-id="d9d75-105">The .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbCommand> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlCommand> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcCommand> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleCommand> object.</span></span> <span data-ttu-id="d9d75-106">Cada uno de estos objetos expone métodos para ejecutar comandos que se basan en el tipo de comando y el valor devuelto deseado, tal como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d9d75-106">Each of these objects exposes methods for executing commands based on the type of command and desired return value, as described in the following table.</span></span>  
  
|<span data-ttu-id="d9d75-107">Get-Help</span><span class="sxs-lookup"><span data-stu-id="d9d75-107">Command</span></span>|<span data-ttu-id="d9d75-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d9d75-108">Return Value</span></span>|  
|-------------|------------------|  
|`ExecuteReader`|<span data-ttu-id="d9d75-109">Devuelve un objeto `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="d9d75-109">Returns a `DataReader` object.</span></span>|  
|`ExecuteScalar`|<span data-ttu-id="d9d75-110">Devuelve un solo valor escalar.</span><span class="sxs-lookup"><span data-stu-id="d9d75-110">Returns a single scalar value.</span></span>|  
|`ExecuteNonQuery`|<span data-ttu-id="d9d75-111">Ejecuta un comando que no devuelve ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="d9d75-111">Executes a command that does not return any rows.</span></span>|  
|`ExecuteXMLReader`|<span data-ttu-id="d9d75-112">Devuelve un valor <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="d9d75-112">Returns an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="d9d75-113">Solo está disponible para un objeto `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="d9d75-113">Available for a `SqlCommand` object only.</span></span>|  
  
 <span data-ttu-id="d9d75-114">Cada objeto command fuertemente tipado admite también una enumeración <xref:System.Data.CommandType> que especifica cómo se interpreta una cadena de comando, tal como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d9d75-114">Each strongly typed command object also supports a <xref:System.Data.CommandType> enumeration that specifies how a command string is interpreted, as described in the following table.</span></span>  
  
|<span data-ttu-id="d9d75-115">CommandType</span><span class="sxs-lookup"><span data-stu-id="d9d75-115">CommandType</span></span>|<span data-ttu-id="d9d75-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9d75-116">Description</span></span>|  
|-----------------|-----------------|  
|`Text`|<span data-ttu-id="d9d75-117">Comando de SQL que define las instrucciones que se van a ejecutar en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d9d75-117">An SQL command defining the statements to be executed at the data source.</span></span>|  
|`StoredProcedure`|<span data-ttu-id="d9d75-118">Nombre del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="d9d75-118">The name of the stored procedure.</span></span> <span data-ttu-id="d9d75-119">Puede usar la propiedad `Parameters` de un comando para tener acceso a los parámetros de entrada y de salida y a los valores devueltos, independientemente del método `Execute` al que se llame.</span><span class="sxs-lookup"><span data-stu-id="d9d75-119">You can use the `Parameters` property of a command to access input and output parameters and return values, regardless of which `Execute` method is called.</span></span> <span data-ttu-id="d9d75-120">Al usar `ExecuteReader`, no es posible el acceso a los valores devueltos y los parámetros de salida hasta que se cierra `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="d9d75-120">When using `ExecuteReader`, return values and output parameters will not be accessible until the `DataReader` is closed.</span></span>|  
|`TableDirect`|<span data-ttu-id="d9d75-121">Nombre de una tabla.</span><span class="sxs-lookup"><span data-stu-id="d9d75-121">The name of a table.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d9d75-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d9d75-122">Example</span></span>  

 <span data-ttu-id="d9d75-123">En el ejemplo de código siguiente se muestra cómo se crea un objeto <xref:System.Data.SqlClient.SqlCommand> para ejecutar un procedimiento almacenado mediante el establecimiento de sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="d9d75-123">The following code example demonstrates how to create a <xref:System.Data.SqlClient.SqlCommand> object to execute a stored procedure by setting its properties.</span></span> <span data-ttu-id="d9d75-124">Para especificar el parámetro de entrada del procedimiento almacenado se usa un objeto <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="d9d75-124">A <xref:System.Data.SqlClient.SqlParameter> object is used to specify the input parameter to the stored procedure.</span></span> <span data-ttu-id="d9d75-125">El comando se ejecuta con el método <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> y el resultado de <xref:System.Data.SqlClient.SqlDataReader> se muestra en la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="d9d75-125">The command is executed using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method, and the output from the <xref:System.Data.SqlClient.SqlDataReader> is displayed in the console window.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/VB/source.vb#1)]  
  
### <a name="troubleshooting-commands"></a><span data-ttu-id="d9d75-126">Solución de problemas de comandos</span><span class="sxs-lookup"><span data-stu-id="d9d75-126">Troubleshooting Commands</span></span>  

 <span data-ttu-id="d9d75-127">El proveedor de datos .NET Framework para SQL Server agrega contadores de rendimiento que permiten detectar problemas intermitentes relacionados con errores en la ejecución de comandos.</span><span class="sxs-lookup"><span data-stu-id="d9d75-127">The .NET Framework Data Provider for SQL Server adds performance counters to enable you to detect intermittent problems related to failed command executions.</span></span> <span data-ttu-id="d9d75-128">Para obtener más información, vea [contadores de rendimiento](performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="d9d75-128">For more information see [Performance Counters](performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9d75-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9d75-129">See also</span></span>

- [<span data-ttu-id="d9d75-130">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="d9d75-130">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="d9d75-131">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="d9d75-131">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="d9d75-132">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d9d75-132">ADO.NET Overview</span></span>](ado-net-overview.md)
