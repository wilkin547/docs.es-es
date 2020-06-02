---
title: Agrupar conexiones
description: Obtenga información sobre la agrupación de conexiones, una técnica de optimización que ADO.NET usa para minimizar el costo de abrir conexiones a orígenes de datos.
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: b8f89dfda7edbde14dbb5945f10f2284ac43c3d8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287095"
---
# <a name="connection-pooling"></a><span data-ttu-id="68d4f-103">Agrupar conexiones</span><span class="sxs-lookup"><span data-stu-id="68d4f-103">Connection Pooling</span></span>
<span data-ttu-id="68d4f-104">La conexión a un origen de datos puede ser un proceso largo.</span><span class="sxs-lookup"><span data-stu-id="68d4f-104">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="68d4f-105">Para minimizar el costo de la apertura de conexiones, ADO.NET usa una técnica de optimización denominada *agrupación*de conexiones, lo que minimiza el costo de abrir y cerrar conexiones repetidas veces.</span><span class="sxs-lookup"><span data-stu-id="68d4f-105">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="68d4f-106">Los proveedores de datos .NET Framework tratan de forma diferente la agrupación de conexiones.</span><span class="sxs-lookup"><span data-stu-id="68d4f-106">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68d4f-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="68d4f-107">In This Section</span></span>  
 [<span data-ttu-id="68d4f-108">Agrupación de conexiones de SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="68d4f-108">SQL Server Connection Pooling (ADO.NET)</span></span>](sql-server-connection-pooling.md)  
 <span data-ttu-id="68d4f-109">Proporciona información general sobre la agrupación de conexiones y describe cómo funciona la agrupación de conexiones en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="68d4f-109">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="68d4f-110">Agrupación de conexiones de OLE DB, ODBC y Oracle</span><span class="sxs-lookup"><span data-stu-id="68d4f-110">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="68d4f-111">Describe la agrupación de conexiones en los proveedores de datos .NET Framework para OLE DB, ODBC y Oracle.</span><span class="sxs-lookup"><span data-stu-id="68d4f-111">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68d4f-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="68d4f-112">See also</span></span>

- [<span data-ttu-id="68d4f-113">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="68d4f-113">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="68d4f-114">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="68d4f-114">ADO.NET Overview</span></span>](ado-net-overview.md)
