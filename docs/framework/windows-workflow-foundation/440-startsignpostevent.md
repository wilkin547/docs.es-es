---
title: "440 - StartSignpostEvent1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 440 - StartSignpostEvent1
## Propiedades  
  
|||  
|-|-|  
|Id.|440|  
|Palabras clave|Solución de problemas|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Descripción  
 En el seguimiento de la actividad, indica que un mensaje ha empezado a cruzar el límite de la actividad para enviar o recibir.  
  
## Mensaje  
 Límite de la actividad.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|ExtendedData|`xs:string`|El nombre de la actividad.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|