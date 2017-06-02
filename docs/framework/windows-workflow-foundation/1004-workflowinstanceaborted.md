---
title: "1004 - WorkflowInstanceAborted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# 1004 - WorkflowInstanceAborted
## Propiedades  
  
|||  
|-|-|  
|Id.|1004|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que una instancia de flujo de trabajo se ha anulado con una excepción.  
  
## Mensaje  
 WorkflowInstance Id: '%1' se anuló con una excepción.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|El id. de instancia del flujo de trabajo.|  
|Excepción|`xs:string`|Detalles de la excepción para la excepción|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|