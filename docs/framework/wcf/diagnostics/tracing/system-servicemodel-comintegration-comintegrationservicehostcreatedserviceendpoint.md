---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: f89dd1373d67714046f8cb958582c3a5dea04456
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674787"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a>System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
No puede mover o eliminar el mensaje.  
  
## <a name="description"></a>Descripción  
 El seguimiento indica que se produjo un error al intentar mover, eliminar o rechazar un mensaje de MSMQ.  
  
 Los mensajes MSMQ son empleados por Windows Communication Foundation (WCF) (cuando se utilizan con NetMsmqBinding o MsmqIntegrationBinding). Este seguimiento está relacionado con `ReceiveErrorHandling` el valor elegido de la propiedad en NetMsmqBinding o MsmqIntegrationBinding.  
  
 Este seguimiento no indica un error general del sistema. Sin embargo, indica que la disposición del mensaje dudoso escogida produjo un error en un mensaje. Para obtener más información sobre cuándo los mensajes se vuelven dudosos y cómo configurar el servicio para que los controle adecuadamente, vea [Manejo de mensajes envenenados](../../feature-details/poison-message-handling.md).  
  
## <a name="see-also"></a>Consulte también

- [Rastreo](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)
