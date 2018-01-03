---
title: Conectarse a un origen de datos en ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 01a7342d6e081bec88aeef2c55461be2d936e4a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="8be88-102">Conectarse a un origen de datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8be88-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="8be88-103">En ADO.NET se utiliza un **conexión** objeto para conectarse a un origen de datos específico mediante el suministro de información de autenticación necesaria en una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="8be88-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="8be88-104">El **conexión** objeto utilizado depende del tipo de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="8be88-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="8be88-105">Cada proveedor de datos .NET Framework incluye un objeto <xref:System.Data.Common.DbConnection>: el proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbConnection>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlConnection>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcConnection> y el proveedor de datos .NET Framework para Oracle incluye un objeto <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="8be88-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8be88-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8be88-106">In This Section</span></span>  
 [<span data-ttu-id="8be88-107">Establecimiento de la conexión</span><span class="sxs-lookup"><span data-stu-id="8be88-107">Establishing the Connection</span></span>](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 <span data-ttu-id="8be88-108">Describe cómo usar un **conexión** objeto que se va a establecer una conexión con un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="8be88-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="8be88-109">Eventos de conexión</span><span class="sxs-lookup"><span data-stu-id="8be88-109">Connection Events</span></span>](../../../../docs/framework/data/adonet/connection-events.md)  
 <span data-ttu-id="8be88-110">Describe cómo usar un **InfoMessage** eventos para recuperar mensajes informativos de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="8be88-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be88-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="8be88-111">See Also</span></span>  
 [<span data-ttu-id="8be88-112">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="8be88-112">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="8be88-113">Agrupación de conexiones</span><span class="sxs-lookup"><span data-stu-id="8be88-113">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [<span data-ttu-id="8be88-114">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="8be88-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="8be88-115">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="8be88-115">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="8be88-116">Transacciones y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="8be88-116">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="8be88-117">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="8be88-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
