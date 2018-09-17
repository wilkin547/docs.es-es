---
title: Conectarse a un origen de datos en ADO.NET
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: f5788b9b0b19f32d03c917575db7b3f40324c0a2
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45696164"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="0bd63-102">Conectarse a un origen de datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0bd63-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="0bd63-103">En ADO.NET utilizará un **conexión** objetos para conectarse a un origen de datos específica, proporcionando la información de autenticación necesaria en una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="0bd63-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="0bd63-104">El **conexión** objeto que se usa depende del tipo de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0bd63-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="0bd63-105">Cada proveedor de datos .NET Framework incluye un objeto <xref:System.Data.Common.DbConnection>: el proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbConnection>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlConnection>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcConnection> y el proveedor de datos .NET Framework para Oracle incluye un objeto <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="0bd63-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0bd63-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0bd63-106">In This Section</span></span>  
 [<span data-ttu-id="0bd63-107">Establecimiento de la conexión</span><span class="sxs-lookup"><span data-stu-id="0bd63-107">Establishing the Connection</span></span>](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 <span data-ttu-id="0bd63-108">Describe cómo utilizar un **conexión** objeto para establecer una conexión a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0bd63-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="0bd63-109">Eventos de conexión</span><span class="sxs-lookup"><span data-stu-id="0bd63-109">Connection Events</span></span>](../../../../docs/framework/data/adonet/connection-events.md)  
 <span data-ttu-id="0bd63-110">Describe cómo utilizar un **InfoMessage** event para recuperar mensajes informativos de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0bd63-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bd63-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bd63-111">See Also</span></span>  
 [<span data-ttu-id="0bd63-112">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="0bd63-112">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="0bd63-113">Agrupación de conexiones</span><span class="sxs-lookup"><span data-stu-id="0bd63-113">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [<span data-ttu-id="0bd63-114">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="0bd63-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="0bd63-115">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="0bd63-115">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="0bd63-116">Transacciones y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="0bd63-116">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="0bd63-117">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="0bd63-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
