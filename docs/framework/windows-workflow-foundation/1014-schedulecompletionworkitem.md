---
title: "1014 - ScheduleCompletionWorkItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1014 - ScheduleCompletionWorkItem
## Propiedades  
  
|||  
|-|-|  
|Id.|1014|  
|Palabras clave|WFRuntime|  
|Nivel|Detallado|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que se ha programado un CompletionWorkItem.  
  
## Mensaje  
 Se ha programado un CompletionWorkItem para la actividad principal '%1', DisplayName: '%2', InstanceId: '%3'. Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|ParentActivity|xs:string|Nombre del tipo de la actividad principal.|  
|ParentDisplayName|xs:string|Identificación y nombre para mostrar de la actividad principal.|  
|ParentInstanceId|xs:string|Identificador de instancia de la actividad principal.|  
|CompletedActivity|xs:string|El nombre del tipo de la actividad que se completó.|  
|CompletedActivityDisplayName|xs:string|Nombre para mostrar de la actividad que se ha completado.|  
|CompletedActivityInstanceId|xs:string|Identificador de instancia de la actividad que se ha completado.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|