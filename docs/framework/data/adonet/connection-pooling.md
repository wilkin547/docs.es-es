---
title: Agrupar conexiones
description: Obtenga información sobre la agrupación de conexiones, una técnica de optimización que ADO.NET usa para minimizar el costo de abrir conexiones a orígenes de datos.
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: f16b3ba733cce4a1efe72e3f4eee48a431a96fb7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198722"
---
# <a name="connection-pooling"></a><span data-ttu-id="c942d-103">Agrupar conexiones</span><span class="sxs-lookup"><span data-stu-id="c942d-103">Connection Pooling</span></span>

<span data-ttu-id="c942d-104">La conexión a un origen de datos puede ser un proceso largo.</span><span class="sxs-lookup"><span data-stu-id="c942d-104">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="c942d-105">Para minimizar el costo de la apertura de conexiones, ADO.NET usa una técnica de optimización denominada *agrupación*de conexiones, lo que minimiza el costo de abrir y cerrar conexiones repetidas veces.</span><span class="sxs-lookup"><span data-stu-id="c942d-105">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="c942d-106">Los proveedores de datos .NET Framework tratan de forma diferente la agrupación de conexiones.</span><span class="sxs-lookup"><span data-stu-id="c942d-106">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c942d-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c942d-107">In This Section</span></span>  

 [<span data-ttu-id="c942d-108">Agrupación de conexiones de SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="c942d-108">SQL Server Connection Pooling (ADO.NET)</span></span>](sql-server-connection-pooling.md)  
 <span data-ttu-id="c942d-109">Proporciona información general sobre la agrupación de conexiones y describe cómo funciona la agrupación de conexiones en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c942d-109">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="c942d-110">Agrupación de conexiones de OLE DB, ODBC y Oracle</span><span class="sxs-lookup"><span data-stu-id="c942d-110">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="c942d-111">Describe la agrupación de conexiones en los proveedores de datos .NET Framework para OLE DB, ODBC y Oracle.</span><span class="sxs-lookup"><span data-stu-id="c942d-111">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c942d-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c942d-112">See also</span></span>

- [<span data-ttu-id="c942d-113">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c942d-113">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="c942d-114">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c942d-114">ADO.NET Overview</span></span>](ado-net-overview.md)
