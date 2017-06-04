---
title: "4206 - UnlockInstanceException | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4206 - UnlockInstanceException
## Propiedades  
  
|||  
|-|-|  
|Id.|4206|  
|Palabras clave|WFInstanceStore|  
|Nivel|Error|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que se encontró una excepción al intentar desbloquear una instancia.  
  
## Mensaje  
 Excepción %1 al intentar desbloquear la instancia.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|ExceptionMessage|xs:string|El mensaje de la excepción SQL.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|