---
title: Mensajes en cola rechazados por segundo
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: 096e2188b13d0fd5a9be35e5e6473107a58c5566
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916193"
---
# <a name="queued-rejected-messages-per-second"></a><span data-ttu-id="906d2-102">Mensajes en cola rechazados por segundo</span><span class="sxs-lookup"><span data-stu-id="906d2-102">Queued Rejected Messages Per Second</span></span>
<span data-ttu-id="906d2-103">Nombre del contador: Mensajes en cola rechazados por segundo.</span><span class="sxs-lookup"><span data-stu-id="906d2-103">Counter Name: Queued Messages Rejected Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="906d2-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="906d2-104">Description</span></span>  
 <span data-ttu-id="906d2-105">Número de mensajes rechazados cada segundo por el transporte en cola en este servicio.</span><span class="sxs-lookup"><span data-stu-id="906d2-105">Number of messages that are rejected by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="906d2-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="906d2-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="906d2-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="906d2-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
