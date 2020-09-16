---
title: 'Servicio: Llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: 5066108d8183502eeaec7c25186c00d9978261b7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546938"
---
# <a name="service-calls-per-second"></a><span data-ttu-id="7c9c9-102">Servicio: Llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="7c9c9-102">Service: Calls Per Second</span></span>
<span data-ttu-id="7c9c9-103">Nombre del contador: llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="7c9c9-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7c9c9-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c9c9-104">Description</span></span>  
 <span data-ttu-id="7c9c9-105">El número de llamadas por segundo a este servicio.</span><span class="sxs-lookup"><span data-stu-id="7c9c9-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="7c9c9-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="7c9c9-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="7c9c9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F), donde el numerador (N) representa el número de operaciones realizadas durante el último intervalo de muestra, el denominador (D) representa el número de pasos transcurridos desde el último intervalo de muestra y F representa la frecuencia de los pasos.</span><span class="sxs-lookup"><span data-stu-id="7c9c9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
