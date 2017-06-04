---
title: "System.ServiceModel.Channels.MsmqPoisonMessageRejected | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.MsmqPoisonMessageRejected
Mensaje dudoso rechazado.  
  
## Descripción  
 El seguimiento de traza indica que se encontró un mensaje dudoso y fue posteriormente rechazado.Esto sucede cuando la propiedad `ReceiveErrorHandling` en NetMsmqBinding o MsmqIntegrationBinding está establecida en `Reject`.Un mensaje rechazado se devuelve a la [Cola de mensajes no entregados](http://go.microsoft.com/fwlink/?LinkId=99544) del remitente.  
  
 Vea [Control de mensajes dudosos](http://go.microsoft.com/fwlink/?LinkId=99546) para obtener más detalles sobre cuándo se convierten los mensajes en dudosos y cómo configurar el servicio para controlarlos adecuadamente.Vea [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) para obtener más detalles sobre lo que significa un mensaje rechazado en MSMQ.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)   
 [Poison\-Message Handling](http://go.microsoft.com/fwlink/?LinkId=99546)   
 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548)