---
title: Errores de llamadas por segundo
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: d3eafc4b31f0e62093a972b7c9f2325a3648d21b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285465"
---
# <a name="calls-failed-per-second"></a>Errores de llamadas por segundo

Nombre de contador: errores de llamadas por segundo  
  
## <a name="description"></a>Descripción  

 Número de llamadas con excepciones no atendidas en esta operación en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 Este contador se incrementa cada vez que hay una excepción no controlada en esta operación.  
  
## <a name="see-also"></a>Vea también

- [Especificación y administración de errores en contratos y servicios](../../specifying-and-handling-faults-in-contracts-and-services.md)
