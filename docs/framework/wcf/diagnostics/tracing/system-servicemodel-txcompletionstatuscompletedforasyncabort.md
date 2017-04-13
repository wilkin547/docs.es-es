---
title: "System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
La transacción especificada para la operación definida se completó debido a la anulación asincrónica.  
  
## Descripción  
 Se anuló la transacción actual debido a que otro participante eligió la interrupción, se produjeron tiempos de espera o hubo otro error dentro del participante de una transacción.  
  
## Solución de problemas  
 Si no se esperaba la anulación, compruebe todos los registros de sistema para determinar la verdadera razón de la anulación.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)