---
title: Errores de llamadas por segundo
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: ff9320b0990a0543bbb1da553d040ff5a4b4fed9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178625"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="dba92-102">Errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="dba92-102">Calls Failed Per Second</span></span>
<span data-ttu-id="dba92-103">Nombre del contador: Errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="dba92-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="dba92-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="dba92-104">Description</span></span>  
 <span data-ttu-id="dba92-105">Número de llamadas con excepciones no atendidas en esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="dba92-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="dba92-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="dba92-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="dba92-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="dba92-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="dba92-108">El contador se incrementa siempre que se produce una excepción no controlada en esta operación.</span><span class="sxs-lookup"><span data-stu-id="dba92-108">This counter is incremented everytime there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dba92-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="dba92-109">See also</span></span>

- [<span data-ttu-id="dba92-110">Especificación y administración de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="dba92-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
