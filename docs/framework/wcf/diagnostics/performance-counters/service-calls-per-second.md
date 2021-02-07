---
description: 'Más información acerca de: servicio: llamadas por segundo'
title: 'Servicio: Llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: f6e21f5f1c7a0d5d4ceeb11f954ebbc95f66a3ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99744037"
---
# <a name="service-calls-per-second"></a><span data-ttu-id="60680-103">Servicio: Llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="60680-103">Service: Calls Per Second</span></span>

<span data-ttu-id="60680-104">Nombre del contador: llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="60680-104">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="60680-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="60680-105">Description</span></span>  

 <span data-ttu-id="60680-106">El número de llamadas por segundo a este servicio.</span><span class="sxs-lookup"><span data-stu-id="60680-106">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="60680-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="60680-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="60680-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F), donde el numerador (N) representa el número de operaciones realizadas durante el último intervalo de muestra, el denominador (D) representa el número de pasos transcurridos desde el último intervalo de muestra y F representa la frecuencia de los pasos.</span><span class="sxs-lookup"><span data-stu-id="60680-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
