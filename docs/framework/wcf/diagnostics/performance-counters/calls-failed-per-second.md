---
title: Errores de llamadas por segundo
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: 8f2337d5ea3eb696c7be5b25d01396676dae2458
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554122"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="8644f-102">Errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="8644f-102">Calls Failed Per Second</span></span>
<span data-ttu-id="8644f-103">Nombre de contador: errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="8644f-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="8644f-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="8644f-104">Description</span></span>  
 <span data-ttu-id="8644f-105">Número de llamadas con excepciones no atendidas en esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="8644f-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="8644f-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="8644f-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="8644f-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="8644f-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="8644f-108">Este contador se incrementa cada vez que hay una excepción no controlada en esta operación.</span><span class="sxs-lookup"><span data-stu-id="8644f-108">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8644f-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="8644f-109">See also</span></span>

- [<span data-ttu-id="8644f-110">Especificación y administración de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="8644f-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
