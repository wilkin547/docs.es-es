---
title: 224 - MessageThrottleAtSeventyPercent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0dd985e3986548938f06e86c1f49d23c43307d17
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="224---messagethrottleatseventypercent"></a>224 - MessageThrottleAtSeventyPercent
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|224|  
|Palabras clave|EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel|  
|Nivel|Advertencia|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 Cuando se ha superado uno de los aceleradores del servicio principal, se emite el evento `MessageThrottleExceeded`. Cuando la punta de actividad se retrasa y el valor actual del acelerador está al 70 por ciento del límite actual, entonces se emite este evento. Tenga en cuenta que este evento solo se emite una vez cuando la actividad se retrasa. Si el valor actual oscila alrededor del valor del 70 por ciento (por ejemplo, 70, 69, 70, 71, 70, 69), solo la primera aparición del 70 por ciento producirá un evento. Una vez emitido este evento, las situaciones futuras de superación del límite del acelerador resultarán en un evento `MessageThrottleExceeded`.  
  
## <a name="message"></a>Mensaje  
 La limitación '%1' de '%2' se encuentra al 70%.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Throttle Name|`xs:string`|El nombre del acelerador que se ha superado. `MaxConcurrentCalls`, `MaxConcurrentInstances` o `MaxConcurrentSessions`,|  
|Limit|`xs:long`|El límite configurado actual del acelerador.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'. Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
