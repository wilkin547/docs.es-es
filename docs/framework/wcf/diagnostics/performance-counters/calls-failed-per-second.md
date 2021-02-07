---
description: 'Más información sobre: errores de llamadas por segundo'
title: Errores de llamadas por segundo
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: 3961754eb73743a1213922f7c9e1bd164334cd6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759723"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="915e0-103">Errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="915e0-103">Calls Failed Per Second</span></span>

<span data-ttu-id="915e0-104">Nombre de contador: errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="915e0-104">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="915e0-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="915e0-105">Description</span></span>  

 <span data-ttu-id="915e0-106">Número de llamadas con excepciones no atendidas en esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="915e0-106">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="915e0-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="915e0-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="915e0-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="915e0-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="915e0-109">Este contador se incrementa cada vez que hay una excepción no controlada en esta operación.</span><span class="sxs-lookup"><span data-stu-id="915e0-109">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="915e0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="915e0-110">See also</span></span>

- [<span data-ttu-id="915e0-111">Especificación y administración de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="915e0-111">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
