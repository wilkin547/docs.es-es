---
description: 'Más información acerca de: contadores de rendimiento del servicio'
title: Contadores de rendimiento de los servicios
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: 16f6f2548cf7f92b64264ac606423c69e62cd110
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686042"
---
# <a name="service-performance-counters"></a><span data-ttu-id="94047-103">Contadores de rendimiento de los servicios</span><span class="sxs-lookup"><span data-stu-id="94047-103">Service Performance Counters</span></span>

<span data-ttu-id="94047-104">Los contadores de rendimiento del servicio miden el conjunto del comportamiento del servicio y se utilizan para diagnosticar el rendimiento de todo el servicio.</span><span class="sxs-lookup"><span data-stu-id="94047-104">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="94047-105">Se pueden encontrar bajo el objeto de rendimiento `ServiceModelService 4.0.0.0` al visualizarlo mediante el monitor de rendimiento (Perfmon.exe).</span><span class="sxs-lookup"><span data-stu-id="94047-105">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="94047-106">Los nombres de las instancias se establecen utilizando el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="94047-106">The instances are named using the following pattern:</span></span>  
  
`ServiceName@ServiceBaseAddress`
  
> [!CAUTION]
> <span data-ttu-id="94047-107">Hay un límite en la longitud del nombre de una instancia del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="94047-107">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="94047-108">Cuando un nombre de instancia de contador de Windows Communication Foundation (WCF) supera la longitud máxima, WCF reemplaza una parte del nombre de instancia por un valor hash.</span><span class="sxs-lookup"><span data-stu-id="94047-108">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94047-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="94047-109">See also</span></span>

- [<span data-ttu-id="94047-110">Contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="94047-110">Performance Counters</span></span>](index.md)
