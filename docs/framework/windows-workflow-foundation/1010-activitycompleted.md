---
title: "1010 - ActivityCompleted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1010 - ActivityCompleted
## Propiedades  
  
|||  
|-|-|  
|Id.|1010|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que una actividad ha completado su ejecución.  
  
## Mensaje  
 Actividad “%1", DisplayName: “%2 ", InstanceId: “%3 " se ha completado en el estado “%4".  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Actividad|xs:string|El nombre de tipo de la actividad.|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|InstanceId|xs:string|La identificación de instancia de la actividad.|  
|Estado|xs:string|Estado de la actividad.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|