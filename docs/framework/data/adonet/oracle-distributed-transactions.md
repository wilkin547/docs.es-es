---
title: Transacciones distribuidas de Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 0e9dcb30eb1962071d7154d4bbf929871c8a12d2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765206"
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="2c4b3-102">Transacciones distribuidas de Oracle</span><span class="sxs-lookup"><span data-stu-id="2c4b3-102">Oracle Distributed Transactions</span></span>
<span data-ttu-id="2c4b3-103">El objeto <xref:System.Data.OracleClient.OracleConnection> se inscribe automáticamente en una transacción distribuida si determina que hay una transacción activa.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="2c4b3-104">La inscripción automática en transacciones tiene lugar cuando se abre la conexión o se recupera del grupo de conexiones.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="2c4b3-105">Para deshabilitar la inscripción automática en transacciones existentes, especifique </span><span class="sxs-lookup"><span data-stu-id="2c4b3-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```  
Enlist=false  
```  
  
 <span data-ttu-id="2c4b3-106">como un parámetro de cadena de conexión de una <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c4b3-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c4b3-107">See Also</span></span>  
 [<span data-ttu-id="2c4b3-108">Oracle y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2c4b3-108">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="2c4b3-109">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="2c4b3-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
