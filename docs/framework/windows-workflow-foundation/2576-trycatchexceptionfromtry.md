---
title: "2576 - TryCatchExceptionFromTry | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 47e48973-b17c-4a16-8338-c84b54aa0a6e
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 2576 - TryCatchExceptionFromTry
## Propiedades  
  
|||  
|-|-|  
|Id.|2576|  
|Palabras clave|WFActivities|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que la actividad TryCatch ha detectado una excepción.  
  
## Mensaje  
 La actividad TryCatch '%1 ha detectado una excepción de tipo '%2'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|Excepción|xs:string|Nombre del tipo de la excepción.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|