---
title: Transacciones distribuidas de Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 6f910f1dbbe448352c0edd5d1b80df659ac453d4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795146"
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="5e673-102">Transacciones distribuidas de Oracle</span><span class="sxs-lookup"><span data-stu-id="5e673-102">Oracle Distributed Transactions</span></span>
<span data-ttu-id="5e673-103">El objeto <xref:System.Data.OracleClient.OracleConnection> se inscribe automáticamente en una transacción distribuida si determina que hay una transacción activa.</span><span class="sxs-lookup"><span data-stu-id="5e673-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="5e673-104">La inscripción automática en transacciones tiene lugar cuando se abre la conexión o se recupera del grupo de conexiones.</span><span class="sxs-lookup"><span data-stu-id="5e673-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="5e673-105">Para deshabilitar la inscripción automática en transacciones existentes, especifique</span><span class="sxs-lookup"><span data-stu-id="5e673-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```  
Enlist=false  
```  
  
 <span data-ttu-id="5e673-106">como un parámetro de cadena de conexión de una <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="5e673-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e673-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e673-107">See also</span></span>

- [<span data-ttu-id="5e673-108">Oracle y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5e673-108">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="5e673-109">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5e673-109">ADO.NET Overview</span></span>](ado-net-overview.md)
