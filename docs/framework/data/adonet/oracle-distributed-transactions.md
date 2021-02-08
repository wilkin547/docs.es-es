---
description: 'Más información acerca de: transacciones distribuidas de Oracle'
title: Transacciones distribuidas de Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: d0c41920f18e0f56ebdf57e3cb82cf829a59c450
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786178"
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="a42ee-103">Transacciones distribuidas de Oracle</span><span class="sxs-lookup"><span data-stu-id="a42ee-103">Oracle Distributed Transactions</span></span>

<span data-ttu-id="a42ee-104">El objeto <xref:System.Data.OracleClient.OracleConnection> se inscribe automáticamente en una transacción distribuida si determina que hay una transacción activa.</span><span class="sxs-lookup"><span data-stu-id="a42ee-104">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="a42ee-105">La inscripción automática en transacciones tiene lugar cuando se abre la conexión o se recupera del grupo de conexiones.</span><span class="sxs-lookup"><span data-stu-id="a42ee-105">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="a42ee-106">Para deshabilitar la inscripción automática en transacciones existentes, especifique </span><span class="sxs-lookup"><span data-stu-id="a42ee-106">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```csharp  
Enlist=false  
```  
  
 <span data-ttu-id="a42ee-107">como un parámetro de cadena de conexión de una <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="a42ee-107">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a42ee-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="a42ee-108">See also</span></span>

- [<span data-ttu-id="a42ee-109">Oracle y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a42ee-109">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="a42ee-110">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a42ee-110">ADO.NET Overview</span></span>](ado-net-overview.md)
