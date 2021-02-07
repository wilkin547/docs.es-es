---
description: 'Más información acerca de: punto de conexión: errores de llamadas por segundo'
title: 'punto de conexión: Errores en llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 262f0fdf0750e8fdb179d41d1a99788784270023
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759645"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="5d6a0-103">punto de conexión: Errores en llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="5d6a0-103">Endpoint: Calls Failed Per Second</span></span>

<span data-ttu-id="5d6a0-104">Nombre del contador: Errores de llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-104">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5d6a0-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d6a0-105">Description</span></span>  

 <span data-ttu-id="5d6a0-106">Número de llamadas que tienen excepciones no controladas y son recibidas por este punto de conexión en un segundo.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-106">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="5d6a0-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="5d6a0-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="5d6a0-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="5d6a0-109">Este contador se incrementa siempre que se produce una excepción no controlada en este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="5d6a0-109">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d6a0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d6a0-110">See also</span></span>

- [<span data-ttu-id="5d6a0-111">Especificación y administración de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="5d6a0-111">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
