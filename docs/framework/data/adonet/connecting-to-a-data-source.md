---
title: Conectar con un origen de datos
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 206a4f741b6bf711b51da794e23f779c2bea6fa0
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094454"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="c1955-102">Conectarse a un origen de datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c1955-102">Connecting to a Data Source in ADO.NET</span></span>

<span data-ttu-id="c1955-103">En ADO.NET, se usa un objeto de **conexión** para conectarse a un origen de datos específico proporcionando la información de autenticación necesaria en una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="c1955-103">In ADO.NET, you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="c1955-104">El objeto de **conexión** que se utiliza depende del tipo de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c1955-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="c1955-105">Cada proveedor de datos .NET Framework incluye un objeto <xref:System.Data.Common.DbConnection>: el proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbConnection>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlConnection>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcConnection> y el proveedor de datos .NET Framework para Oracle incluye un objeto <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="c1955-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1955-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c1955-106">In This Section</span></span>  
 <span data-ttu-id="c1955-107">[Establecimiento de la conexión](establishing-the-connection.md)</span><span class="sxs-lookup"><span data-stu-id="c1955-107">[Establishing the Connection](establishing-the-connection.md)</span></span>\
 <span data-ttu-id="c1955-108">Describe cómo utilizar un objeto de **conexión** para establecer una conexión a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c1955-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 <span data-ttu-id="c1955-109">[Eventos de conexión](connection-events.md)</span><span class="sxs-lookup"><span data-stu-id="c1955-109">[Connection Events](connection-events.md)</span></span>\
 <span data-ttu-id="c1955-110">Describe cómo usar un evento **InfoMessage** para recuperar mensajes informativos de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c1955-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1955-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1955-111">See also</span></span>

- [<span data-ttu-id="c1955-112">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="c1955-112">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="c1955-113">Agrupación de conexiones</span><span class="sxs-lookup"><span data-stu-id="c1955-113">Connection Pooling</span></span>](connection-pooling.md)
- [<span data-ttu-id="c1955-114">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="c1955-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="c1955-115">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="c1955-115">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="c1955-116">Transacciones y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="c1955-116">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="c1955-117">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c1955-117">ADO.NET Overview</span></span>](ado-net-overview.md)
