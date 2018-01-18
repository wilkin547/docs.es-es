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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1df18730d3a4428f245fe4222dafec0eaf6c08a5
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="bbe14-102">Conectarse a un origen de datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bbe14-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="bbe14-103">En ADO.NET se utiliza un **conexión** objeto para conectarse a un origen de datos específico mediante el suministro de información de autenticación necesaria en una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="bbe14-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="bbe14-104">El **conexión** objeto utilizado depende del tipo de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="bbe14-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="bbe14-105">Cada proveedor de datos .NET Framework incluye un objeto <xref:System.Data.Common.DbConnection>: el proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbConnection>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlConnection>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcConnection> y el proveedor de datos .NET Framework para Oracle incluye un objeto <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="bbe14-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bbe14-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bbe14-106">In This Section</span></span>  
 [<span data-ttu-id="bbe14-107">Establecimiento de la conexión</span><span class="sxs-lookup"><span data-stu-id="bbe14-107">Establishing the Connection</span></span>](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 <span data-ttu-id="bbe14-108">Describe cómo usar un **conexión** objeto que se va a establecer una conexión con un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="bbe14-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="bbe14-109">Eventos de conexión</span><span class="sxs-lookup"><span data-stu-id="bbe14-109">Connection Events</span></span>](../../../../docs/framework/data/adonet/connection-events.md)  
 <span data-ttu-id="bbe14-110">Describe cómo usar un **InfoMessage** eventos para recuperar mensajes informativos de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="bbe14-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe14-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbe14-111">See Also</span></span>  
 [<span data-ttu-id="bbe14-112">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="bbe14-112">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="bbe14-113">Agrupación de conexiones</span><span class="sxs-lookup"><span data-stu-id="bbe14-113">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [<span data-ttu-id="bbe14-114">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="bbe14-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="bbe14-115">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="bbe14-115">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="bbe14-116">Transacciones y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="bbe14-116">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="bbe14-117">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="bbe14-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
