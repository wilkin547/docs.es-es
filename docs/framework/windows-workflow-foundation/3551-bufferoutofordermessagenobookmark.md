---
title: "3551 - BufferOutOfOrderMessageNoBookmark | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3551 - BufferOutOfOrderMessageNoBookmark
## Propiedades  
  
|||  
|-|-|  
|Id.|3551|  
|Palabras clave|WFServices|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Descripción  
 Indica que se ha producido un error en la reanudación de marcador.  La operación de recepción almacenada en búfer se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.  
  
## Mensaje  
 La operación '%2' en la instancia del servicio '%1' no se puede realizar en este momento.  Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|OperationName|xs:string|Nombre de la operación.|  
|ServiceInstanceId|xs:string|Identificador de la instancia del servicio.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|