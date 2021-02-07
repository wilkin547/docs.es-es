---
description: 'Más información sobre: mensajes dudosos en cola por segundo'
title: Mensajes dudosos en cola por segundo
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: 3240974445debf86ff17187e4c6762b39610bd46
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99744089"
---
# <a name="queued-poison-messages-per-second"></a>Mensajes dudosos en cola por segundo

Nombre de contador: Mensajes dudosos en cola por segundo.  
  
## <a name="description"></a>Descripción  

 Número de mensajes marcados como dudosos por el transporte en cola en este servicio en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
