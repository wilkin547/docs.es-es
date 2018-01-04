---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2f905c345db89e909920334a7dbb524095bc46b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a>System.ServiceModel.Channels.MsmqMessageDropped
MSMQ colocó el mensaje.  
  
## <a name="description"></a>Descripción  
 El seguimiento de traza indica que se quitó un mensaje de MSMQ. Los mensajes de MSMQ pueden quitarse cuando [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (usado con NetMsmqBinding o MsmqIntegrationBinding) no puede procesarlos. Tales mensajes se conocen como mensajes dudosos.  
  
 Se quita un mensaje dudoso cuando la propiedad `ReceiveErrorHandling` de NetMsmqBinding o MsmqIntegrationBinding está establecida como `Drop`. Un mensaje quitado se quita de la cola y ya no puede recuperarse.  
  
 Vea [de mensajes dudosos](http://go.microsoft.com/fwlink/?LinkID=99546) para obtener más detalles sobre cuándo los mensajes se convierten en mensajes dudosos y cómo configurar el servicio para controlarlos adecuadamente.  
  
## <a name="see-also"></a>Vea también  
 [Traza](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Control de mensajes dudosos](http://go.microsoft.com/fwlink/?LinkID=99546)
