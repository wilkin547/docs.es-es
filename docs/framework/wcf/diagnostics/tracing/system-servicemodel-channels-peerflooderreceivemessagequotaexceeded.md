---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2931eec5646b44eea19d70b11eb43c056b0ee0e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a>System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
La velocidad de mensajes entrantes es demasiado alta.  
  
## <a name="description"></a>Descripción  
 Este seguimiento se produce cuando se intentan procesar los mensajes entrantes. No se pudo reenviar un mensaje a un vecino específico porque se ha superado la cuota establecida para dicho vecino. Esto se produce cuando un vecino que no responde no borra un trabajo pendiente de mensajes pendientes para ese vecino.  
  
## <a name="troubleshooting"></a>Solución de problemas  
 Reduzca la velocidad a la cual se envían los mensajes dentro de la malla.  
  
## <a name="see-also"></a>Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Uso del seguimiento para solucionar problemas de la aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)
