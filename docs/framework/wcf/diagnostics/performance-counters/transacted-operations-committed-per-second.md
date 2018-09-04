---
title: Operaciones de transacción confirmadas por segundo
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: 124eae3b36a731ac50a147782b19c87e3adfa7be
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43564016"
---
# <a name="transacted-operations-committed-per-second"></a><span data-ttu-id="a4d4e-102">Operaciones de transacción confirmadas por segundo</span><span class="sxs-lookup"><span data-stu-id="a4d4e-102">Transacted Operations Committed Per Second</span></span>
<span data-ttu-id="a4d4e-103">Nombre del contador: Operaciones de transacción confirmadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="a4d4e-103">Counter Name: Transacted Operations Committed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a4d4e-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4d4e-104">Description</span></span>  
 <span data-ttu-id="a4d4e-105">Número de operaciones transaccionales confirmadas en este servicio cada segundo.</span><span class="sxs-lookup"><span data-stu-id="a4d4e-105">Number of transactional operations that have been committed in this service in a second.</span></span>  
  
 <span data-ttu-id="a4d4e-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="a4d4e-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="a4d4e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="a4d4e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
