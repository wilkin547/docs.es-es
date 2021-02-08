---
description: 'Más información sobre: operaciones de transacción dudosas por segundo'
title: Operaciones de transacción dudosas por segundo
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: e4f8b8c9db1c92ea4348763cdc4a633f058dbaf2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771098"
---
# <a name="transacted-operations-in-doubt-per-second"></a><span data-ttu-id="6aaf5-103">Operaciones de transacción dudosas por segundo</span><span class="sxs-lookup"><span data-stu-id="6aaf5-103">Transacted Operations In Doubt Per Second</span></span>

<span data-ttu-id="6aaf5-104">Nombre del contador: Operaciones de transacción en duda por segundo.</span><span class="sxs-lookup"><span data-stu-id="6aaf5-104">Counter Name: Transacted Operations In Doubt Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6aaf5-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="6aaf5-105">Description</span></span>  

 <span data-ttu-id="6aaf5-106">El número de operaciones de transacción con un resultado en duda en este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="6aaf5-106">Number of transactional operations with an in-doubt outcome in this service in a second.</span></span>  
  
 <span data-ttu-id="6aaf5-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="6aaf5-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="6aaf5-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="6aaf5-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
