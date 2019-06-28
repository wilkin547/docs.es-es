---
title: Errores de llamadas por segundo
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: aa8cd4c2d9f642b525b2b9ccb931c4f2101a5129
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67421786"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="23b74-102">Errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="23b74-102">Calls Failed Per Second</span></span>
<span data-ttu-id="23b74-103">Nombre del contador: Errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="23b74-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="23b74-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="23b74-104">Description</span></span>  
 <span data-ttu-id="23b74-105">Número de llamadas con excepciones no atendidas en esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="23b74-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="23b74-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="23b74-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="23b74-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="23b74-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="23b74-108">Este contador se incrementa cada vez que hay una excepción no controlada en esta operación.</span><span class="sxs-lookup"><span data-stu-id="23b74-108">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23b74-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="23b74-109">See also</span></span>

- [<span data-ttu-id="23b74-110">Especificación y gestión de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="23b74-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
