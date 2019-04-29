---
title: 'Punto de conexión: Mensajes de mensajería de confianza quitados por segundo'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: 8f935bee06d175ce454bd7f58a1afbbe9ab505ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797207"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="ad12c-102">Punto de conexión: Mensajes de mensajería de confianza quitados por segundo</span><span class="sxs-lookup"><span data-stu-id="ad12c-102">Endpoint: Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="ad12c-103">Nombre del contador: Las sesiones de mensajes de confianza quitan por segundo.</span><span class="sxs-lookup"><span data-stu-id="ad12c-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ad12c-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad12c-104">Description</span></span>  
 <span data-ttu-id="ad12c-105">Número total de mensajes de mensajería de confianza quitados en este punto de conexión en un segundo.</span><span class="sxs-lookup"><span data-stu-id="ad12c-105">Total number of reliable messaging messages that have been dropped at this endpoint in a second.</span></span>  
  
 <span data-ttu-id="ad12c-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="ad12c-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="ad12c-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="ad12c-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
