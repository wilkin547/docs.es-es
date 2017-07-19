---
title: "1148 - FlowchartSwitchCaseNotFound | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9ee7fcee-e040-4306-968e-ed840a1cb00c
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1148 - FlowchartSwitchCaseNotFound
## Propiedades  
  
|||  
|-|-|  
|Id.|1148|  
|Palabras clave|WFActivities|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que no se pudo encontrar ni un caso correspondiente ni un caso predeterminado en un modificador de diagrama de flujo.  La ejecución del diagrama de flujo va a finalizar.  
  
## Mensaje  
 Flowchart '%1'\/FlowSwitch no puede encontrar una actividad Case ni un caso predeterminado que coincida con el resultado de la expresión.  La ejecución del diagrama de flujo va a finalizar.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Diagrama de flujo|xs:string|El nombre para mostrar del diagrama de flujo.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|