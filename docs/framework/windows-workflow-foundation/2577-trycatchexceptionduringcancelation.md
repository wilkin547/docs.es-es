---
title: "2577 - TryCatchExceptionDuringCancelation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 2577 - TryCatchExceptionDuringCancelation
## Propiedades  
  
|||  
|-|-|  
|Id.|2577|  
|Palabras clave|WFActivities|  
|Nivel|Advertencia|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que una actividad secundaria de la actividad TryCatch ha producido una excepción durante la cancelación.  
  
## Mensaje  
 Una actividad secundaria de la actividad TryCatch '%1' produjo una excepción durante la cancelación.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|