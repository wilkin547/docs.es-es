---
title: "441- StopSignpostEvent1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc9850a5-0dc3-4b84-a09a-744301c7c18e
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# 441- StopSignpostEvent1
## Propiedades  
  
|||  
|-|-|  
|Id.|441|  
|Palabras clave|Solución de problemas|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Descripción  
 En el seguimiento de la actividad, indica que un mensaje ha terminado de cruzar un límite de la actividad para enviar o recibir.  
  
## Mensaje  
 Límite de la actividad.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Extended Data|`xs:string`|El nombre de la actividad.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|