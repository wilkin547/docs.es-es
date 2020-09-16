---
title: Mensajes dudosos en cola por segundo
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: 39118b515949e6ad4f6ff651037cd757a6dd9bbf
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552653"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="eee2b-102">Mensajes dudosos en cola por segundo</span><span class="sxs-lookup"><span data-stu-id="eee2b-102">Queued Poison Messages Per Second</span></span>
<span data-ttu-id="eee2b-103">Nombre de contador: Mensajes dudosos en cola por segundo.</span><span class="sxs-lookup"><span data-stu-id="eee2b-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="eee2b-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="eee2b-104">Description</span></span>  
 <span data-ttu-id="eee2b-105">Número de mensajes marcados como dudosos por el transporte en cola en este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="eee2b-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="eee2b-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="eee2b-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="eee2b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="eee2b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
