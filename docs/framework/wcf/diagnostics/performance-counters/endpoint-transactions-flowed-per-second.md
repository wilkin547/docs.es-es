---
title: 'punto de conexión: Flujo de transacciones por segundo'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 39458dcb6ac033fd5084b5f2e760e0e26c345da7
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163558"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="4f5b3-102">punto de conexión: Flujo de transacciones por segundo</span><span class="sxs-lookup"><span data-stu-id="4f5b3-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="4f5b3-103">Nombre del contador: flujo de transacciones por segundo.</span><span class="sxs-lookup"><span data-stu-id="4f5b3-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4f5b3-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f5b3-104">Description</span></span>  
 <span data-ttu-id="4f5b3-105">Número de transacciones de flujo a las operaciones en este extremo en un segundo.</span><span class="sxs-lookup"><span data-stu-id="4f5b3-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="4f5b3-106">Este contador se incrementa siempre que se encuentra un id. de transacción en un mensaje enviado al extremo.</span><span class="sxs-lookup"><span data-stu-id="4f5b3-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="4f5b3-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="4f5b3-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="4f5b3-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="4f5b3-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
