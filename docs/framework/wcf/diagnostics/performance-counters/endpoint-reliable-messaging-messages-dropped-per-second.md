---
title: 'Extremo: mensajes de mensajería de confianza quitados por segundo'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: 7dc52caea0233953dd72e77e4d662083f4a370e4
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76164052"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="78bb0-102">Extremo: mensajes de mensajería de confianza quitados por segundo</span><span class="sxs-lookup"><span data-stu-id="78bb0-102">Endpoint: Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="78bb0-103">Nombre de contador: sesiones de mensajería de confianza quitadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="78bb0-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="78bb0-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="78bb0-104">Description</span></span>  
 <span data-ttu-id="78bb0-105">Número total de mensajes de mensajería de confianza quitados en este punto de conexión en un segundo.</span><span class="sxs-lookup"><span data-stu-id="78bb0-105">Total number of reliable messaging messages that have been dropped at this endpoint in a second.</span></span>  
  
 <span data-ttu-id="78bb0-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="78bb0-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="78bb0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="78bb0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
