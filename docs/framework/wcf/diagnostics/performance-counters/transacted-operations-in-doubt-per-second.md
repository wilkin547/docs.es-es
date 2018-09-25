---
title: Operaciones de transacción dudosas por segundo
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: f7365c4e5f03711129916c8c6964f7e25e9b553e
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2018
ms.locfileid: "47027562"
---
# <a name="transacted-operations-in-doubt-per-second"></a><span data-ttu-id="41193-102">Operaciones de transacción dudosas por segundo</span><span class="sxs-lookup"><span data-stu-id="41193-102">Transacted Operations In Doubt Per Second</span></span>
<span data-ttu-id="41193-103">Nombre del contador: Operaciones de transacción en duda por segundo.</span><span class="sxs-lookup"><span data-stu-id="41193-103">Counter Name: Transacted Operations In Doubt Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="41193-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="41193-104">Description</span></span>  
 <span data-ttu-id="41193-105">El número de operaciones de transacción con un resultado en duda en este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="41193-105">Number of transactional operations with an in-doubt outcome in this service in a second.</span></span>  
  
 <span data-ttu-id="41193-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="41193-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="41193-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="41193-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
