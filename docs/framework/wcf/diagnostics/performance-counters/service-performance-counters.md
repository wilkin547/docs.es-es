---
title: Contadores de rendimiento de los servicios
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: 71eff5c656a4782056ac518f105f73bc549da336
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="service-performance-counters"></a>Contadores de rendimiento de los servicios
Los contadores de rendimiento del servicio miden el conjunto del comportamiento del servicio y se utilizan para diagnosticar el rendimiento de todo el servicio. Se pueden encontrar bajo el objeto de rendimiento `ServiceModelService 4.0.0.0` al visualizarlo mediante el monitor de rendimiento (Perfmon.exe). Los nombres de las instancias se establecen utilizando el siguiente patrón:  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  Hay un límite en la longitud del nombre de una instancia del contador de rendimiento. Cuando un nombre de instancia del contador de Windows Communication Foundation (WCF) supera la longitud máxima, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] reemplaza una parte del nombre de instancia con un valor hash.  
  
## <a name="see-also"></a>Vea también  
 [Contadores de rendimiento](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
