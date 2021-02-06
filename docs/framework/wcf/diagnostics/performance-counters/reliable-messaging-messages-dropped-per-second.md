---
description: 'Más información sobre: mensajes de mensajería de confianza quitados por segundo'
title: Mensajes de mensajería de confianza quitados por segundo
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: 6132316f100cecdba357a6da071e23de8c9a2181
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655115"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="bb421-103">Mensajes de mensajería de confianza quitados por segundo</span><span class="sxs-lookup"><span data-stu-id="bb421-103">Reliable Messaging Messages Dropped Per Second</span></span>

<span data-ttu-id="bb421-104">Nombre de contador: sesiones de mensajería de confianza quitadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="bb421-104">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bb421-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb421-105">Description</span></span>  

 <span data-ttu-id="bb421-106">Número total de mensajes de mensajería de confianza que han sido quitados en este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="bb421-106">Total number of reliable messaging messages that have been dropped in this service in a second.</span></span>  
  
 <span data-ttu-id="bb421-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="bb421-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="bb421-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="bb421-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
