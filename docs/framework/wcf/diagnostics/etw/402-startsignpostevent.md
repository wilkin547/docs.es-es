---
title: "402 - StartSignpostEvent | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5e5be126-765d-4ac9-88e7-008e9ef4f0e5
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 402 - StartSignpostEvent
## Propiedades  
  
|||  
|-|-|  
|Id.|402|  
|Palabras clave|Solución de problemas|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Descripción  
 Este evento marca el inicio de una actividad de un extremo a otro.Contiene el nombre de la actividad.  
  
## Mensaje  
 Límite de la actividad.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Extended Data|`xs:string`|El nombre de la actividad.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|