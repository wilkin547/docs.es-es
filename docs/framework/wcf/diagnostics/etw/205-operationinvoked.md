---
title: "205 - OperationInvoked | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 205 - OperationInvoked
## Propiedades  
  
|||  
|-|-|  
|Id.|205|  
|Palabras clave|Solución de problemas, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Servidor de aplicaciones\-Aplicaciones\/Analítico|  
  
## Descripción  
 Este evento se emite justo antes de que el `OperationInvoker` predeterminado del modelo de servicio inicie una llamada a un método.  
  
## Mensaje  
 Un OperationInvoker invocó el método '%1'.Información del autor de la llamada: '%2'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Method Name|`xs:string`|El nombre de CLR del método invocado por `OperationInvoker`.|  
|Información del autor de la llamada|`xs:string`|La dirección IP y el número de puerto del cliente en el formato 'IPAddress:PortNumber'.Los dos valores se recuperan de la propiedad de mensaje 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' en el contexto de la operación.Tenga en cuenta que, para los enlaces que no son de TCP, este valor es `null`.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.El formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio'.Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|