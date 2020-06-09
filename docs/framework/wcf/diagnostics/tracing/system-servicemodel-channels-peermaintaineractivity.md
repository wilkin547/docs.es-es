---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.date: 03/30/2017
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
ms.openlocfilehash: ce97eaa2ad5c9dbd5f4d6f81186960c489eb4b85
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596082"
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a>System.ServiceModel.Channels.PeerMaintainerActivity
El módulo PeerMaintainer realiza una operación específica (los detalles se incluyen en el cuerpo del mensaje de seguimiento).  
  
## <a name="description"></a>Descripción  
 Esta traza se produce durante varias operaciones de PeerMaintainer.  
  
 PeerMaintainer es un componente interno de PeerNode. Cada minuto o cada 32 mensajes recibidos, envía un mensaje de LinkUtility a sus vecinos con estadísticas sobre cuántos mensajes se intercambiaron y cuántos son útiles (no duplicados, sin modificar). Esto ayuda a determinar la utilidad del vínculo de un vecino determinado. Aproximadamente cada cinco minutos, el mantenedor comprueba el estado de las conexiones de los vecinos. Si el número de conexiones de los vecinos supera el número ideal, el mantenedor recorta las conexiones menos útiles. Si no hay bastantes conexiones, el mantenedor adquiere conexiones nuevas.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
