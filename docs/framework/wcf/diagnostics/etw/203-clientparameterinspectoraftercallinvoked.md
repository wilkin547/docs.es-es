---
title: "203 - ClientParameterInspectorAfterCallInvoked | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 203 - ClientParameterInspectorAfterCallInvoked
## Propiedades  
  
|||  
|-|-|  
|Id.|203|  
|Palabras clave|Troubleshooting, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Descripción  
 Se emite este evento cuando el modelo de servicio ha invocado el método `AfterCall` en un inspector de parámetro de cliente.  
  
## Mensaje  
 El distribuidor invocó 'AfterCall' en ClientParameterInspector de tipo '%1'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|TypeName|`xs:string`|El nombre completo \(FullName\) de CLR del tipo del inspector invocado.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.  El formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio'.  Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|