---
title: "39456 - TrackingRecordDropped | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 39456 - TrackingRecordDropped
## Propiedades  
  
|||  
|-|-|  
|Id.|39456|  
|Palabras clave|WFTracking|  
|Nivel|Advertencia|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que se ha quitado un registro de seguimiento porque su tamaño supera el máximo permitido por el proveedor de sesión ETW.  
  
## Mensaje  
 El tamaño del registro de seguimiento %1 excede el máximo permitido por la sesión de ETW para el proveedor %2  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Excepción|xs:string|Detalles de la excepción para la excepción|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|