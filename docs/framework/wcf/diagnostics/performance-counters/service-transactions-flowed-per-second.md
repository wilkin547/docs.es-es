---
title: 'Servicio: flujo de transacciones por segundo'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: cb41abe74568c3e9641443b81fce3fb6eb6e41bf
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402773"
---
# <a name="service-transactions-flowed-per-second"></a><span data-ttu-id="b4c46-102">Servicio: flujo de transacciones por segundo</span><span class="sxs-lookup"><span data-stu-id="b4c46-102">Service: Transactions Flowed Per Second</span></span>
<span data-ttu-id="b4c46-103">Nombre del contador: flujo de transacciones por segundo.</span><span class="sxs-lookup"><span data-stu-id="b4c46-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b4c46-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4c46-104">Description</span></span>  
 <span data-ttu-id="b4c46-105">Número de transacciones que fluyen a las operaciones de este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="b4c46-105">Number of transactions flowed to operations in this service in a second.</span></span>  
  
 <span data-ttu-id="b4c46-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="b4c46-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b4c46-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b4c46-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
