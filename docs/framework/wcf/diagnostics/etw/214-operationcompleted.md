---
title: "214 - OperationCompleted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 214 - OperationCompleted
## Propiedades  
  
|||  
|-|-|  
|Id.|214|  
|Palabras clave|HealthMonitoring, EndToEndMonitoring, Solución de problemas, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Servidor de aplicaciones\-Aplicaciones\/Analítico|  
  
## Descripción  
 Este evento se emite cuando `OperationInvoker` predeterminado del modelo de servicio ha finalizado una llamada a un método sin que dicho método haya generado una excepción.  
  
## Mensaje  
 Un OperationInvoker completó la llamada al método '%1'.La duración de la llamada al método fue de '%2' ms.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Method Name|`xs:string`|El nombre de CLR del método invocado por `OperationInvoker`.|  
|Duration|`xs:long`|El tiempo, en milisegundos, que tardó `OperationInvoker` en invocar el método.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.El formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio'.Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|