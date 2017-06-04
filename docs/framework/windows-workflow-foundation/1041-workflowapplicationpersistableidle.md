---
title: "1041 - WorkflowApplicationPersistableIdle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1041 - WorkflowApplicationPersistableIdle
## Propiedades  
  
|||  
|-|-|  
|Id.|1041|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que una aplicación de flujo de trabajo está inactiva y con persistencia.  La aplicación de flujo de trabajo estará inactiva o se conservará.  
  
## Mensaje  
 WorkflowApplication con id. '%1' está inactivo y es persistente. Se realizará la siguiente acción: %2.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|WorkflowApplicationId|xs:string|Identificador de la aplicación del flujo de trabajo.|  
|ActionTaken|xs:string|La acción que se adoptará en la aplicación de flujo de trabajo.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|