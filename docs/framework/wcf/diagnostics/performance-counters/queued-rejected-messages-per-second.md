---
description: 'Más información sobre: mensajes rechazados en cola por segundo'
title: Mensajes en cola rechazados por segundo
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: d0d227a26a49921449786d2c9f885fac13a82bde
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99744076"
---
# <a name="queued-rejected-messages-per-second"></a><span data-ttu-id="ee827-103">Mensajes en cola rechazados por segundo</span><span class="sxs-lookup"><span data-stu-id="ee827-103">Queued Rejected Messages Per Second</span></span>

<span data-ttu-id="ee827-104">Nombre de contador: mensajes en cola rechazados por segundo.</span><span class="sxs-lookup"><span data-stu-id="ee827-104">Counter Name: Queued Messages Rejected Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ee827-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee827-105">Description</span></span>  

 <span data-ttu-id="ee827-106">Número de mensajes rechazados cada segundo por el transporte en cola en este servicio.</span><span class="sxs-lookup"><span data-stu-id="ee827-106">Number of messages that are rejected by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="ee827-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="ee827-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="ee827-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="ee827-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
