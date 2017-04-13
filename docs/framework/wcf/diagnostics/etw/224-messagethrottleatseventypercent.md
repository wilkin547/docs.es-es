---
title: "224 - MessageThrottleAtSeventyPercent | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 224 - MessageThrottleAtSeventyPercent
## Propiedades  
  
|||  
|-|-|  
|Id.|224|  
|Palabras clave|EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel|  
|Nivel|Advertencia|  
|Canal|Microsoft\-Windows\-Servidor de aplicaciones\-Aplicaciones\/Analítico|  
  
## Descripción  
 Cuando se ha superado uno de los aceleradores del servicio principal, se emite el evento `MessageThrottleExceeded`.Cuando la punta de actividad se retrasa y el valor actual del acelerador está al 70 por ciento del límite actual, entonces se emite este evento.Tenga en cuenta que este evento solo se emite una vez cuando la actividad se retrasa.Si el valor actual oscila alrededor del valor del 70 por ciento \(por ejemplo, 70, 69, 70, 71, 70, 69\), solo la primera aparición del 70 por ciento producirá un evento.Una vez emitido este evento, las situaciones futuras de superación del límite del acelerador resultarán en un evento `MessageThrottleExceeded`.  
  
## Mensaje  
 La limitación '%1' de '%2' se encuentra al 70%.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Throttle Name|`xs:string`|El nombre del acelerador que se ha superado.`MaxConcurrentCalls`, `MaxConcurrentInstances` o `MaxConcurrentSessions`,|  
|Limit|`xs:long`|El límite configurado actual del acelerador.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.El formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio'.Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|