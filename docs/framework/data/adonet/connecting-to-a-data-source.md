---
title: Conectarse a un origen de datos en ADO.NET
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 01e4048fb9c7b53b1b1907d1965f822b9a4644a4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786764"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="4c56c-102">Conectarse a un origen de datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4c56c-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="4c56c-103">En ADO.NET se usa un objeto de **conexión** para conectarse a un origen de datos específico proporcionando la información de autenticación necesaria en una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="4c56c-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="4c56c-104">El objeto de **conexión** que se utiliza depende del tipo de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="4c56c-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="4c56c-105">Cada proveedor de datos .NET Framework incluye un objeto <xref:System.Data.Common.DbConnection>: el proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbConnection>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlConnection>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcConnection> y el proveedor de datos .NET Framework para Oracle incluye un objeto <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="4c56c-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c56c-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4c56c-106">In This Section</span></span>  
 [<span data-ttu-id="4c56c-107">Establecimiento de la conexión</span><span class="sxs-lookup"><span data-stu-id="4c56c-107">Establishing the Connection</span></span>](establishing-the-connection.md)  
 <span data-ttu-id="4c56c-108">Describe cómo utilizar un objeto de **conexión** para establecer una conexión a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="4c56c-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="4c56c-109">Eventos de conexión</span><span class="sxs-lookup"><span data-stu-id="4c56c-109">Connection Events</span></span>](connection-events.md)  
 <span data-ttu-id="4c56c-110">Describe cómo usar un evento **InfoMessage** para recuperar mensajes informativos de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="4c56c-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c56c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c56c-111">See also</span></span>

- [<span data-ttu-id="4c56c-112">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="4c56c-112">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="4c56c-113">Agrupación de conexiones</span><span class="sxs-lookup"><span data-stu-id="4c56c-113">Connection Pooling</span></span>](connection-pooling.md)
- [<span data-ttu-id="4c56c-114">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="4c56c-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="4c56c-115">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="4c56c-115">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="4c56c-116">Transacciones y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="4c56c-116">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="4c56c-117">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4c56c-117">ADO.NET Overview</span></span>](ado-net-overview.md)
