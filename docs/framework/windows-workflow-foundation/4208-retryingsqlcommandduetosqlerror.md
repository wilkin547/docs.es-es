---
title: "4208 - RetryingSqlCommandDueToSqlError | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4208 - RetryingSqlCommandDueToSqlError
## Propiedades  
  
|||  
|-|-|  
|Id.|4208|  
|Palabras clave|WFInstanceStore|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que el proveedor de SQL está reintentando un comando SQL debido a un error de SQL.  
  
## Mensaje  
 Reintentando un comando SQL debido al número de error de SQL %1.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|ErrorNumber|xs:string|Número del error de SQL.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|