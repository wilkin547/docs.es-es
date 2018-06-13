---
title: Mensajes dudosos en cola por segundo
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: 6407cce120f5d534f88a12591ea2ad09bb5130d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473264"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="70a97-102">Mensajes dudosos en cola por segundo</span><span class="sxs-lookup"><span data-stu-id="70a97-102">Queued Poison Messages Per Second</span></span>
<span data-ttu-id="70a97-103">Nombre de contador: Mensajes dudosos en cola por segundo.</span><span class="sxs-lookup"><span data-stu-id="70a97-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="70a97-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="70a97-104">Description</span></span>  
 <span data-ttu-id="70a97-105">Número de mensajes marcados como dudosos por el transporte en cola en este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="70a97-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="70a97-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="70a97-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="70a97-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="70a97-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
