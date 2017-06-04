---
title: "System.ServiceModel.TxCompletionStatusCompletedForError | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.TxCompletionStatusCompletedForError
La transacción especificada para la operación especificada se completó debido a una excepción de ejecución no controlada.  
  
## Descripción  
 Se efectúa el seguimiento cuando se produce un error durante un intento de completar la transacción actual.Esto sucede antes de que se envíe una respuesta o un error al autor de la llamada.  
  
## Solución de problemas  
 Busque en el mensaje de seguimiento el mensaje de excepción y cualquier elemento procesable.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)