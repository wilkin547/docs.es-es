---
title: "1007 - WorkflowApplicationPersisted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f4ea4452-28e3-4e66-93c6-eb12ee29bcb1
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1007 - WorkflowApplicationPersisted
## Propiedades  
  
|||  
|-|-|  
|Id.|1007|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que una aplicación de flujo de trabajo se conserva.  
  
## Mensaje  
 WorkflowApplication Id: '%1' se conservó.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|WorkflowApplicationId|`xs:string`|Identificador de la aplicación del flujo de trabajo.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|