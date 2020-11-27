---
title: Mensajes en cola rechazados por segundo
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: 2b7686ee94ab051bc255bdb71681c8d1c473094c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276209"
---
# <a name="queued-rejected-messages-per-second"></a>Mensajes en cola rechazados por segundo

Nombre de contador: mensajes en cola rechazados por segundo.  
  
## <a name="description"></a>Descripción  

 Número de mensajes rechazados cada segundo por el transporte en cola en este servicio.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
