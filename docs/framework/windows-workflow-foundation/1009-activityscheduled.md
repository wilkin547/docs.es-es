---
title: "1009 - ActivityScheduled | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1009 - ActivityScheduled
## Propiedades  
  
|||  
|-|-|  
|Id.|1009|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que una actividad se está programando para ejecutarse.  
  
## Mensaje  
 Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|ParentActivity|xs:string|Nombre del tipo de la actividad principal.|  
|ParentDisplayName|xs:string|Identificación y nombre para mostrar de la actividad principal.|  
|ParentInstanceId|xs:string|Identificador de instancia de la actividad principal.|  
|ChildActivity|xs:string|Nombre del tipo de la actividad secundaria programada.|  
|ChildDisplayName|xs:string|El nombre para mostrar de la actividad secundaria programada.|  
|ChildInstanceId|xs:string|Identificador de instancia de la actividad secundaria programada.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|