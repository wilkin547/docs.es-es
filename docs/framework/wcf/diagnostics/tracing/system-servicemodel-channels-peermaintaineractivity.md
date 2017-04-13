---
title: "System.ServiceModel.Channels.PeerMaintainerActivity | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# System.ServiceModel.Channels.PeerMaintainerActivity
El módulo PeerMaintainer realiza una operación específica \(los detalles se incluyen en el cuerpo del mensaje de seguimiento\).  
  
## Descripción  
 Esta traza se produce durante varias operaciones de PeerMaintainer.  
  
 PeerMaintainer es un componente interno de PeerNode.  Cada minuto o cada 32 mensajes recibidos, envía un mensaje de LinkUtility a sus vecinos con estadísticas sobre cuántos mensajes se intercambiaron y cuántos son útiles \(no duplicados, sin modificar\).  Esto ayuda a determinar la utilidad del vínculo de un vecino determinado.  Aproximadamente cada cinco minutos, el mantenedor comprueba el estado de las conexiones de los vecinos.  Si el número de conexiones de los vecinos supera el número ideal, el mantenedor recorta las conexiones menos útiles.  Si no hay bastantes conexiones, el mantenedor adquiere conexiones nuevas.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)