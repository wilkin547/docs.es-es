---
title: Mensajes de mensajería de confianza quitados por segundo
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: 7722b32f99b302c5c272e095033879c9e04c7ee1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43542846"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="694ee-102">Mensajes de mensajería de confianza quitados por segundo</span><span class="sxs-lookup"><span data-stu-id="694ee-102">Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="694ee-103">Nombre de contador: sesiones de mensajería de confianza quitadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="694ee-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="694ee-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="694ee-104">Description</span></span>  
 <span data-ttu-id="694ee-105">Número total de mensajes de mensajería de confianza que han sido quitados en este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="694ee-105">Total number of reliable messaging messages that have been dropped in this service in a second.</span></span>  
  
 <span data-ttu-id="694ee-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="694ee-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="694ee-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="694ee-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
