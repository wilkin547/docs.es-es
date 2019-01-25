---
title: 'Punto de conexión: Errores de llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 03fbdd83246fa811424f445823f705a3bef5697a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608042"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="28cb1-102">Punto de conexión: Errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="28cb1-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="28cb1-103">Nombre del contador: Errores de llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="28cb1-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="28cb1-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="28cb1-104">Description</span></span>  
 <span data-ttu-id="28cb1-105">Número de llamadas que tienen excepciones no controladas y son recibidas por este punto de conexión en un segundo.</span><span class="sxs-lookup"><span data-stu-id="28cb1-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="28cb1-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="28cb1-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="28cb1-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="28cb1-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="28cb1-108">Este contador se incrementa siempre que se produce una excepción no controlada en este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="28cb1-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28cb1-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="28cb1-109">See also</span></span>
- [<span data-ttu-id="28cb1-110">Especificación y gestión de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="28cb1-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
