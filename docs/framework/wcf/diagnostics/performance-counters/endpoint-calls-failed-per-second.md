---
title: 'punto de conexión: Errores en llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 0aeafa3d273ae22d9bbfe5e3edbac80c6e4851bd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271258"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="1e623-102">punto de conexión: Errores en llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="1e623-102">Endpoint: Calls Failed Per Second</span></span>

<span data-ttu-id="1e623-103">Nombre del contador: Errores de llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="1e623-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1e623-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e623-104">Description</span></span>  

 <span data-ttu-id="1e623-105">Número de llamadas que tienen excepciones no controladas y son recibidas por este punto de conexión en un segundo.</span><span class="sxs-lookup"><span data-stu-id="1e623-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="1e623-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="1e623-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="1e623-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="1e623-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="1e623-108">Este contador se incrementa siempre que se produce una excepción no controlada en este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="1e623-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e623-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e623-109">See also</span></span>

- [<span data-ttu-id="1e623-110">Especificación y administración de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="1e623-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
