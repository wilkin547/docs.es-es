---
title: 210 - MessageThrottleExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ca08ea-c11c-4753-946e-98aa820f8711
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2d027f549e86095c732d0e60df3faded44a39fd2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="210---messagethrottleexceeded"></a>210 - MessageThrottleExceeded
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|210|  
|Palabras clave|EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel|  
|Nivel|Advertencia|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 Este evento se emite cuando se ha superado uno de los tres aceleradores del servicio principales. Tenga en cuenta que este evento solo se emite cuando se supera inicialmente el límite del acelerador. Por ejemplo, si el límite del acelerador para las llamadas simultáneas es 10, la llamada simultánea n.º 11 da como resultado un evento `MessageThrottleExceeded`. La llamada n.º 12 no produce otro evento. Además, para evitar una secuencia de eventos con ruido, la actividad que se sitúa cerca del límite no produce otro evento. En este ejemplo, si un par de llamadas finalizan, hay 9 llamadas simultáneas. Si, posteriormente, entran dos llamadas más, el valor actual será de nuevo 11. Esto no produce otro evento. Cuando el valor actual desciende al 70 por ciento del límite del acelerador, se emite un evento diferente que indica que la actividad es más lenta. Actividad futura que supera los resultados límite en otro evento `MessageThrottleExceeded` que se emite. En este ejemplo, si la cantidad de llamadas simultáneas desciende a 7 y, a continuación, vuelve a alcanzar 11, se emite otro evento `MessageThrottleExceeded`.  
  
## <a name="message"></a>Mensaje  
 Se alcanzó el límite '%1' de '%2'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Throttle Name|`xs:string`|El nombre del acelerador que se ha superado. `MaxConcurrentCalls`, `MaxConcurrentInstances` o `MaxConcurrentSessions`,|  
|Limit|`xs:long`|El límite configurado actual del acelerador.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'. Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
