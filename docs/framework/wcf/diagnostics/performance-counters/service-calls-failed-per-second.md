---
title: 'Servicio: Errores en llamadas por segundo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f1b196f3bed9b4e02963b090cf92a771d4bc5742
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="d6a41-102">Servicio: Errores en llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="d6a41-102">Service: Calls Failed Per Second</span></span>
<span data-ttu-id="d6a41-103">Nombre del contador: Errores de llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="d6a41-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d6a41-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6a41-104">Description</span></span>  
 <span data-ttu-id="d6a41-105">Número de llamadas que tienen excepciones no controladas y que son recibidas por este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="d6a41-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="d6a41-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="d6a41-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="d6a41-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="d6a41-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="d6a41-108">En código administrado, las excepciones se inician al producirse condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="d6a41-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="d6a41-109">En código administrado, las excepciones se inician al producirse condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="d6a41-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="d6a41-110">El contador se incrementa cada vez que hay una excepción no atendida en este servicio.</span><span class="sxs-lookup"><span data-stu-id="d6a41-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6a41-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6a41-111">See Also</span></span>  
 [<span data-ttu-id="d6a41-112">Especificación y gestión de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="d6a41-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
