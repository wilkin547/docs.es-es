---
title: 'Servicio: Errores en llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: 5629c55cba6f21de24a1de7e8d38a9c08fcf4fb1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559114"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="66519-102">Servicio: Errores en llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="66519-102">Service: Calls Failed Per Second</span></span>
<span data-ttu-id="66519-103">Nombre del contador: Errores de llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="66519-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="66519-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="66519-104">Description</span></span>  
 <span data-ttu-id="66519-105">Número de llamadas que tienen excepciones no controladas y que son recibidas por este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="66519-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="66519-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="66519-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="66519-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="66519-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="66519-108">En código administrado, las excepciones se inician al producirse condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="66519-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="66519-109">En código administrado, las excepciones se inician al producirse condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="66519-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="66519-110">El contador se incrementa cada vez que hay una excepción no atendida en este servicio.</span><span class="sxs-lookup"><span data-stu-id="66519-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66519-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="66519-111">See also</span></span>

- [<span data-ttu-id="66519-112">Especificación y administración de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="66519-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
