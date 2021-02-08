---
description: 'Más información sobre: System. ServiceModel. Channels. HttpChannelMessageReceiveFailed'
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: 41c31305fabc369faedec460fc3a042426d45e37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769876"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a>System.ServiceModel.Channels.HttpChannelMessageReceiveFailed

Error al recibir un mensaje a través de un canal HTTP.  
  
## <a name="description"></a>Descripción  

 Este seguimiento de traza puede emitirse como una advertencia o un error. En ambos casos, el seguimiento se emite si no se encuentra un agente de escucha compatible para una solicitud HTTP entrante, y se descarta la solicitud. Esto podría suceder si el agente de escucha no reconociese el verbo HTTP de la solicitud, o si el agente realizase la escucha en la dirección a la que está destinada la solicitud. El seguimiento de traza se emite como advertencia en caso de autohospedaje, y como error si el servicio se hospeda en IIS.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
