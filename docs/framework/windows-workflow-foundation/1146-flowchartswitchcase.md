---
title: "1146 - FlowchartSwitchCase | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 274e9209-1720-4512-a615-e742f00895f4
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1146 - FlowchartSwitchCase
## Propiedades  
  
|||  
|-|-|  
|Id.|1146|  
|Palabras clave|WFActivities|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica qué caso se ha seleccionado en un modificador de diagrama de flujo.  
  
## Mensaje  
 Flowchart '%1'\/FlowSwitch \- Se seleccionó el caso '%2'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Diagrama de flujo|xs:string|El nombre para mostrar del diagrama de flujo.|  
|Caso|xs:string|Caso de roles que seleccionó.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|