---
title: "204 - ClientParameterInspectorBeforeCallInvoked | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8253555a-9002-4565-8ede-33d7a33a895f
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 204 - ClientParameterInspectorBeforeCallInvoked
## Propiedades  
  
|||  
|-|-|  
|Id.|204|  
|Palabras clave|Solución de problemas, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Servidor de aplicaciones\-Aplicaciones\/Analítico|  
  
## Descripción  
 Se emite este evento cuando el modelo de servicio ha invocado el método `BeforeCall` en un inspector de parámetro de cliente.  
  
## Mensaje  
 El distribuidor invocó 'BeforeCall' en ClientParameterInspector de tipo '%1'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|TypeName|`xs:string`|El nombre completo \(FullName\) de CLR del tipo del inspector invocado.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.El formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio'.Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|