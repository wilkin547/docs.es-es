---
description: 'Más información acerca de: punto de conexión: llamadas por segundo'
title: 'Extremo: Llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
ms.openlocfilehash: 10e3cb892119999225abaa8b85ea59065650795d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759580"
---
# <a name="endpoint-calls-per-second"></a><span data-ttu-id="95f3a-103">Extremo: Llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="95f3a-103">Endpoint: Calls Per Second</span></span>

<span data-ttu-id="95f3a-104">Nombre del contador: llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="95f3a-104">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="95f3a-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="95f3a-105">Description</span></span>  

 <span data-ttu-id="95f3a-106">Número de llamadas a este punto de conexión en un segundo.</span><span class="sxs-lookup"><span data-stu-id="95f3a-106">Number of calls to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="95f3a-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="95f3a-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="95f3a-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="95f3a-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
