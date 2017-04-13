---
title: "219 - ServiceException | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 219 - ServiceException
## Propiedades  
  
|||  
|-|-|  
|Id.|219|  
|Palabras clave|EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel|  
|Nivel|Error|  
|Canal|Microsoft\-Windows\-Servidor de aplicaciones\-Aplicaciones\/Analítico|  
  
## Descripción  
 Este evento se emite cuando un servicio WCF encuentra una excepción no controlada.Esto incluye las excepciones no controladas durante la activación, durante el procesamiento de mensajes y en código de usuario.  
  
## Mensaje  
 Excepción no controlada del tipo '%2' durante el procesamiento de mensajes.ToString de excepción completa: %1.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|ExceptionToString|`xs:string`|El resultado de llamar a `ToString`\(\) en la excepción de CLR.|  
|ExceptionTypeName|`xs:string`|El nombre completo \(FullName\) de CLR del tipo de la excepción.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.El formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio'.Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|