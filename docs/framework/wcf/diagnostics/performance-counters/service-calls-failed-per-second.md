---
title: 'Servicio: Errores en llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: 5629c55cba6f21de24a1de7e8d38a9c08fcf4fb1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559114"
---
# <a name="service-calls-failed-per-second"></a>Servicio: Errores en llamadas por segundo
Nombre del contador: Errores de llamadas por segundo.  
  
## <a name="description"></a>Descripción  
 Número de llamadas que tienen excepciones no controladas y que son recibidas por este servicio en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 En código administrado, las excepciones se inician al producirse condiciones de error.  
  
 En código administrado, las excepciones se inician al producirse condiciones de error.  
  
 El contador se incrementa cada vez que hay una excepción no atendida en este servicio.  
  
## <a name="see-also"></a>Vea también

- [Especificación y administración de errores en contratos y servicios](../../specifying-and-handling-faults-in-contracts-and-services.md)
