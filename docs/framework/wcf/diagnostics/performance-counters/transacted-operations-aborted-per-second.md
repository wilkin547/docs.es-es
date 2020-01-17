---
title: Operaciones de transacción anuladas por segundo
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: d03f1faf7d2a00d02500fe9759ba940445d8eee3
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76164026"
---
# <a name="transacted-operations-aborted-per-second"></a><span data-ttu-id="530fb-102">Operaciones de transacción anuladas por segundo</span><span class="sxs-lookup"><span data-stu-id="530fb-102">Transacted Operations Aborted Per Second</span></span>
<span data-ttu-id="530fb-103">Nombre del contador: operaciones de transacción anuladas por segundo.</span><span class="sxs-lookup"><span data-stu-id="530fb-103">Counter Name: Transacted Operations Aborted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="530fb-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="530fb-104">Description</span></span>  
 <span data-ttu-id="530fb-105">Número de operaciones transaccionales anuladas en este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="530fb-105">Number of transactional operations that have been aborted in this service in a second.</span></span>  
  
 <span data-ttu-id="530fb-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="530fb-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="530fb-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="530fb-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
