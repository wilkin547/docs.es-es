---
title: "3507 - ServiceEndpointAdded | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3507 - ServiceEndpointAdded
## Propiedades  
  
|||  
|-|-|  
|Id.|3507|  
|Palabras clave|WFServices|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Descripción  
 Indica que se ha agregado un extremo de servicio.  
  
## Mensaje  
 Se ha agregado un extremo de servicio a la dirección '%1', enlace '%2', y contrato '%3'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Dirección|xs:string|Dirección del extremo.|  
|Enlaces|xs:string|El enlace del extremo.|  
|Contrato|xs:string|Contrato del extremo.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|