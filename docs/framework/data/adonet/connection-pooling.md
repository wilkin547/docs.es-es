---
title: "Agrupación de conexiones"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 5082adda3c03bfbc40eafb174513a39fe17a3da8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="connection-pooling"></a><span data-ttu-id="95f77-102">Agrupación de conexiones</span><span class="sxs-lookup"><span data-stu-id="95f77-102">Connection Pooling</span></span>
<span data-ttu-id="95f77-103">La conexión a un origen de datos puede ser un proceso largo.</span><span class="sxs-lookup"><span data-stu-id="95f77-103">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="95f77-104">Para minimizar el costo de abrir conexiones, ADO.NET emplea una técnica de optimización llamada *agrupación de conexiones*, que reduce el costo de abrir y cerrar las conexiones repetidamente.</span><span class="sxs-lookup"><span data-stu-id="95f77-104">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="95f77-105">Los proveedores de datos .NET Framework tratan de forma diferente la agrupación de conexiones.</span><span class="sxs-lookup"><span data-stu-id="95f77-105">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95f77-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="95f77-106">In This Section</span></span>  
 [<span data-ttu-id="95f77-107">Agrupación de conexiones de SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="95f77-107">SQL Server Connection Pooling (ADO.NET)</span></span>](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)  
 <span data-ttu-id="95f77-108">Proporciona información general acerca de la agrupación de conexiones y describe cómo funciona en [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95f77-108">Provides an overview of connection pooling and describes how connection pooling works in [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="95f77-109">Agrupación de conexiones de OLE DB, ODBC y Oracle</span><span class="sxs-lookup"><span data-stu-id="95f77-109">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="95f77-110">Describe la agrupación de conexiones en los proveedores de datos .NET Framework para OLE DB, ODBC y Oracle.</span><span class="sxs-lookup"><span data-stu-id="95f77-110">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95f77-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="95f77-111">See Also</span></span>  
 [<span data-ttu-id="95f77-112">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="95f77-112">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="95f77-113">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="95f77-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
