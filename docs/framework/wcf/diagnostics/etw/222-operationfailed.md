---
title: "222 - OperationFailed | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 222 - OperationFailed
## Propiedades  
  
|||  
|-|-|  
|Id.|222|  
|Palabras clave|EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel|  
|Nivel|Advertencia|  
|Canal|Microsoft\-Windows\-Servidor de aplicaciones\-Aplicaciones\/Analítico|  
  
## Descripción  
 Este evento se emite cuando `OperationInvoker` predeterminado del modelo de servicio detecta una excepción al invocar el método.Tenga en cuenta que las excepciones que derivan de `FaultException` hacen que este evento no se emita.  
  
## Mensaje  
 El método '%1' produjo una excepción no controlada al invocarse por OperationInvoker.La duración de la llamada de método fue de '%2' ms.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Method Name|`xs:string`|El nombre de CLR del método invocado por `OperationInvoker`.|  
|Duration|`xs:long`|El tiempo, en milisegundos, que tardó `OperationInvoker` en invocar el método.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.El formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio'.Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|