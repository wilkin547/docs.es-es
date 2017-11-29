---
title: Contadores de rendimiento de los servicios
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: de51c6d0a3070f8bba8a2c77f9c028e7cfbc944d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="service-performance-counters"></a><span data-ttu-id="5b25b-102">Contadores de rendimiento de los servicios</span><span class="sxs-lookup"><span data-stu-id="5b25b-102">Service Performance Counters</span></span>
<span data-ttu-id="5b25b-103">Los contadores de rendimiento del servicio miden el conjunto del comportamiento del servicio y se utilizan para diagnosticar el rendimiento de todo el servicio.</span><span class="sxs-lookup"><span data-stu-id="5b25b-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="5b25b-104">Se pueden encontrar bajo el objeto de rendimiento `ServiceModelService 4.0.0.0` al visualizarlo mediante el monitor de rendimiento (Perfmon.exe).</span><span class="sxs-lookup"><span data-stu-id="5b25b-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="5b25b-105">Los nombres de las instancias se establecen utilizando el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="5b25b-105">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  <span data-ttu-id="5b25b-106">Hay un límite en la longitud del nombre de una instancia del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5b25b-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="5b25b-107">Cuando un nombre de instancia de contador [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] supera la longitud máxima, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] reemplaza una parte del nombre de instancia con un valor hash.</span><span class="sxs-lookup"><span data-stu-id="5b25b-107">When a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] counter instance name exceeds the maximum length, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b25b-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b25b-108">See Also</span></span>  
 [<span data-ttu-id="5b25b-109">Contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="5b25b-109">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
