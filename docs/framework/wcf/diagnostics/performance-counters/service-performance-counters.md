---
title: Contadores de rendimiento de los servicios
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: 4ce0efbeb0a1d6f2409bb976102b8ec8821d5cdc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70848999"
---
# <a name="service-performance-counters"></a><span data-ttu-id="70f9e-102">Contadores de rendimiento de los servicios</span><span class="sxs-lookup"><span data-stu-id="70f9e-102">Service Performance Counters</span></span>
<span data-ttu-id="70f9e-103">Los contadores de rendimiento del servicio miden el conjunto del comportamiento del servicio y se utilizan para diagnosticar el rendimiento de todo el servicio.</span><span class="sxs-lookup"><span data-stu-id="70f9e-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="70f9e-104">Se pueden encontrar bajo el objeto de rendimiento `ServiceModelService 4.0.0.0` al visualizarlo mediante el monitor de rendimiento (Perfmon.exe).</span><span class="sxs-lookup"><span data-stu-id="70f9e-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="70f9e-105">Los nombres de las instancias se establecen utilizando el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="70f9e-105">The instances are named using the following pattern:</span></span>  
  
`ServiceName@ServiceBaseAddress`
  
> [!CAUTION]
> <span data-ttu-id="70f9e-106">Hay un límite en la longitud del nombre de una instancia del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="70f9e-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="70f9e-107">Cuando un nombre de instancia de contador de Windows Communication Foundation (WCF) supera la longitud máxima, WCF reemplaza una parte del nombre de instancia por un valor hash.</span><span class="sxs-lookup"><span data-stu-id="70f9e-107">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f9e-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="70f9e-108">See also</span></span>

- [<span data-ttu-id="70f9e-109">Contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="70f9e-109">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
