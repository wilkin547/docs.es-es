---
title: "39458 - TrackingRecordTruncated | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 39458 - TrackingRecordTruncated
## Propiedades  
  
|||  
|-|-|  
|Id.|39458|  
|Palabras clave|WFTracking|  
|Nivel|Advertencia|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que se ha truncado un registro de seguimiento.  Se han quitado las variables, anotaciones y datos del usuario.  
  
## Mensaje  
 Se ha escrito un registro de seguimiento %1 truncado en la sesión de ETW con el proveedor %2.  Se han quitado las variables, anotaciones y datos del usuario.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|RecordNumber|xs:string|Número del registro de seguimiento.|  
|ProviderId|xs:string|Identificador del proveedor ETW.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|