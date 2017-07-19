---
title: "221 - MessageReceivedFromTransport | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 221 - MessageReceivedFromTransport
## Propiedades  
  
|||  
|-|-|  
|Id.|221|  
|Palabras clave|EndToEndMonitoring, Solución de problemas, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Servidor de aplicaciones\-Aplicaciones\/Analítico|  
  
## Descripción  
 Este evento se emite cuando el modelo de servicio recibe un mensaje del transporte.  
  
## Mensaje  
 El distribuidor recibió un mensaje del transporte.Correlation ID \=\= '%1'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Correlation ID|`xs:GUID`|El identificador de actividad usado para poner en correlación un evento `MessageSentToTransport` de un servicio o cliente con su `MessageReceivedFromTransport` correspondiente en el otro extremo.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.El formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio'.Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|