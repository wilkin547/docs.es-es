---
title: "1103 - WorkflowActivitySuspend | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b64e15c2-cb2c-4314-9074-ce2c6717232e
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1103 - WorkflowActivitySuspend
## Propiedades  
  
|||  
|-|-|  
|Id.|1103|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que la actividad de flujo de trabajo se ha suspendido.  
  
## Mensaje  
 Id. de WorkflowInstance: '%1' actividad E2E  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|WorkflowInstanceId|xs:string|Identificación de instancia del flujo de trabajo.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|