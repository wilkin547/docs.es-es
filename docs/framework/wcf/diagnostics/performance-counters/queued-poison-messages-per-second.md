---
title: Mensajes dudosos en cola por segundo
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: d4c921b105dfd1c1a364d2c86f54ab920078dd4a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509344"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="82c6d-102">Mensajes dudosos en cola por segundo</span><span class="sxs-lookup"><span data-stu-id="82c6d-102">Queued Poison Messages Per Second</span></span>
<span data-ttu-id="82c6d-103">Nombre de contador: Mensajes dudosos en cola por segundo.</span><span class="sxs-lookup"><span data-stu-id="82c6d-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="82c6d-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="82c6d-104">Description</span></span>  
 <span data-ttu-id="82c6d-105">Número de mensajes marcados como dudosos por el transporte en cola en este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="82c6d-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="82c6d-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="82c6d-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="82c6d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="82c6d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
