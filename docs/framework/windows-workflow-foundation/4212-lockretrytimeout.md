---
title: "4212 - LockRetryTimeout | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4212 - LockRetryTimeout
## Propiedades  
  
|||  
|-|-|  
|Id.|4212|  
|Palabras clave|WFInstanceStore|  
|Nivel|Advertencia|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 El proveedor de SQL detectó que se agotó el tiempo de espera al intentar adquirir el bloqueo de instancia.  
  
## Mensaje  
 Se agotó el tiempo de espera al intentar adquirir el bloqueo de la instancia. La operación no se completó en el tiempo de espera asignado de %1.  El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Delay|xs:string|Retraso entre los intentos.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|