---
description: 'Más información sobre: mensajes en cola quitados por segundo'
title: Mensajes en cola quitados por segundo
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: e5959b76795514dec03d6ae4d08ac248994777fa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759554"
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="10900-103">Mensajes en cola quitados por segundo</span><span class="sxs-lookup"><span data-stu-id="10900-103">Queue Dropped Messages Per Second</span></span>

<span data-ttu-id="10900-104">Nombre de contador: Mensajes en cola quitados por segundo.</span><span class="sxs-lookup"><span data-stu-id="10900-104">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="10900-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="10900-105">Description</span></span>  

 <span data-ttu-id="10900-106">Número de mensajes quitados cada segundo por el transporte en cola en este servicio.</span><span class="sxs-lookup"><span data-stu-id="10900-106">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="10900-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="10900-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="10900-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="10900-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
