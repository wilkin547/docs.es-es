---
title: 'Servicio: Errores en llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: c97e4b0c6c2c71756a9bed7b1a2359ad0c118a98
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252977"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="287f0-102">Servicio: Errores en llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="287f0-102">Service: Calls Failed Per Second</span></span>

<span data-ttu-id="287f0-103">Nombre del contador: Errores de llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="287f0-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="287f0-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="287f0-104">Description</span></span>  

 <span data-ttu-id="287f0-105">Número de llamadas que tienen excepciones no controladas y que son recibidas por este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="287f0-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="287f0-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="287f0-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="287f0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="287f0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="287f0-108">En código administrado, las excepciones se inician al producirse condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="287f0-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="287f0-109">En código administrado, las excepciones se inician al producirse condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="287f0-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="287f0-110">El contador se incrementa cada vez que hay una excepción no atendida en este servicio.</span><span class="sxs-lookup"><span data-stu-id="287f0-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="287f0-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="287f0-111">See also</span></span>

- [<span data-ttu-id="287f0-112">Especificación y administración de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="287f0-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
