---
title: "punto de conexión: Errores en llamadas por segundo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5da436c5e8159ff922c36172490a28e854bbee8b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="38459-102">punto de conexión: Errores en llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="38459-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="38459-103">Nombre del contador: Errores de llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="38459-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="38459-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="38459-104">Description</span></span>  
 <span data-ttu-id="38459-105">Número de llamadas que tienen excepciones no controladas y son recibidas por este punto de conexión en un segundo.</span><span class="sxs-lookup"><span data-stu-id="38459-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="38459-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="38459-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="38459-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="38459-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="38459-108">Este contador se incrementa siempre que se produce una excepción no controlada en este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="38459-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38459-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="38459-109">See Also</span></span>  
 [<span data-ttu-id="38459-110">Especificación y gestión de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="38459-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
