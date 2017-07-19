---
title: "213 - ServiceHostStarted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 213 - ServiceHostStarted
## Propiedades  
  
|||  
|-|-|  
|Id.|213|  
|Palabras clave|EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceHost|  
|Nivel|LogAlways|  
|Canal|Microsoft\-Windows\-Servidor de aplicaciones\-Aplicaciones\/Analítico|  
  
## Descripción  
 Este evento se emite cuando se inicia un host de servicio hospedado en web.Esto suele ocurrir cuando un mensaje activa el servicio.También puede pasar si el servicio se configura para iniciarse automáticamente.  
  
## Mensaje  
 ServiceHost iniciado: '%1'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Service Type Name|`xs:string`|El nombre completo \(FullName\) de CLR del tipo de implementación del servicio.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.El formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio'.Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|