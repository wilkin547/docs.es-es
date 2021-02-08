---
description: 'Más información acerca de: servicio: errores de llamadas por segundo'
title: 'Servicio: Errores en llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: b271d5076d0f0c89c4d33b124e0184584795466a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803365"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="2e29e-103">Servicio: Errores en llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="2e29e-103">Service: Calls Failed Per Second</span></span>

<span data-ttu-id="2e29e-104">Nombre del contador: Errores de llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="2e29e-104">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2e29e-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e29e-105">Description</span></span>  

 <span data-ttu-id="2e29e-106">Número de llamadas que tienen excepciones no controladas y que son recibidas por este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="2e29e-106">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="2e29e-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="2e29e-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="2e29e-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="2e29e-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="2e29e-109">En código administrado, las excepciones se inician al producirse condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="2e29e-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="2e29e-110">En código administrado, las excepciones se inician al producirse condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="2e29e-110">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="2e29e-111">El contador se incrementa cada vez que hay una excepción no atendida en este servicio.</span><span class="sxs-lookup"><span data-stu-id="2e29e-111">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e29e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e29e-112">See also</span></span>

- [<span data-ttu-id="2e29e-113">Especificación y administración de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="2e29e-113">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
