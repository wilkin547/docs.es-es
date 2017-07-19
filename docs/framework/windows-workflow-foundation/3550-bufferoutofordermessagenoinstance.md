---
title: "3550 - BufferOutOfOrderMessageNoInstance | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3550 - BufferOutOfOrderMessageNoInstance
## Propiedades  
  
|||  
|-|-|  
|Id.|3550|  
|Palabras clave|WFServices|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Descripción  
 Indica que se ha producido un error en la recepción almacenada en el búfer.  La operación se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.  
  
## Mensaje  
 La operación '%1' no se puede realizar en este momento.  Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|OperationName|xs:string|Nombre de la operación.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|