---
title: Operaciones de transacción confirmadas por segundo
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: 3bec51a7be63c54a240b85032ecac09b87173393
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474277"
---
# <a name="transacted-operations-committed-per-second"></a><span data-ttu-id="6b0e1-102">Operaciones de transacción confirmadas por segundo</span><span class="sxs-lookup"><span data-stu-id="6b0e1-102">Transacted Operations Committed Per Second</span></span>
<span data-ttu-id="6b0e1-103">Nombre del contador: Operaciones de transacción confirmadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="6b0e1-103">Counter Name: Transacted Operations Committed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6b0e1-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b0e1-104">Description</span></span>  
 <span data-ttu-id="6b0e1-105">Número de operaciones transaccionales confirmadas en este servicio cada segundo.</span><span class="sxs-lookup"><span data-stu-id="6b0e1-105">Number of transactional operations that have been committed in this service in a second.</span></span>  
  
 <span data-ttu-id="6b0e1-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="6b0e1-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="6b0e1-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="6b0e1-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
