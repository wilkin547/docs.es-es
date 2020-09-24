---
title: Transacciones distribuidas de Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: a21134c3283d3d9d8d7660eecaaf74d60ecf6662
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166526"
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="918b9-102">Transacciones distribuidas de Oracle</span><span class="sxs-lookup"><span data-stu-id="918b9-102">Oracle Distributed Transactions</span></span>

<span data-ttu-id="918b9-103">El objeto <xref:System.Data.OracleClient.OracleConnection> se inscribe automáticamente en una transacción distribuida si determina que hay una transacción activa.</span><span class="sxs-lookup"><span data-stu-id="918b9-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="918b9-104">La inscripción automática en transacciones tiene lugar cuando se abre la conexión o se recupera del grupo de conexiones.</span><span class="sxs-lookup"><span data-stu-id="918b9-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="918b9-105">Para deshabilitar la inscripción automática en transacciones existentes, especifique </span><span class="sxs-lookup"><span data-stu-id="918b9-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```csharp  
Enlist=false  
```  
  
 <span data-ttu-id="918b9-106">como un parámetro de cadena de conexión de una <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="918b9-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="918b9-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="918b9-107">See also</span></span>

- [<span data-ttu-id="918b9-108">Oracle y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="918b9-108">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="918b9-109">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="918b9-109">ADO.NET Overview</span></span>](ado-net-overview.md)
