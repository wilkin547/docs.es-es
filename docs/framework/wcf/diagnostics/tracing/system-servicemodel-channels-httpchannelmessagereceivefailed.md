---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: e11b376924ee74e5d0d67da0cac59af41655dc44
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594080"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a>System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
Error al recibir un mensaje a través de un canal HTTP.  
  
## <a name="description"></a>Descripción  
 Este seguimiento de traza puede emitirse como una advertencia o un error. En ambos casos, el seguimiento se emite si no se encuentra un agente de escucha compatible para una solicitud HTTP entrante, y se descarta la solicitud. Esto podría suceder si el agente de escucha no reconociese el verbo HTTP de la solicitud, o si el agente realizase la escucha en la dirección a la que está destinada la solicitud. El seguimiento de traza se emite como advertencia en caso de autohospedaje, y como error si el servicio se hospeda en IIS.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
