---
title: "System.ServiceModel.Channels.MsmqMessageDropped | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.MsmqMessageDropped
MSMQ colocó el mensaje.  
  
## Descripción  
 El seguimiento de traza indica que se quitó un mensaje de MSMQ.Los mensajes de MSMQ pueden quitarse cuando [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] \(usado con NetMsmqBinding o MsmqIntegrationBinding\) no puede procesarlos.Estos mensajes se conocen como mensajes dudosos.  
  
 Se quita un mensaje dudoso cuando la propiedad `ReceiveErrorHandling` de NetMsmqBinding o MsmqIntegrationBinding está establecida como `Drop`.Un mensaje quitado se quita de la cola y ya no puede recuperarse.  
  
 Vea [Control de mensajes dudosos](http://go.microsoft.com/fwlink/?LinkID=99546) para obtener más información acerca de cuándo se convierten los mensajes en dudosos y cómo configurar el servicio para controlarlos adecuadamente.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)   
 [Poison\-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546)