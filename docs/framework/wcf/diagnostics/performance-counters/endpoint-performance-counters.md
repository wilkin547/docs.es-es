---
title: "Contadores de rendimiento del punto de conexión"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 157f0cc5d860841940b0850ca3895f82a12d47ce
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint-performance-counters"></a><span data-ttu-id="4bae7-102">Contadores de rendimiento del punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4bae7-102">Endpoint Performance Counters</span></span>
<span data-ttu-id="4bae7-103">Los contadores de rendimiento del punto de conexión capturan datos que revelan cómo un punto de conexión está aceptando los mensajes.</span><span class="sxs-lookup"><span data-stu-id="4bae7-103">Endpoint performance counters capture data that reveals how an endpoint is accepting messages.</span></span> <span data-ttu-id="4bae7-104">Se pueden encontrar en el objeto de rendimiento `ServiceModelEndpoint 4.0.0.0` al verlo con el Monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4bae7-104">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="4bae7-105">Las instancias se denominan utilizando este patrón:</span><span class="sxs-lookup"><span data-stu-id="4bae7-105">The instances are named using this pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="4bae7-106">Los datos son similares a los datos reunidos para las operaciones individuales, pero solo se agregan a lo largo del extremo.</span><span class="sxs-lookup"><span data-stu-id="4bae7-106">The data is similar to that collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4bae7-107">Hay un límite en la longitud del nombre de una instancia del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4bae7-107">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="4bae7-108">Cuando un nombre de instancia de contador [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] supera la longitud máxima, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] reemplaza una parte del nombre de instancia con un valor hash.</span><span class="sxs-lookup"><span data-stu-id="4bae7-108">When a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] counter instance name exceeds the maximum length, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bae7-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bae7-109">See Also</span></span>  
 [<span data-ttu-id="4bae7-110">Contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="4bae7-110">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
