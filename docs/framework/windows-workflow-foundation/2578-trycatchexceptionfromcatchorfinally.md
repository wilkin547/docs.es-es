---
title: "2578 - TryCatchExceptionFromCatchOrFinally | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4803fee6-b8d8-4937-9907-d5c5fd5299db
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 2578 - TryCatchExceptionFromCatchOrFinally
## Propiedades  
  
|||  
|-|-|  
|Id.|2578|  
|Palabras clave|WFActivities|  
|Nivel|Advertencia|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que una actividad Catch o Finally ha producido una excepción.  
  
## Mensaje  
 Una actividad Catch o Finally asociada a la actividad TryCatch '%1' produjo una excepción.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|