---
description: 'Más información acerca de: punto de conexión: mensajes de mensajería de confianza quitados por segundo'
title: 'Extremo: mensajes de mensajería de confianza quitados por segundo'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: 257ea74aeb23ef8962ce8910dee635b83f76d960
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735886"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="75e90-103">Extremo: mensajes de mensajería de confianza quitados por segundo</span><span class="sxs-lookup"><span data-stu-id="75e90-103">Endpoint: Reliable Messaging Messages Dropped Per Second</span></span>

<span data-ttu-id="75e90-104">Nombre de contador: sesiones de mensajería de confianza quitadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="75e90-104">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="75e90-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="75e90-105">Description</span></span>  

 <span data-ttu-id="75e90-106">Número total de mensajes de mensajería de confianza quitados en este punto de conexión en un segundo.</span><span class="sxs-lookup"><span data-stu-id="75e90-106">Total number of reliable messaging messages that have been dropped at this endpoint in a second.</span></span>  
  
 <span data-ttu-id="75e90-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="75e90-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="75e90-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="75e90-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
