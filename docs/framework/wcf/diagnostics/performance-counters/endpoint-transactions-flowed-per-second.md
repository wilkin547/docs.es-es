---
description: 'Más información acerca de: punto de conexión: flujo de transacciones por segundo'
title: 'punto de conexión: Flujo de transacciones por segundo'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 96a122b97bce703b0a0e00c6e74f72c980253652
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655362"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="46dcd-103">punto de conexión: Flujo de transacciones por segundo</span><span class="sxs-lookup"><span data-stu-id="46dcd-103">Endpoint: Transactions Flowed Per Second</span></span>

<span data-ttu-id="46dcd-104">Nombre del contador: flujo de transacciones por segundo.</span><span class="sxs-lookup"><span data-stu-id="46dcd-104">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="46dcd-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="46dcd-105">Description</span></span>  

 <span data-ttu-id="46dcd-106">Número de transacciones de flujo a las operaciones en este extremo en un segundo.</span><span class="sxs-lookup"><span data-stu-id="46dcd-106">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="46dcd-107">Este contador se incrementa siempre que se encuentra un id. de transacción en un mensaje enviado al extremo.</span><span class="sxs-lookup"><span data-stu-id="46dcd-107">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="46dcd-108">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="46dcd-108">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="46dcd-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="46dcd-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
