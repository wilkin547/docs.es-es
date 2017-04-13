---
title: "209 - MessageInspectorBeforeSendInvoked | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 209 - MessageInspectorBeforeSendInvoked
## Propiedades  
  
|||  
|-|-|  
|Id.|209|  
|Palabras clave|Solución de problemas, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Servidor de aplicaciones\-Aplicaciones\/Analítico|  
  
## Descripción  
 Se emite este evento cuando el modelo de servicio ha invocado el método `BeforeSend` en un inspector de mensaje.  
  
## Mensaje  
 El distribuidor invocó 'BeforeSendRequest' en un MessageInspector de tipo '%1'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|TypeName|`xs:string`|Nombre completo \(FullName\) de CLR del tipo de `MessageInspector` invocado.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.El formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio'.Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|