---
title: Mensajes de mensajería de confianza quitados por segundo
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: 1e6db155f21fb2443394bc3a65235d4e9539dab3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276183"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a>Mensajes de mensajería de confianza quitados por segundo

Nombre de contador: sesiones de mensajería de confianza quitadas por segundo.  
  
## <a name="description"></a>Descripción  

 Número total de mensajes de mensajería de confianza que han sido quitados en este servicio en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
