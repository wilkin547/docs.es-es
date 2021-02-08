---
description: 'Más información sobre: System. ServiceModel. Channels. PeerFlooderReceiveMessageQuotaExceeded'
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: 8ad164b253491f3a533c4828cd76f915eb5aed68
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780875"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a>System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded

La velocidad de mensajes entrantes es demasiado alta.  
  
## <a name="description"></a>Descripción  

 Este seguimiento se produce cuando se intentan procesar los mensajes entrantes. No se pudo reenviar un mensaje a un vecino específico porque se ha superado la cuota establecida para dicho vecino. Esto se produce cuando un vecino que no responde no borra un trabajo pendiente de mensajes pendientes para ese vecino.  
  
## <a name="troubleshooting"></a>Solución de problemas  

 Reduzca la velocidad a la cual se envían los mensajes dentro de la malla.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
