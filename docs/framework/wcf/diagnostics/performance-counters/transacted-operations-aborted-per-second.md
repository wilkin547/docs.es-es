---
description: 'Más información acerca de: operaciones de transacción anuladas por segundo'
title: Operaciones de transacción anuladas por segundo
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: de130c18e065e48ed7ac18442b2bc5f82c2f6861
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771202"
---
# <a name="transacted-operations-aborted-per-second"></a><span data-ttu-id="b9ccc-103">Operaciones de transacción anuladas por segundo</span><span class="sxs-lookup"><span data-stu-id="b9ccc-103">Transacted Operations Aborted Per Second</span></span>

<span data-ttu-id="b9ccc-104">Nombre del contador: operaciones de transacción anuladas por segundo.</span><span class="sxs-lookup"><span data-stu-id="b9ccc-104">Counter Name: Transacted Operations Aborted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b9ccc-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9ccc-105">Description</span></span>  

 <span data-ttu-id="b9ccc-106">Número de operaciones transaccionales anuladas en este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="b9ccc-106">Number of transactional operations that have been aborted in this service in a second.</span></span>  
  
 <span data-ttu-id="b9ccc-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="b9ccc-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b9ccc-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b9ccc-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
