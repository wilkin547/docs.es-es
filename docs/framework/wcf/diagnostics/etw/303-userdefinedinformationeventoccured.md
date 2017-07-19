---
title: "303 - UserDefinedInformationEventOccured | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5ed5acaf-3755-4417-92c4-4ebc8e854ca1
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 303 - UserDefinedInformationEventOccured
## Propiedades  
  
|||  
|-|-|  
|Id.|303|  
|Palabras clave|Solución de problemas, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Servidor de aplicaciones\-Aplicaciones\/Analítico|  
  
## Descripción  
 Este evento se emite desde el código de usuario.Los desarrolladores pueden emitir este evento cuando se produce un evento informativo definido por el usuario en su servicio.Esto se puede llevar a cabo con las API de <xref:System.Diagnostics.Eventing>.Además, hay un ejemplo de WCF que ajusta esa API y muestra cómo emitir este evento correctamente.  
  
## Mensaje  
 Nombre: '%1', referencia: '%2', carga:%3  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Name|`xs:string`|El nombre del evento definido por el usuario.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.El formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio'.Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|Payload|`xs:string`|La carga del evento definida por el usuario.|