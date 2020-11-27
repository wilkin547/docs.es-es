---
title: 'Extremo: mensajes de mensajería de confianza quitados por segundo'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: b8c0f91b2de5d023232756159a50236574308954
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290847"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a>Extremo: mensajes de mensajería de confianza quitados por segundo

Nombre de contador: sesiones de mensajería de confianza quitadas por segundo.  
  
## <a name="description"></a>Descripción  

 Número total de mensajes de mensajería de confianza quitados en este punto de conexión en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
