---
title: Mensajes en cola rechazados por segundo
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: 805b4f5d1e7882f38cfcc76ad63451d735389d5f
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163974"
---
# <a name="queued-rejected-messages-per-second"></a><span data-ttu-id="13632-102">Mensajes en cola rechazados por segundo</span><span class="sxs-lookup"><span data-stu-id="13632-102">Queued Rejected Messages Per Second</span></span>
<span data-ttu-id="13632-103">Nombre de contador: mensajes en cola rechazados por segundo.</span><span class="sxs-lookup"><span data-stu-id="13632-103">Counter Name: Queued Messages Rejected Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="13632-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="13632-104">Description</span></span>  
 <span data-ttu-id="13632-105">Número de mensajes rechazados cada segundo por el transporte en cola en este servicio.</span><span class="sxs-lookup"><span data-stu-id="13632-105">Number of messages that are rejected by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="13632-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="13632-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="13632-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="13632-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
