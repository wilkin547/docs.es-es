---
title: "4201 - EndSqlCommandExecute | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 4201 - EndSqlCommandExecute
## Propiedades  
  
|||  
|-|-|  
|Id.|4201|  
|Palabras clave|WFInstanceStore|  
|Nivel|Detallado|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que un comando SQL ha terminado de ejecutarse.  
  
## Mensaje  
 Ejecución de comando SQL final: %1  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|SqlCommand|xs:string|El comando SQL que se ejecutó.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|