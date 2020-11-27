---
title: Errores de llamadas por segundo
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: d3eafc4b31f0e62093a972b7c9f2325a3648d21b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285465"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="311d8-102">Errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="311d8-102">Calls Failed Per Second</span></span>

<span data-ttu-id="311d8-103">Nombre de contador: errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="311d8-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="311d8-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="311d8-104">Description</span></span>  

 <span data-ttu-id="311d8-105">Número de llamadas con excepciones no atendidas en esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="311d8-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="311d8-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="311d8-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="311d8-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="311d8-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="311d8-108">Este contador se incrementa cada vez que hay una excepción no controlada en esta operación.</span><span class="sxs-lookup"><span data-stu-id="311d8-108">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="311d8-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="311d8-109">See also</span></span>

- [<span data-ttu-id="311d8-110">Especificación y administración de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="311d8-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
