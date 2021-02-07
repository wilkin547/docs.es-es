---
description: Más información acerca de cómo conectarse a un origen de datos en ADO.NET
title: Conectar con un origen de datos
deescription: Learn about Connection objects, used to connect to data sources in ADO.NET. The Connection object you choose depends on the type of data source.
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 0bf66b9dc609a704cf89380e2376f50197e047a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663890"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="6123e-103">Conectarse a un origen de datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6123e-103">Connecting to a Data Source in ADO.NET</span></span>

<span data-ttu-id="6123e-104">En ADO.NET, se usa un objeto de **conexión** para conectarse a un origen de datos específico proporcionando la información de autenticación necesaria en una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="6123e-104">In ADO.NET, you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="6123e-105">El objeto **Connection** utilizado depende del tipo de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="6123e-105">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="6123e-106">Cada proveedor de datos .NET Framework incluye un objeto <xref:System.Data.Common.DbConnection>: el proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbConnection>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlConnection>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcConnection> y el proveedor de datos .NET Framework para Oracle incluye un objeto <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="6123e-106">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6123e-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6123e-107">In This Section</span></span>  

 <span data-ttu-id="6123e-108">[Establecimiento de la conexión](establishing-the-connection.md)</span><span class="sxs-lookup"><span data-stu-id="6123e-108">[Establishing the Connection](establishing-the-connection.md)</span></span>\
 <span data-ttu-id="6123e-109">Describe cómo se establece una conexión con un origen de datos mediante un objeto **Connection**.</span><span class="sxs-lookup"><span data-stu-id="6123e-109">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 <span data-ttu-id="6123e-110">[Eventos de conexión](connection-events.md)</span><span class="sxs-lookup"><span data-stu-id="6123e-110">[Connection Events](connection-events.md)</span></span>\
 <span data-ttu-id="6123e-111">Describe la forma de usar un evento **InfoMessage** para recuperar mensajes informativos de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="6123e-111">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6123e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="6123e-112">See also</span></span>

- [<span data-ttu-id="6123e-113">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="6123e-113">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="6123e-114">Agrupar conexiones</span><span class="sxs-lookup"><span data-stu-id="6123e-114">Connection Pooling</span></span>](connection-pooling.md)
- [<span data-ttu-id="6123e-115">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="6123e-115">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="6123e-116">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="6123e-116">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="6123e-117">Transacciones y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="6123e-117">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="6123e-118">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6123e-118">ADO.NET Overview</span></span>](ado-net-overview.md)
