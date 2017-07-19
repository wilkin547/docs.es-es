---
title: "1002 - WorkflowApplicationTerminated | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# 1002 - WorkflowApplicationTerminated
## Propiedades  
  
|||  
|-|-|  
|Id.|1002|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que una aplicación de flujo de trabajo ha finalizado en el estado Faulted con una excepción.  
  
## Mensaje  
 WorkflowApplication Id: '%1' se terminó.  Se ha completado con el estado Faulted y con una excepción.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|WorkflowApplicationId|`xs:string`|Identificador de la aplicación del flujo de trabajo.|  
|Excepción|`xs:string`|Detalles de la excepción para la excepción|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|