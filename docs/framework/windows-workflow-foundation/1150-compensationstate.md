---
title: "1150 - CompensationState | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1150 - CompensationState
## Propiedades  
  
|||  
|-|-|  
|Id.|1150|  
|Palabras clave|WFActivities|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica un cambio de estado en un CompensableActivity.  
  
## Mensaje  
 CompensableActivity '%1' no tiene el estado '%2'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|Estado|xs:string|Estado de compensación.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|