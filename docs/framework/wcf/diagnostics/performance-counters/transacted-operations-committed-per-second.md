---
title: Operaciones de transacción confirmadas por segundo
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: b81146516413c4afa9baf9a533797f0867a1b20d
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163857"
---
# <a name="transacted-operations-committed-per-second"></a><span data-ttu-id="e6e5b-102">Operaciones de transacción confirmadas por segundo</span><span class="sxs-lookup"><span data-stu-id="e6e5b-102">Transacted Operations Committed Per Second</span></span>
<span data-ttu-id="e6e5b-103">Nombre del contador: Operaciones de transacción confirmadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-103">Counter Name: Transacted Operations Committed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e6e5b-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6e5b-104">Description</span></span>  
 <span data-ttu-id="e6e5b-105">Número de operaciones transaccionales confirmadas en este servicio cada segundo.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-105">Number of transactional operations that have been committed in this service in a second.</span></span>  
  
 <span data-ttu-id="e6e5b-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="e6e5b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="e6e5b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
