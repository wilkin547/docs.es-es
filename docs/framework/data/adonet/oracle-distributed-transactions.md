---
title: Transacciones distribuidas de Oracle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7c48232bb204b71c662a99bf210ad54fc3ee9eb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="82849-102">Transacciones distribuidas de Oracle</span><span class="sxs-lookup"><span data-stu-id="82849-102">Oracle Distributed Transactions</span></span>
<span data-ttu-id="82849-103">El objeto <xref:System.Data.OracleClient.OracleConnection> se inscribe automáticamente en una transacción distribuida si determina que hay una transacción activa.</span><span class="sxs-lookup"><span data-stu-id="82849-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="82849-104">La inscripción automática en transacciones tiene lugar cuando se abre la conexión o se recupera del grupo de conexiones.</span><span class="sxs-lookup"><span data-stu-id="82849-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="82849-105">Para deshabilitar la inscripción automática en transacciones existentes, especifique </span><span class="sxs-lookup"><span data-stu-id="82849-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```  
Enlist=false  
```  
  
 <span data-ttu-id="82849-106">como un parámetro de cadena de conexión de una <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="82849-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82849-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="82849-107">See Also</span></span>  
 [<span data-ttu-id="82849-108">Oracle y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="82849-108">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="82849-109">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="82849-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
