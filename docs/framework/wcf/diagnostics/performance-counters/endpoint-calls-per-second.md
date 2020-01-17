---
title: 'Extremo: Llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
ms.openlocfilehash: d639d881bcedd336c7bbabd28ec385f60ff54d43
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163792"
---
# <a name="endpoint-calls-per-second"></a><span data-ttu-id="62b8b-102">Extremo: Llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="62b8b-102">Endpoint: Calls Per Second</span></span>
<span data-ttu-id="62b8b-103">Nombre del contador: llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="62b8b-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="62b8b-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="62b8b-104">Description</span></span>  
 <span data-ttu-id="62b8b-105">Número de llamadas a este punto de conexión en un segundo.</span><span class="sxs-lookup"><span data-stu-id="62b8b-105">Number of calls to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="62b8b-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="62b8b-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="62b8b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="62b8b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
