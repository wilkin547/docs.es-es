---
title: 'Punto de conexión: Errores de llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 52419f45adde768d19d6b46642d52ad0a1844197
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100033"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="ae618-102">Punto de conexión: Errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="ae618-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="ae618-103">Nombre del contador: Errores de llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="ae618-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ae618-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae618-104">Description</span></span>  
 <span data-ttu-id="ae618-105">Número de llamadas que tienen excepciones no controladas y son recibidas por este punto de conexión en un segundo.</span><span class="sxs-lookup"><span data-stu-id="ae618-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="ae618-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="ae618-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="ae618-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="ae618-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="ae618-108">Este contador se incrementa siempre que se produce una excepción no controlada en este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ae618-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae618-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae618-109">See also</span></span>

- [<span data-ttu-id="ae618-110">Especificación y administración de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="ae618-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
