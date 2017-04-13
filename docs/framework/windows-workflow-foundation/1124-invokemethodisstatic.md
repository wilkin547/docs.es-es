---
title: "1124 - InvokeMethodIsStatic | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b9643641-fb52-4fa8-b354-4dd6617d68f6
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1124 - InvokeMethodIsStatic
## Propiedades  
  
|||  
|-|-|  
|Id.|1124|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Durante el paso CacheMetadata, la actividad InvokeMethod indica que el método que se va a invocar es estático.  
  
## Mensaje  
 InvokeMethod '%1': el método es estático.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|InvokeMethod|xs:string|Identificación y nombre para mostrar de la actividad InvokeMethod.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|