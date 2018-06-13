---
title: Contadores de rendimiento del punto de conexión
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: 8354cff600f8c16a5ab9b4f6efd3c0b93a46276c
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803142"
---
# <a name="endpoint-performance-counters"></a><span data-ttu-id="d3cb9-102">Contadores de rendimiento del punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d3cb9-102">Endpoint Performance Counters</span></span>
<span data-ttu-id="d3cb9-103">Los contadores de rendimiento del punto de conexión capturan datos que revelan cómo un punto de conexión está aceptando los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d3cb9-103">Endpoint performance counters capture data that reveals how an endpoint is accepting messages.</span></span> <span data-ttu-id="d3cb9-104">Se pueden encontrar en el objeto de rendimiento `ServiceModelEndpoint 4.0.0.0` al verlo con el Monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d3cb9-104">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="d3cb9-105">Las instancias se denominan utilizando este patrón:</span><span class="sxs-lookup"><span data-stu-id="d3cb9-105">The instances are named using this pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="d3cb9-106">Los datos son similares a los datos reunidos para las operaciones individuales, pero solo se agregan a lo largo del extremo.</span><span class="sxs-lookup"><span data-stu-id="d3cb9-106">The data is similar to that collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="d3cb9-107">Hay un límite en la longitud del nombre de una instancia del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d3cb9-107">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="d3cb9-108">Cuando un nombre de instancia del contador de Windows Communication Foundation (WCF) supera la longitud máxima, WCF reemplaza una parte del nombre de instancia con un valor hash.</span><span class="sxs-lookup"><span data-stu-id="d3cb9-108">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3cb9-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3cb9-109">See Also</span></span>  
 [<span data-ttu-id="d3cb9-110">Contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="d3cb9-110">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
