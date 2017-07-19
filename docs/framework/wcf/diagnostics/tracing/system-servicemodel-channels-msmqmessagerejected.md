---
title: "System.ServiceModel.Channels.MsmqMessageRejected | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.MsmqMessageRejected
MSMQ rechazó el mensaje.  
  
## Descripción  
 Este seguimiento indica que se rechazó un mensaje de MSMQ.  
  
 Se pueden rechazar los mensajes de MSMQ cuando [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] \(usado con NetMsmqBinding o MsmqIntegrationBinding\) no puede procesarlos.Tales mensajes se conocen como mensajes dudosos.Se rechaza un mensaje dudoso cuando la propiedad `ReceiveErrorHandling` de NetMsmqBinding o MsmqIntegrationBinding está establecida en `Reject`.Un mensaje rechazado se devuelve a la [Cola de mensajes no entregados](http://go.microsoft.com/fwlink/?LinkID=99544) del remitente.  
  
 Vea [Control de mensajes dudosos](http://go.microsoft.com/fwlink/?LinkID=99546) para obtener más detalles sobre cuándo se convierten los mensajes en dudosos y cómo configurar el servicio para controlarlos adecuadamente.  
  
 Vea [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548) para obtener más detalles sobre lo que significa un mensaje rechazado en MSMQ.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)   
 [Poison\-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546)   
 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548)