---
title: 'Servicio: Llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: 5066108d8183502eeaec7c25186c00d9978261b7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546938"
---
# <a name="service-calls-per-second"></a>Servicio: Llamadas por segundo
Nombre del contador: llamadas por segundo.  
  
## <a name="description"></a>Descripción  
 El número de llamadas por segundo a este servicio.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F), donde el numerador (N) representa el número de operaciones realizadas durante el último intervalo de muestra, el denominador (D) representa el número de pasos transcurridos desde el último intervalo de muestra y F representa la frecuencia de los pasos.
