---
title: 'Servicio: flujo de transacciones por segundo'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: 158bd7e2f2f98e91215ef7351cf90493a2d3059d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236837"
---
# <a name="service-transactions-flowed-per-second"></a><span data-ttu-id="e3c7c-102">Servicio: flujo de transacciones por segundo</span><span class="sxs-lookup"><span data-stu-id="e3c7c-102">Service: Transactions Flowed Per Second</span></span>

<span data-ttu-id="e3c7c-103">Nombre del contador: flujo de transacciones por segundo.</span><span class="sxs-lookup"><span data-stu-id="e3c7c-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e3c7c-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3c7c-104">Description</span></span>  

 <span data-ttu-id="e3c7c-105">Número de transacciones que fluyen a las operaciones de este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="e3c7c-105">Number of transactions flowed to operations in this service in a second.</span></span>  
  
 <span data-ttu-id="e3c7c-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="e3c7c-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="e3c7c-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="e3c7c-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
