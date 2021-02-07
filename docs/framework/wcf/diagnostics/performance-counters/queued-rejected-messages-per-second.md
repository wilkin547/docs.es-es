---
description: 'Más información sobre: mensajes rechazados en cola por segundo'
title: Mensajes en cola rechazados por segundo
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: d0d227a26a49921449786d2c9f885fac13a82bde
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99744076"
---
# <a name="queued-rejected-messages-per-second"></a>Mensajes en cola rechazados por segundo

Nombre de contador: mensajes en cola rechazados por segundo.  
  
## <a name="description"></a>Descripción  

 Número de mensajes rechazados cada segundo por el transporte en cola en este servicio.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
