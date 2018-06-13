---
title: Operaciones de transacción anuladas por segundo
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: dacdf93f4610df9161134a41ece19fd2a18637c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474537"
---
# <a name="transacted-operations-aborted-per-second"></a><span data-ttu-id="8e82a-102">Operaciones de transacción anuladas por segundo</span><span class="sxs-lookup"><span data-stu-id="8e82a-102">Transacted Operations Aborted Per Second</span></span>
<span data-ttu-id="8e82a-103">Nombre del contador: operaciones de transacción anuladas por segundo.</span><span class="sxs-lookup"><span data-stu-id="8e82a-103">Counter Name: Transacted Operations Aborted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8e82a-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e82a-104">Description</span></span>  
 <span data-ttu-id="8e82a-105">Número de operaciones transaccionales anuladas en este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="8e82a-105">Number of transactional operations that have been aborted in this service in a second.</span></span>  
  
 <span data-ttu-id="8e82a-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="8e82a-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="8e82a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="8e82a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
