---
title: "210 - MessageThrottleExceeded | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 24ca08ea-c11c-4753-946e-98aa820f8711
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 210 - MessageThrottleExceeded
## Propiedades  
  
|||  
|-|-|  
|Id.|210|  
|Palabras clave|EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel|  
|Nivel|Advertencia|  
|Canal|Microsoft\-Windows\-Servidor de aplicaciones\-Aplicaciones\/Analítico|  
  
## Descripción  
 Este evento se emite cuando se ha superado uno de los tres aceleradores del servicio principales.Tenga en cuenta que este evento solo se emite cuando se supera inicialmente el límite del acelerador.Por ejemplo, si el límite del acelerador para las llamadas simultáneas es 10, la llamada simultánea n.º 11 da como resultado un evento `MessageThrottleExceeded`.La llamada n.º 12 no produce otro evento.Además, para evitar una secuencia de eventos con ruido, la actividad que se sitúa cerca del límite no produce otro evento.En este ejemplo, si un par de llamadas finalizan, hay 9 llamadas simultáneas.Si, posteriormente, entran dos llamadas más, el valor actual será de nuevo 11.Esto no produce otro evento.Cuando el valor actual desciende al 70 por ciento del límite del acelerador, se emite un evento diferente que indica que la actividad es más lenta.Actividad futura que supera los resultados límite en otro evento `MessageThrottleExceeded` que se emite.En este ejemplo, si la cantidad de llamadas simultáneas desciende a 7 y, a continuación, vuelve a alcanzar 11, se emite otro evento `MessageThrottleExceeded`.  
  
## Mensaje  
 Se alcanzó el límite '%1' de '%2'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Throttle Name|`xs:string`|El nombre del acelerador que se ha superado.`MaxConcurrentCalls`, `MaxConcurrentInstances` o `MaxConcurrentSessions`,|  
|Limit|`xs:long`|El límite configurado actual del acelerador.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.El formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio'.Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|