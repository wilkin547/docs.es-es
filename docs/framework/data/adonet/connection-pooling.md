---
title: Agrupación de conexiones
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: 4cba53993489f51ed39ac52bff4fa252beb9aafd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180458"
---
# <a name="connection-pooling"></a><span data-ttu-id="9093a-102">Agrupación de conexiones</span><span class="sxs-lookup"><span data-stu-id="9093a-102">Connection Pooling</span></span>
<span data-ttu-id="9093a-103">La conexión a un origen de datos puede ser un proceso largo.</span><span class="sxs-lookup"><span data-stu-id="9093a-103">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="9093a-104">Para minimizar el costo de abrir conexiones, ADO.NET emplea una técnica de optimización llamada *agrupación de conexiones*, que reduce el costo de abrir y cerrar conexiones repetidas veces.</span><span class="sxs-lookup"><span data-stu-id="9093a-104">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="9093a-105">Los proveedores de datos .NET Framework tratan de forma diferente la agrupación de conexiones.</span><span class="sxs-lookup"><span data-stu-id="9093a-105">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9093a-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9093a-106">In This Section</span></span>  
 [<span data-ttu-id="9093a-107">Agrupación de conexiones de SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="9093a-107">SQL Server Connection Pooling (ADO.NET)</span></span>](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)  
 <span data-ttu-id="9093a-108">Proporciona información general de la agrupación de conexiones y describe cómo funciona la agrupación de conexiones en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9093a-108">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="9093a-109">Agrupación de conexiones de OLE DB, ODBC y Oracle</span><span class="sxs-lookup"><span data-stu-id="9093a-109">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="9093a-110">Describe la agrupación de conexiones en los proveedores de datos .NET Framework para OLE DB, ODBC y Oracle.</span><span class="sxs-lookup"><span data-stu-id="9093a-110">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9093a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="9093a-111">See also</span></span>

- [<span data-ttu-id="9093a-112">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9093a-112">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="9093a-113">Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="9093a-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
