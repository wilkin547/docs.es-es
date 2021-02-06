---
description: 'Más información acerca de: operaciones de transacción confirmadas por segundo'
title: Operaciones de transacción confirmadas por segundo
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: 019906cccc527a032d91eb20328eddbb6d9aada8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655089"
---
# <a name="transacted-operations-committed-per-second"></a><span data-ttu-id="14203-103">Operaciones de transacción confirmadas por segundo</span><span class="sxs-lookup"><span data-stu-id="14203-103">Transacted Operations Committed Per Second</span></span>

<span data-ttu-id="14203-104">Nombre del contador: Operaciones de transacción confirmadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="14203-104">Counter Name: Transacted Operations Committed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="14203-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="14203-105">Description</span></span>  

 <span data-ttu-id="14203-106">Número de operaciones transaccionales confirmadas en este servicio cada segundo.</span><span class="sxs-lookup"><span data-stu-id="14203-106">Number of transactional operations that have been committed in this service in a second.</span></span>  
  
 <span data-ttu-id="14203-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="14203-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="14203-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="14203-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
