---
title: 'Extremo: Llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
ms.openlocfilehash: 3c9f9882be935474ec187e2829e8e1e58b091afa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253159"
---
# <a name="endpoint-calls-per-second"></a><span data-ttu-id="bd5a5-102">Extremo: Llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="bd5a5-102">Endpoint: Calls Per Second</span></span>

<span data-ttu-id="bd5a5-103">Nombre del contador: llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="bd5a5-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bd5a5-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd5a5-104">Description</span></span>  

 <span data-ttu-id="bd5a5-105">Número de llamadas a este punto de conexión en un segundo.</span><span class="sxs-lookup"><span data-stu-id="bd5a5-105">Number of calls to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="bd5a5-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="bd5a5-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="bd5a5-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="bd5a5-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
