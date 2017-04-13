---
title: "4210 - SqlExceptionCaught | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f0ce8af3-eb4c-48c8-b3d9-dd2f94b5574b
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4210 - SqlExceptionCaught
## Propiedades  
  
|||  
|-|-|  
|Id.|4210|  
|Palabras clave|WFInstanceStore|  
|Nivel|Advertencia|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que se detectó una excepción SQL.  
  
## Mensaje  
 Se detectó la excepción de SQL con el número %1 y el mensaje %2  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|ErrorNumber|xs:string|Número del error de SQL.|  
|ExceptionMessage|xs:string|El mensaje de la excepción SQL.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|