---
title: "System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
No puede mover o eliminar el mensaje.  
  
## Descripción  
 El seguimiento indica que se produjo un error al intentar mover, eliminar o rechazar un mensaje de MSMQ.  
  
 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] emplea mensajes MSMQ \(cuando se utiliza con NetMsmqBinding o MsmqIntegrationBinding\).Este seguimiento está relacionado con el valor elegido de la propiedad `ReceiveErrorHandling` en NetMsmqBinding o MsmqIntegrationBinding.  
  
 Este seguimiento no indica un error general del sistema.  Sin embargo, indica que la disposición del mensaje dudoso escogida produjo un error en un mensaje.  Vea [Control de mensajes dudosos](http://go.microsoft.com/fwlink/?LinkID=99546) para obtener más detalles sobre cuándo se convierten los mensajes en dudosos y cómo configurar el servicio para controlarlos adecuadamente.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)