---
title: Errores de llamadas por segundo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 876932c707a30d25e6ee6d9abf8e3510dcd13f65
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="5e9a3-102">Errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="5e9a3-102">Calls Failed Per Second</span></span>
<span data-ttu-id="5e9a3-103">Nombre de contador: errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="5e9a3-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="5e9a3-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e9a3-104">Description</span></span>  
 <span data-ttu-id="5e9a3-105">Número de llamadas con excepciones no atendidas en esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="5e9a3-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="5e9a3-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="5e9a3-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="5e9a3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="5e9a3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="5e9a3-108">El contador se incrementa siempre que se produce una excepción no controlada en esta operación.</span><span class="sxs-lookup"><span data-stu-id="5e9a3-108">This counter is incremented everytime there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e9a3-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e9a3-109">See Also</span></span>  
 [<span data-ttu-id="5e9a3-110">Especificación y gestión de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="5e9a3-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
