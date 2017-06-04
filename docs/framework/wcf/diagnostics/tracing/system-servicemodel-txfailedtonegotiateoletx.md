---
title: "System.ServiceModel.TxFailedToNegotiateOleTx | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# System.ServiceModel.TxFailedToNegotiateOleTx
No se pudo completar la negociación protocolar OleTransactions para el contexto de coordinación especificado.  
  
## Descripción  
 Se le hace el seguimiento cuando una transacción entrante con información OleTx no puede usar la información OleTx adjunta, y volverá a utilizar en su lugar WS\-AT.  
  
## Solución de problemas  
 Indica un posible problema en la comunicación MSDTC RPC entre equipos.Si muchos de estos seguimientos aparecen en el registro, puede reducirse drásticamente el rendimiento.Si no se desea OleTx, establezca `OleTxUpgradeEnabled` en 0 en la configuración de registro de WS\-AT.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)